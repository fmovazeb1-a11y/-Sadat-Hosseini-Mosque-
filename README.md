# -Sadat-Hosseini-Mosque-


/*
 * SEPİDAR MOSQUE BACKEND
 * Google Apps Script + Google Sheets
 *
 * ابتدا initializeDatabase را یک بار اجرا کن.
 * سپس در Script Properties رمز مدیر را تنظیم کن.
 */

const APP = {
  SHEETS: {
    Members: ['id', 'name', 'group', 'points', 'active', 'createdAt'],
    Attendance: ['id', 'memberId', 'date', 'status', 'note', 'createdAt'],
    Points: ['id', 'memberId', 'delta', 'reason', 'date', 'createdAt'],
    Reviews: ['id', 'memberId', 'type', 'message', 'status', 'reply', 'createdAt', 'updatedAt'],
    AdminLogs: ['id', 'action', 'details', 'createdAt']
  },
  SESSION_HOURS: 8
};

function initializeDatabase() {
  const props = PropertiesService.getScriptProperties();
  let dbId = props.getProperty('DB_ID');

  if (!dbId) {
    const ss = SpreadsheetApp.create('Sepidar Mosque Database');
    dbId = ss.getId();
    props.setProperty('DB_ID', dbId);
  }

  const ss = SpreadsheetApp.openById(dbId);

  Object.keys(APP.SHEETS).forEach(name => {
    let sh = ss.getSheetByName(name);
    if (!sh) sh = ss.insertSheet(name);

    const headers = APP.SHEETS[name];
    if (sh.getLastRow() === 0) {
      sh.appendRow(headers);
      sh.setFrozenRows(1);
    }
  });

  if (!props.getProperty('SESSION_SECRET')) {
    props.setProperty(
      'SESSION_SECRET',
      Utilities.getUuid() + Utilities.getUuid()
    );
  }

  Logger.log('Database ready: ' + ss.getUrl());
}

/*
 * رمز مدیر را از مسیر:
 * Project Settings > Script Properties
 * با نام ADMIN_PASSWORD تنظیم کن.
 *
 * این تابع رمز را به هش تبدیل می‌کند و مقدار خام را پاک می‌کند.
 */
function secureAdminPassword() {
  const props = PropertiesService.getScriptProperties();
  const password = props.getProperty('ADMIN_PASSWORD');

  if (!password || password.length < 8) {
    throw new Error('رمز مدیر باید حداقل ۸ کاراکتر باشد.');
  }

  props.setProperty('ADMIN_PASSWORD_HASH', sha256(password));
  props.deleteProperty('ADMIN_PASSWORD');

  Logger.log('Admin password secured.');
}

function doGet(e) {
  const params = (e && e.parameter) || {};
  const callback = params.callback || '';

  let result;
  try {
    result = handleRequest(params);
  } catch (err) {
    result = { ok: false, error: String(err.message || err) };
  }

  const json = JSON.stringify(result);

  if (callback) {
    if (!/^[a-zA-Z_$][0-9a-zA-Z_$\.]*$/.test(callback)) {
      return ContentService.createTextOutput('Invalid callback');
    }

    return ContentService
      .createTextOutput(callback + '(' + json + ');')
      .setMimeType(ContentService.MimeType.JAVASCRIPT);
  }

  return ContentService
    .createTextOutput(json)
    .setMimeType(ContentService.MimeType.JSON);
}

function handleRequest(p) {
  const action = String(p.action || '');

  if (action === 'publicData') return getPublicData();
  if (action === 'login') return login(p.password);
  if (action === 'submitReview') return submitReview(p);

  const adminActions = [
    'addMember',
    'deleteMember',
    'attendance',
    'changePoints',
    'reviewDecision',
    'changePassword'
  ];

  if (adminActions.includes(action)) {
    verifySession(p.token);
    return runAdminAction(action, p);
  }

  throw new Error('درخواست نامعتبر است.');
}

function db() {
  const id = PropertiesService.getScriptProperties().getProperty('DB_ID');
  if (!id) throw new Error('پایگاه داده راه‌اندازی نشده است.');
  return SpreadsheetApp.openById(id);
}

function sheet(name) {
  const sh = db().getSheetByName(name);
  if (!sh) throw new Error('جدول پیدا نشد: ' + name);
  return sh;
}

function readTable(name) {
  const values = sheet(name).getDataRange().getValues();
  if (values.length < 2) return [];

  const headers = values[0].map(String);
  return values.slice(1)
    .filter(row => row.some(cell => cell !== ''))
    .map(row => {
      const obj = {};
      headers.forEach((key, i) => {
        let value = row[i];
        if (value instanceof Date) {
          value = value.toISOString();
        }
        obj[key] = value;
      });
      return obj;
    });
}

function getPublicData() {
  const members = readTable('Members')
    .filter(m => String(m.active) === 'TRUE' || m.active === true);

  return {
    ok: true,
    members: members,
    attendance: readTable('Attendance'),
    points: readTable('Points'),
    reviews: readTable('Reviews').map(r => ({
      id: r.id,
      memberId: r.memberId,
      type: r.type,
      message: r.message,
      status: r.status,
      reply: r.reply,
      createdAt: r.createdAt,
      updatedAt: r.updatedAt
    })),
    updatedAt: new Date().toISOString()
  };
}

function login(password) {
  const props = PropertiesService.getScriptProperties();
  const savedHash = props.getProperty('ADMIN_PASSWORD_HASH');

  if (!savedHash) throw new Error('رمز مدیر هنوز تنظیم نشده است.');

  if (sha256(String(password || '')) !== savedHash) {
    Utilities.sleep(700);
    throw new Error('رمز مدیر اشتباه است.');
  }

  const expires = Date.now() + APP.SESSION_HOURS * 60 * 60 * 1000;
  const payload = Utilities.base64EncodeWebSafe(
    JSON.stringify({ exp: expires })
  );

  const signature = sign(payload);
  return { ok: true, token: payload + '.' + signature, expiresAt: expires };
}

function verifySession(token) {
  if (!token || typeof token !== 'string') {
    throw new Error('ابتدا وارد پنل مدیریت شو.');
  }

  const parts = token.split('.');
  if (parts.length !== 2 || sign(parts[0]) !== parts[1]) {
    throw new Error('نشست مدیر معتبر نیست؛ دوباره وارد شو.');
  }

  let data;
  try {
    data = JSON.parse(
      Utilities.newBlob(
        Utilities.base64DecodeWebSafe(parts[0])
      ).getDataAsString()
    );
  } catch (_) {
    throw new Error('نشست مدیر نامعتبر است.');
  }

  if (!data.exp || Date.now() > data.exp) {
    throw new Error('نشست مدیر منقضی شده است.');
  }
}

function sign(value) {
  const secret = PropertiesService.getScriptProperties()
    .getProperty('SESSION_SECRET');

  if (!secret) throw new Error('کلید امنیتی تنظیم نشده است.');

  const bytes = Utilities.computeHmacSha256Signature(value, secret);
  return Utilities.base64EncodeWebSafe(bytes);
}

function sha256(value) {
  const bytes = Utilities.computeDigest(
    Utilities.DigestAlgorithm.SHA_256,
    value,
    Utilities.Charset.UTF_8
  );
  return Utilities.base64EncodeWebSafe(bytes);
}

function runAdminAction(action, p) {
  const lock = LockService.getScriptLock();
  lock.waitLock(15000);

  try {
    if (action === 'addMember') {
      const name = clean(p.name, 80);
      const group = clean(p.group || '', 40);
      if (!name) throw new Error('نام عضو را وارد کن.');

      const id = Utilities.getUuid();
      sheet('Members').appendRow([
        id, name, group, 0, true, new Date()
      ]);

      logAction('افزودن عضو', name);
      return { ok: true, id: id };
    }

    if (action === 'deleteMember') {
      const id = clean(p.memberId, 80);
      const sh = sheet('Members');
      const rows = sh.getDataRange().getValues();

      for (let i = 1; i < rows.length; i++) {
        if (String(rows[i][0]) === id) {
          sh.getRange(i + 1, 5).setValue(false);
          logAction('غیرفعال کردن عضو', String(rows[i][1]));
          return { ok: true };
        }
      }
      throw new Error('عضو پیدا نشد.');
    }

    if (action === 'attendance') {
      const memberId = clean(p.memberId, 80);
      const status = clean(p.status, 20);
      const date = clean(p.date || '', 30);
      const note = clean(p.note || '', 200);

      if (!['حاضر', 'غایب', 'تاخیر', 'موجه'].includes(status)) {
        throw new Error('وضعیت حضور نامعتبر است.');
      }
      if (!findMember(memberId)) throw new Error('عضو پیدا نشد.');

      sheet('Attendance').appendRow([
        Utilities.getUuid(), memberId, date || new Date().toISOString(),
        status, note, new Date()
      ]);

      logAction('ثبت حضور و غیاب', memberId + ' - ' + status);
      return { ok: true };
    }

    if (action === 'changePoints') {
      const memberId = clean(p.memberId, 80);
      const delta = Number(p.delta);
      const reason = clean(p.reason, 250);

      if (!findMember(memberId)) throw new Error('عضو پیدا نشد.');
      if (!Number.isInteger(delta) || delta === 0 || Math.abs(delta) > 10000) {
        throw new Error('مقدار امتیاز نامعتبر است.');
      }
      if (!reason) throw new Error('دلیل تغییر امتیاز را بنویس.');

      const sh = sheet('Members');
      const rows = sh.getDataRange().getValues();

      for (let i = 1; i < rows.length; i++) {
        if (String(rows[i][0]) === memberId && rows[i][4] === true) {
          const current = Number(rows[i][3]) || 0;
          sh.getRange(i + 1, 4).setValue(current + delta);
          sheet('Points').appendRow([
            Utilities.getUuid(), memberId, delta, reason,
            new Date().toISOString(), new Date()
          ]);
          logAction('تغییر امتیاز', memberId + ' / ' + delta + ' / ' + reason);
          return { ok: true, points: current + delta };
        }
      }
      throw new Error('عضو فعال پیدا نشد.');
    }

    if (action === 'reviewDecision') {
      const id = clean(p.reviewId, 80);
      const status = clean(p.status, 30);
      const reply = clean(p.reply || '', 300);

      if (!['بررسی شد', 'تأیید شد', 'رد شد'].includes(status)) {
        throw new Error('وضعیت درخواست نامعتبر است.');
      }

      const sh = sheet('Reviews');
      const rows = sh.getDataRange().getValues();

      for (let i = 1; i < rows.length; i++) {
        if (String(rows[i][0]) === id) {
          sh.getRange(i + 1, 5).setValue(status);
          sh.getRange(i + 1, 6).setValue(reply);
          sh.getRange(i + 1, 8).setValue(new Date());
          logAction('رسیدگی به درخواست', id + ' / ' + status);
          return { ok: true };
        }
      }
      throw new Error('درخواست پیدا نشد.');
    }

    if (action === 'changePassword') {
      const oldPassword = String(p.oldPassword || '');
      const newPassword = String(p.newPassword || '');

      const props = PropertiesService.getScriptProperties();
      if (sha256(oldPassword) !== props.getProperty('ADMIN_PASSWORD_HASH')) {
        throw new Error('رمز فعلی اشتباه است.');
      }
      if (newPassword.length < 8) {
        throw new Error('رمز جدید باید حداقل ۸ کاراکتر باشد.');
      }

      props.setProperty('ADMIN_PASSWORD_HASH', sha256(newPassword));
      logAction('تغییر رمز مدیر', 'رمز مدیر تغییر کرد');
      return { ok: true };
    }

    throw new Error('عملیات ناشناخته است.');
  } finally {
    lock.releaseLock();
  }
}

function submitReview(p) {
  const memberId = clean(p.memberId, 80);
  const type = clean(p.type, 30);
  const message = clean(p.message, 500);

  if (!findMember(memberId)) throw new Error('عضو پیدا نشد.');
  if (!['امتیاز', 'حضور و غیاب'].includes(type)) {
    throw new Error('نوع درخواست نامعتبر است.');
  }
  if (message.length < 5) throw new Error('توضیحات درخواست کوتاه است.');

  sheet('Reviews').appendRow([
    Utilities.getUuid(), memberId, type, message,
    'در انتظار بررسی', '', new Date(), new Date()
  ]);

  return { ok: true };
}

function findMember(id) {
  return readTable('Members').find(m =>
    String(m.id) === String(id) &&
    (m.active === true || String(m.active) === 'TRUE')
  );
}

function logAction(action, details) {
  sheet('AdminLogs').appendRow([
    Utilities.getUuid(), action, details, new Date()
  ]);
}

function clean(value, max) {
  return String(value == null ? '' : value)
    .replace(/[<>]/g, '')
    .trim()
    .slice(0, max);
}
