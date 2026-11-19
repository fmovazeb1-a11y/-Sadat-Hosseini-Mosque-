# -Sadat-Hosseini-Mosque-


<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#092b22">
<title>مسجد سادات حسینی | گروهک سپیدار</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600;700;800&family=Amiri:wght@400;700&display=swap" rel="stylesheet">

<style>
:root {
  --bg:#071e19;
  --bg2:#0b3025;
  --panel:rgba(15,55,42,.88);
  --panel2:#123d2e;
  --gold:#d8b66a;
  --gold2:#f0d99c;
  --cream:#f4eedf;
  --muted:#b8c7b9;
  --line:rgba(216,182,106,.22);
  --green:#1d6a4a;
  --red:#bd655d;
  --shadow:0 16px 45px rgba(0,0,0,.24);
}
* {box-sizing:border-box}
html {scroll-behavior:smooth}
body {
  margin:0;
  min-height:100vh;
  color:var(--cream);
  background:
    radial-gradient(ellipse at 15% 10%,rgba(35,111,75,.25),transparent 38%),
    radial-gradient(ellipse at 90% 80%,rgba(190,145,61,.09),transparent 35%),
    var(--bg);
  font-family:"Vazirmatn",sans-serif;
}
body:before {
  content:"";
  position:fixed;
  inset:0;
  pointer-events:none;
  opacity:.12;
  z-index:-1;
  background-image:
    repeating-linear-gradient(45deg,transparent 0 28px,rgba(216,182,106,.2) 29px 30px,transparent 31px 58px),
    repeating-linear-gradient(-45deg,transparent 0 28px,rgba(216,182,106,.13) 29px 30px,transparent 31px 58px);
  background-size:58px 58px;
}
button,input,select,textarea {font:inherit}
button {cursor:pointer}
button:focus-visible,input:focus-visible,select:focus-visible,textarea:focus-visible {
  outline:2px solid var(--gold2);
  outline-offset:3px;
}
.container {width:min(1160px,92%);margin:auto}
.topbar {
  border-bottom:1px solid var(--line);
  background:rgba(5,25,20,.78);
  backdrop-filter:blur(16px);
  position:sticky;top:0;z-index:20;
}
.top-inner {
  min-height:76px;
  display:flex;align-items:center;justify-content:space-between;gap:15px;
}
.brand {display:flex;align-items:center;gap:12px}
.logo {
  width:47px;height:47px;border:1px solid var(--gold);
  border-radius:15px;display:grid;place-items:center;
  color:var(--gold2);font-size:25px;
  background:linear-gradient(145deg,#1b523b,#09251d);
  box-shadow:0 0 25px rgba(216,182,106,.12);
}
.brand h1 {font-size:16px;margin:0;font-weight:800}
.brand small {display:block;color:var(--muted);font-size:11px;margin-top:3px}
.top-actions {display:flex;gap:8px;align-items:center}
.btn {
  border:1px solid var(--line);border-radius:12px;
  padding:10px 15px;color:var(--cream);
  background:rgba(255,255,255,.04);
  transition:.2s;
}
.btn:hover {transform:translateY(-2px);border-color:var(--gold)}
.btn.gold {
  color:#17251b;background:linear-gradient(135deg,var(--gold2),var(--gold));
  border:0;font-weight:800;
}
.btn.small {padding:7px 11px;font-size:12px}
.hero {padding:44px 0 25px}
.hero-card {
  border:1px solid var(--line);border-radius:25px;
  padding:30px;position:relative;overflow:hidden;
  background:linear-gradient(115deg,rgba(19,67,48,.95),rgba(8,37,29,.94));
  box-shadow:var(--shadow);
}
.hero-card:after {
  content:"۞";position:absolute;left:15px;top:-48px;
  font-size:220px;color:rgba(216,182,106,.07);
}
.hero-content {position:relative;z-index:1}
.eyebrow {color:var(--gold2);font-size:12px;letter-spacing:.4px}
.hero h2 {font-size:clamp(23px,4vw,38px);margin:10px 0}
.hero p {color:var(--muted);line-height:2;margin:0;max-width:650px}
.ayah {
  margin-top:24px;padding:18px;border-radius:16px;
  border:1px solid rgba(216,182,106,.25);
  background:rgba(0,0,0,.13);
}
.ayah .arabic {
  font-family:"Amiri",serif;font-size:clamp(21px,3.5vw,29px);
  color:var(--gold2);line-height:1.9;text-align:center;
}
.ayah small {display:block;text-align:center;color:var(--muted);margin-top:8px}
.stats {
  display:grid;grid-template-columns:repeat(3,1fr);
  gap:13px;margin:20px 0;
}
.stat,.card {
  background:var(--panel);border:1px solid var(--line);
  border-radius:18px;box-shadow:var(--shadow);
}
.stat {padding:18px}
.stat span {color:var(--muted);font-size:12px}
.stat strong {display:block;color:var(--gold2);font-size:26px;margin-top:6px}
.nav {
  display:flex;gap:8px;overflow-x:auto;padding:8px 0 15px;
  scrollbar-width:thin;
}
.nav button {
  white-space:nowrap;border:1px solid var(--line);
  color:var(--muted);background:rgba(255,255,255,.035);
  border-radius:12px;padding:10px 15px;
}
.nav button.active,.nav button:hover {
  color:#17251b;background:var(--gold);border-color:var(--gold);
}
.section {display:none;padding:8px 0 35px;animation:appear .3s ease}
.section.active {display:block}
@keyframes appear {from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}
.section-title {display:flex;align-items:center;justify-content:space-between;gap:12px;margin:12px 0 18px}
.section-title h2 {font-size:19px;margin:0}
.section-title p {color:var(--muted);font-size:12px;margin:5px 0 0}
.card {padding:20px;margin-bottom:15px}
.grid {display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:15px}
.member-list {display:grid;gap:10px}
.member {
  display:flex;align-items:center;justify-content:space-between;gap:12px;
  padding:14px;border-radius:14px;background:rgba(255,255,255,.035);
  border:1px solid rgba(255,255,255,.07);
}
.member-info {display:flex;align-items:center;gap:11px;min-width:0}
.avatar {
  width:42px;height:42px;border-radius:13px;display:grid;place-items:center;
  background:linear-gradient(145deg,#d8b66a,#94713a);
  color:#18271d;font-weight:800;flex-shrink:0;
}
.member-name {font-weight:700}
.member-sub {font-size:11px;color:var(--muted);margin-top:3px}
.points {color:var(--gold2);font-weight:800;white-space:nowrap}
.table-wrap {overflow-x:auto}
table {width:100%;border-collapse:collapse;min-width:440px}
th,td {padding:13px 10px;text-align:right;border-bottom:1px solid var(--line);font-size:13px}
th {color:var(--gold2);font-weight:700}
td {color:var(--cream)}
input,select,textarea {
  width:100%;padding:12px;border-radius:11px;
  color:var(--cream);background:#09271f;border:1px solid var(--line);
}
textarea {min-height:95px;resize:vertical}
label {display:block;font-size:12px;color:var(--muted);margin:12px 0 7px}
.form-grid {display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}
.form-actions {display:flex;gap:9px;flex-wrap:wrap;margin-top:15px}
.notice {
  border:1px solid rgba(216,182,106,.25);border-radius:13px;
  padding:13px;color:var(--muted);font-size:12px;line-height:1.9;
  background:rgba(216,182,106,.06);
}
.empty {padding:25px;text-align:center;color:var(--muted);font-size:13px}
.profile-head {display:flex;align-items:center;gap:14px;margin-bottom:18px}
.profile-head .avatar {width:60px;height:60px;font-size:22px}
.badge {
  display:inline-block;border-radius:30px;padding:5px 10px;
  background:rgba(216,182,106,.12);color:var(--gold2);font-size:11px;
}
footer {border-top:1px solid var(--line);padding:25px 0 35px;text-align:center;color:var(--muted);font-size:12px}
footer strong {color:var(--gold2)}
.toast {
  position:fixed;bottom:20px;left:50%;transform:translate(-50%,20px);
  background:#f4eedf;color:#12271d;padding:12px 18px;border-radius:12px;
  opacity:0;pointer-events:none;transition:.25s;z-index:99;font-size:13px;
  box-shadow:var(--shadow);max-width:90%;text-align:center;
}
.toast.show {opacity:1;transform:translate(-50%,0)}
@media(max-width:650px) {
  .top-inner {min-height:67px}
  .brand h1 {font-size:14px}
  .brand small {font-size:10px}
  .logo {width:40px;height:40px}
  .top-actions .btn {padding:8px 10px;font-size:11px}
  .hero {padding-top:25px}
  .hero-card {padding:21px}
  .stats {gap:8px}
  .stat {padding:13px 10px}
  .stat strong {font-size:21px}
  .stat span {font-size:10px}
  .grid,.form-grid {grid-template-columns:1fr}
  .section-title h2 {font-size:17px}
  .card {padding:15px}
}
@media(prefers-reduced-motion:reduce) {
  *,*:before,*:after {animation:none!important;scroll-behavior:auto!important;transition:none!important}
}
</style>
</head>

<body>
<header class="topbar">
  <div class="container top-inner">
    <div class="brand">
      <div class="logo">۞</div>
      <div>
        <h1>مسجد سادات حسینی</h1>
        <small>سامانه اعضا و امتیازات</small>
      </div>
    </div>
    <div class="top-actions">
      <span class="badge">گروهک سپیدار</span>
      <button class="btn small" onclick="showSection('admin')">مدیریت</button>
    </div>
  </div>
</header>

<main class="container">
  <section class="hero">
    <div class="hero-card">
      <div class="hero-content">
        <div class="eyebrow">سامانه یکپارچه اعضای مسجد</div>
        <h2>به مسجد سادات حسینی خوش آمدید</h2>
        <p>سامانه‌ای برای مشاهده امتیازات، رتبه‌بندی، حضور و غیاب و سوابق اعضا؛ با هدف نظم، شفافیت و مشارکت بیشتر.</p>
        <div class="ayah">
          <div class="arabic">إِنَّ اللَّهَ يُحِبُّ الْمُحْسِنِينَ</div>
          <small>خداوند نیکوکاران را دوست دارد — سوره بقره، آیه ۱۹۵</small>
        </div>
      </div>
    </div>
  </section>

  <section class="stats">
    <div class="stat"><span>تعداد اعضای فعال</span><strong id="memberCount">۰</strong></div>
    <div class="stat"><span>مجموع امتیازات</span><strong id="totalPoints">۰</strong></div>
    <div class="stat"><span>تعداد ثبت حضور</span><strong id="attendanceCount">۰</strong></div>
  </section>

  <nav class="nav" aria-label="بخش‌های سایت">
    <button class="active" data-section="dashboard" onclick="showSection('dashboard',this)">خانه</button>
    <button data-section="members" onclick="showSection('members',this)">اعضا</button>
    <button data-section="ranking" onclick="showSection('ranking',this)">رتبه‌بندی</button>
    <button data-section="profile" onclick="showSection('profile',this)">پروفایل عضو</button>
    <button data-section="admin" onclick="showSection('admin',this)">مدیریت</button>
  </nav>

  <section id="dashboard" class="section active">
    <div class="section-title">
      <div><h2>نمای کلی سامانه</h2><p>اطلاعات کلی اعضا و فعالیت‌ها</p></div>
      <span class="badge">داشبورد</span>
    </div>
    <div class="grid">
      <div class="card">
        <h3>اعضای برتر</h3>
        <div id="topMembers" class="member-list"><div class="empty">هنوز اطلاعاتی متصل نشده است.</div></div>
      </div>
      <div class="card">
        <h3>آخرین تغییرات امتیاز</h3>
        <div id="recentPoints" class="empty">پس از اتصال پایگاه داده نمایش داده می‌شود.</div>
      </div>
    </div>
    <div class="notice">این سامانه برای نمایش عمومی طراحی شده است. ثبت یا تغییر اطلاعات فقط از طریق دسترسی مدیریتی انجام خواهد شد.</div>
  </section>

  <section id="members" class="section">
    <div class="section-title"><div><h2>فهرست اعضا</h2><p>جست‌وجو و مشاهده اطلاعات اعضا</p></div></div>
    <div class="card">
      <label for="memberSearch">جست‌وجوی نام عضو</label>
      <input id="memberSearch" placeholder="نام عضو را وارد کن..." oninput="renderMembers()">
      <div id="memberList" class="member-list" style="margin-top:15px">
        <div class="empty">هنوز عضوی ثبت نشده است.</div>
      </div>
    </div>
  </section>

  <section id="ranking" class="section">
    <div class="section-title"><div><h2>جدول رتبه‌بندی</h2><p>رتبه اعضا بر اساس امتیاز فعلی</p></div></div>
    <div class="card table-wrap">
      <table>
        <thead><tr><th>رتبه</th><th>نام عضو</th><th>امتیاز</th><th>پروفایل</th></tr></thead>
        <tbody id="rankingBody"><tr><td colspan="4" class="empty">اطلاعاتی برای نمایش وجود ندارد.</td></tr></tbody>
      </table>
    </div>
  </section>

  <section id="profile" class="section">
    <div class="section-title"><div><h2>پروفایل عضو</h2><p>سوابق امتیاز و حضور و غیاب</p></div></div>
    <div class="card">
      <label for="profileSelect">انتخاب عضو</label>
      <select id="profileSelect" onchange="renderProfile()"><option value="">ابتدا عضو را انتخاب کن</option></select>
      <div id="profileContent" class="empty">پس از اتصال اطلاعات اعضا، پروفایل اینجا نمایش داده می‌شود.</div>
    </div>
  </section>

  <section id="admin" class="section">
    <div class="section-title"><div><h2>پنل مدیریت</h2><p>ویژه مدیر سامانه</p></div><span class="badge">مدیریت</span></div>
    <div class="card" id="loginCard">
      <h3>ورود مدیر</h3>
      <p class="member-sub">برای مدیریت اعضا و ثبت تغییرات، وارد حساب مدیر شو.</p>
      <label for="adminPassword">رمز عبور</label>
      <input id="adminPassword" type="password" autocomplete="current-password" placeholder="رمز مدیر">
      <div class="form-actions"><button class="btn gold" onclick="loginAdmin()">ورود به مدیریت</button></div>
      <div id="loginMessage" class="member-sub" role="status"></div>
    </div>

    <div id="adminPanel" hidden>
      <div class="card">
        <div class="section-title"><h2>افزودن عضو</h2><button class="btn small" onclick="logoutAdmin()">خروج مدیر</button></div>
        <div class="form-grid">
          <div><label for="newName">نام و نام خانوادگی</label><input id="newName" placeholder="نام عضو"></div>
          <div><label for="newGroup">گروه یا پایه (اختیاری)</label><input id="newGroup" placeholder="مثلاً نوجوانان"></div>
        </div>
        <div class="form-actions"><button class="btn gold" onclick="adminAction('addMember')">ثبت عضو</button></div>
      </div>

      <div class="card">
        <h3>تغییر امتیاز</h3>
        <label for="pointMember">عضو</label><select id="pointMember"></select>
        <div class="form-grid">
          <div><label for="pointDelta">مقدار تغییر (مثبت یا منفی)</label><input id="pointDelta" type="number" placeholder="مثلاً ۵ یا -۲"></div>
          <div><label for="pointReason">دلیل تغییر</label><input id="pointReason" placeholder="دلیل را واضح بنویس"></div>
        </div>
        <div class="form-actions"><button class="btn gold" onclick="adminAction('changePoints')">ثبت تغییر امتیاز</button></div>
      </div>

      <div class="card">
        <h3>ثبت حضور و غیاب</h3>
        <label for="attendanceMember">عضو</label><select id="attendanceMember"></select>
        <div class="form-grid">
          <div><label for="attendanceStatus">وضعیت</label>
            <select id="attendanceStatus">
              <option>حاضر</option><option>غایب</option><option>تاخیر</option><option>موجه</option>
            </select>
          </div>
          <div><label for="attendanceDate">تاریخ</label><input id="attendanceDate" placeholder="مثلاً ۱۴۰۵/۰۸/۲۹"></div>
        </div>
        <label for="attendanceNote">توضیحات (اختیاری)</label><input id="attendanceNote" placeholder="توضیحات">
        <div class="form-actions"><button class="btn gold" onclick="adminAction('attendance')">ثبت حضور</button></div>
      </div>

      <div class="card">
        <h3>درخواست‌های بررسی اعضا</h3>
        <div id="reviewList" class="empty">درخواست‌ها پس از اتصال سرور نمایش داده می‌شوند.</div>
      </div>

      <div class="card">
        <h3>تغییر رمز مدیر</h3>
        <label for="oldPassword">رمز فعلی</label><input id="oldPassword" type="password">
        <label for="newPassword">رمز جدید</label><input id="newPassword" type="password">
        <div class="form-actions"><button class="btn" onclick="changePassword()">تغییر رمز</button></div>
      </div>
    </div>
  </section>
</main>

<footer>
  <div>با آرزوی توفیق و همدلی برای همه اعضا</div>
  <div style="margin-top:8px">طراحی و توسعه توسط <strong>گروهک سپیدار</strong></div>
</footer>

<div class="toast" id="toast" role="status"></div>

<script>
/*
 * پس از آماده شدن سرور، آدرس Web App در این قسمت قرار می‌گیرد.
 * تا آن زمان، عملیات مدیریتی و دریافت اطلاعات فعال نیستند.
 */
const API_URL = "";

let appData = {
  members: [],
  attendance: [],
  points: [],
  reviews: []
};
let adminToken = "";

const fa = value => Number(value || 0).toLocaleString('fa-IR');

function toast(message) {
  const el = document.getElementById('toast');
  el.textContent = message;
  el.classList.add('show');
  setTimeout(() => el.classList.remove('show'), 2800);
}

function showSection(id, button) {
  document.querySelectorAll('.section').forEach(el => el.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  document.querySelectorAll('.nav button').forEach(el => el.classList.remove('active'));
  const navButton = button || document.querySelector('[data-section="' + id + '"]');
  if (navButton) navButton.classList.add('active');
  window.scrollTo({top:0,behavior:'smooth'});
}

function activeMembers() {
  return appData.members.filter(m => m.active === true || String(m.active).toUpperCase() === 'TRUE');
}

function renderStats() {
  const members = activeMembers();
  document.getElementById('memberCount').textContent = fa(members.length);
  document.getElementById('totalPoints').textContent = fa(
    members.reduce((sum,m) => sum + Number(m.points || 0),0)
  );
  document.getElementById('attendanceCount').textContent = fa(appData.attendance.length);
}

function memberName(id) {
  const m = appData.members.find(x => String(x.id) === String(id));
  return m ? m.name : 'عضو حذف‌شده';
}

function openProfile(id) {
  showSection('profile');
  document.getElementById('profileSelect').value = id;
  renderProfile();
}

function renderMembers() {
  const q = document.getElementById('memberSearch').value.trim().toLowerCase();
  const members = activeMembers().filter(m => String(m.name).toLowerCase().includes(q));
  const box = document.getElementById('memberList');
  box.innerHTML = '';
  if (!members.length) {
    box.innerHTML = '<div class="empty">عضوی پیدا نشد.</div>';
    return;
  }
  members.forEach(m => {
    const item = document.createElement('div');
    item.className = 'member';
    const info = document.createElement('div');
    info.className = 'member-info';
    const avatar = document.createElement('div');
    avatar.className = 'avatar';
    avatar.textContent = String(m.name || '?').trim().charAt(0);
    const text = document.createElement('div');
    const name = document.createElement('div');
    name.className = 'member-name';
    name.textContent = m.name;
    const sub = document.createElement('div');
    sub.className = 'member-sub';
    sub.textContent = m.group || 'عضو مسجد';
    text.append(name,sub);
    info.append(avatar,text);
    const right = document.createElement('div');
    right.style.textAlign = 'left';
    const points = document.createElement('div');
    points.className = 'points';
    points.textContent = fa(m.points) + ' امتیاز';
    const view = document.createElement('button');
    view.className = 'btn small';
    view.textContent = 'پروفایل';
    view.onclick = () => openProfile(m.id);
    right.append(points,view);
    item.append(info,right);
    box.append(item);
  });
}

function renderRanking() {
  const members = [...activeMembers()].sort((a,b) => Number(b.points||0)-Number(a.points||0));
  const body = document.getElementById('rankingBody');
  body.innerHTML = '';
  if (!members.length) {
    body.innerHTML = '<tr><td colspan="4" class="empty">هنوز عضوی ثبت نشده است.</td></tr>';
    return;
  }
  members.forEach((m,i) => {
    const tr = document.createElement('tr');
    [fa(i+1),m.name,fa(m.points)].forEach(value => {
      const td = document.createElement('td');
      td.textContent = value;
      tr.append(td);
    });
    const td = document.createElement('td');
    const btn = document.createElement('button');
    btn.className = 'btn small';
    btn.textContent = 'مشاهده';
    btn.onclick = () => openProfile(m.id);
    td.append(btn);tr.append(td);body.append(tr);
  });
}

function fillMemberSelects() {
  const selects = ['profileSelect','pointMember','attendanceMember'];
  selects.forEach(id => {
    const el = document.getElementById(id);
    const old = el.value;
    el.innerHTML = '';
    const first = document.createElement('option');
    first.value = '';
    first.textContent = 'انتخاب عضو';
    el.append(first);
    activeMembers().forEach(m => {
      const option = document.createElement('option');
      option.value = m.id;
      option.textContent = m.name;
      el.append(option);
    });
    if ([...el.options].some(o => o.value === old)) el.value = old;
  });
}

function renderProfile() {
  const id = document.getElementById('profileSelect').value;
  const box = document.getElementById('profileContent');
  const member = appData.members.find(m => String(m.id) === String(id));
  if (!member) {
    box.textContent = 'یک عضو را انتخاب کن.';
    box.className = 'empty';
    return;
  }
  box.className = '';
  box.innerHTML = '';
  const head = document.createElement('div');
  head.className = 'profile-head';
  const avatar = document.createElement('div');
  avatar.className = 'avatar';
  avatar.textContent = String(member.name).charAt(0);
  const details = document.createElement('div');
  const name = document.createElement('h3');
  name.textContent = member.name;
  const points = document.createElement('div');
  points.className = 'points';
  points.textContent = fa(member.points) + ' امتیاز';
  details.append(name,points);head.append(avatar,details);box.append(head);

  const pointTitle = document.createElement('h4');
  pointTitle.textContent = 'تاریخچه امتیازات';
  box.append(pointTitle);
  const pointRows = appData.points.filter(p => String(p.memberId) === String(id)).slice().reverse();
  appendHistory(box,pointRows,p => `${Number(p.delta)>0?'+':''}${fa(p.delta)} امتیاز — ${p.reason || 'بدون توضیح'} — ${p.date || ''}`);

  const attendanceTitle = document.createElement('h4');
  attendanceTitle.textContent = 'تاریخچه حضور و غیاب';
  box.append(attendanceTitle);
  const attendanceRows = appData.attendance.filter(a => String(a.memberId) === String(id)).slice().reverse();
  appendHistory(box,attendanceRows,a => `${a.status} — ${a.date || ''} ${a.note || ''}`);
}

function appendHistory(box,rows,formatter) {
  if (!rows.length) {
    const empty = document.createElement('div');
    empty.className = 'empty';
    empty.textContent = 'سابقه‌ای ثبت نشده است.';
    box.append(empty);return;
  }
  rows.forEach(row => {
    const item = document.createElement('div');
    item.className = 'member-sub';
    item.style.padding = '11px 0';
    item.style.borderBottom = '1px solid var(--line)';
    item.textContent = formatter(row);
    box.append(item);
  });
}

function renderDashboard() {
  const top = [...activeMembers()].sort((a,b) => Number(b.points||0)-Number(a.points||0)).slice(0,5);
  const box = document.getElementById('topMembers');
  box.innerHTML = '';
  if (!top.length) box.innerHTML = '<div class="empty">هنوز اطلاعاتی متصل نشده است.</div>';
  top.forEach((m,i) => {
    const item = document.createElement('div');
    item.className = 'member';
    const name = document.createElement('span');
    name.textContent = `${fa(i+1)}. ${m.name}`;
    const points = document.createElement('strong');
    points.className = 'points';
    points.textContent = fa(m.points);
    item.append(name,points);box.append(item);
  });

  const recent = document.getElementById('recentPoints');
  recent.innerHTML = '';
  const rows = appData.points.slice(-5).reverse();
  if (!rows.length) recent.textContent = 'تغییری ثبت نشده است.';
  rows.forEach(p => {
    const div = document.createElement('div');
    div.className = 'member-sub';
    div.style.padding = '8px 0';
    div.textContent = `${memberName(p.memberId)}: ${Number(p.delta)>0?'+':''}${fa(p.delta)} — ${p.reason || ''}`;
    recent.append(div);
  });
}

function renderAll() {
  renderStats();
  renderMembers();
  renderRanking();
  renderDashboard();
  fillMemberSelects();
  renderProfile();
}

function requireApi() {
  if (!API_URL) {
    toast('اتصال سرور هنوز تنظیم نشده؛ مرحله اتصال را بعداً انجام می‌دهیم.');
    return false;
  }
  return true;
}

/*
 * توابع زیر بعد از آماده شدن نسخه امن سرور تکمیل می‌شوند.
 * هیچ داده‌ای در این نسخه به‌صورت محلی یا آزمایشی ذخیره نمی‌شود.
 */
function loginAdmin() {
  if (!requireApi()) return;
  toast('اتصال امن ورود مدیر در مرحله راه‌اندازی سرور فعال می‌شود.');
}

function logoutAdmin() {
  adminToken = '';
  document.getElementById('adminPanel').hidden = true;
  document.getElementById('loginCard').hidden = false;
}

function adminAction(action) {
  if (!requireApi()) return;
  toast('ابتدا اتصال امن سرور باید تکمیل شود.');
}

function changePassword() {
  if (!requireApi()) return;
  toast('تغییر رمز پس از اتصال سرور فعال می‌شود.');
}

renderAll();
</script>
</body>
</html>
