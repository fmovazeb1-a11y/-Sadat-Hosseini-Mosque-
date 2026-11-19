# -Sadat-Hosseini-Mosque-


<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#101c36">
<title>مسجد سادات حسینی | سامانه اعضا</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;600;700;800;900&display=swap');

:root{
 --bg:#0b1224;
 --panel:#121e37;
 --panel2:#192847;
 --blue:#3185ff;
 --cyan:#39d5dc;
 --white:#f5f8ff;
 --muted:#94a4c1;
 --line:#ffffff12;
 --green:#32d69a;
 --red:#ff647c;
 --gold:#ffc85b;
}

*{box-sizing:border-box}

body{
 margin:0;
 background:var(--bg);
 color:var(--white);
 font-family:'Vazirmatn',Tahoma,sans-serif;
 min-height:100vh;
 overflow-x:hidden;
}

body:before{
 content:"";
 position:fixed;
 width:450px;height:450px;
 background:#176bff20;
 filter:blur(110px);
 top:-180px;right:-130px;
 pointer-events:none;
 z-index:-1;
}

body:after{
 content:"";
 position:fixed;
 width:350px;height:350px;
 background:#12d5d020;
 filter:blur(100px);
 bottom:-160px;left:-100px;
 pointer-events:none;
 z-index:-1;
}

*{scroll-behavior:smooth}

button,input,select{
 font-family:inherit;
}

button{cursor:pointer}

.container{
 max-width:1150px;
 margin:auto;
 padding:0 18px;
}

header{
 padding:27px 0 18px;
 background:linear-gradient(130deg,#111d39,#17376c);
 border-bottom:1px solid var(--line);
 position:relative;
 overflow:hidden;
}

header:after{
 content:"";
 position:absolute;
 width:250px;height:250px;
 border:1px solid #ffffff12;
 border-radius:50%;
 left:-80px;top:-130px;
 box-shadow:0 0 0 35px #ffffff06,0 0 0 70px #ffffff04;
}

.top{
 display:flex;
 align-items:center;
 justify-content:space-between;
 gap:15px;
 flex-wrap:wrap;
 position:relative;
 z-index:1;
}

.brand{
 display:flex;
 align-items:center;
 gap:14px;
}

.logo{
 width:58px;height:58px;
 display:grid;
 place-items:center;
 border-radius:18px;
 background:linear-gradient(135deg,var(--blue),var(--cyan));
 font-size:28px;
 box-shadow:0 8px 30px #3185ff55;
}

.brand h1{
 margin:0;
 font-size:clamp(21px,4vw,30px);
 font-weight:900;
}

.brand p{
 margin:4px 0 0;
 color:#c0d3f5;
 font-size:12px;
}

.status{
 border:1px solid #ffffff25;
 background:#ffffff0d;
 padding:9px 14px;
 border-radius:30px;
 font-size:12px;
 color:#dceaff;
}

.status i{
 display:inline-block;
 width:8px;height:8px;
 border-radius:50%;
 background:var(--gold);
 margin-left:7px;
}

nav{
 display:flex;
 gap:8px;
 overflow-x:auto;
 padding:22px 0 0;
 scrollbar-width:none;
 position:relative;
 z-index:2;
}

nav button{
 border:1px solid transparent;
 background:#ffffff0c;
 color:#d2def3;
 padding:10px 17px;
 border-radius:12px;
 white-space:nowrap;
 transition:.25s;
 font-size:13px;
}

nav button:hover{
 background:#ffffff18;
 transform:translateY(-2px);
}

nav button.active{
 color:white;
 background:linear-gradient(120deg,#2875ec,#2560c4);
 box-shadow:0 5px 20px #2875ec40;
}

main{
 padding-top:27px;
 padding-bottom:45px;
}

.page{
 animation:pageIn .45s ease both;
}

@keyframes pageIn{
 from{opacity:0;transform:translateY(15px)}
 to{opacity:1;transform:translateY(0)}
}

.hero{
 background:linear-gradient(115deg,#1a3970,#174d7b 65%,#116b76);
 border:1px solid #ffffff18;
 border-radius:23px;
 padding:25px;
 margin-bottom:20px;
 position:relative;
 overflow:hidden;
}

.hero:after{
 content:"✦";
 position:absolute;
 font-size:160px;
 color:#ffffff0b;
 left:30px;top:-50px;
 transform:rotate(20deg);
}

.hero h2{
 font-size:23px;
 margin:0 0 7px;
 position:relative;
 z-index:1;
}

.hero p{
 color:#d2e5ff;
 font-size:13px;
 margin:0;
 position:relative;
 z-index:1;
}

.grid{
 display:grid;
 grid-template-columns:repeat(4,1fr);
 gap:13px;
}

.card{
 background:linear-gradient(145deg,#162440,#111c33);
 border:1px solid var(--line);
 border-radius:19px;
 padding:19px;
 box-shadow:0 12px 30px #00000018;
 transition:.25s;
}

.card:hover{
 transform:translateY(-3px);
 border-color:#ffffff27;
}

.stat{
 position:relative;
 overflow:hidden;
}

.stat:after{
 content:"";
 position:absolute;
 width:90px;height:90px;
 border-radius:50%;
 background:#3185ff12;
 left:-30px;bottom:-40px;
}

.stat small{
 color:var(--muted);
 font-size:12px;
}

.stat strong{
 display:block;
 font-size:30px;
 margin-top:9px;
 color:white;
}

.stat .symbol{
 font-size:20px;
 color:var(--cyan);
}

.section{
 margin-top:19px;
}

.section-title{
 display:flex;
 align-items:center;
 justify-content:space-between;
 gap:10px;
 margin-bottom:13px;
}

.section-title h2,.card h2{
 margin:0;
 font-size:18px;
}

.muted{
 color:var(--muted);
 font-size:12px;
}

.table-wrap{
 overflow-x:auto;
}

table{
 width:100%;
 border-collapse:collapse;
 min-width:350px;
 font-size:13px;
}

th,td{
 text-align:right;
 padding:13px 9px;
 border-bottom:1px solid var(--line);
}

th{
 color:var(--muted);
 font-weight:500;
}

tr:last-child td{border-bottom:0}

tr{
 transition:.2s;
}

tbody tr:hover{
 background:#ffffff08;
}

.rank{
 display:inline-grid;
 place-items:center;
 width:29px;height:29px;
 border-radius:9px;
 background:#ffffff0e;
}

.rank.first{
 background:#ffc85b20;
 color:var(--gold);
}

.badge{
 display:inline-block;
 padding:4px 9px;
 border-radius:20px;
 font-size:11px;
 background:#3185ff20;
 color:#8dbbff;
}

.badge.green{
 background:#32d69a18;
 color:var(--green);
}

.badge.red{
 background:#ff647c18;
 color:var(--red);
}

.btn{
 border:0;
 padding:10px 15px;
 border-radius:11px;
 background:linear-gradient(120deg,#2875ec,#1e5fca);
 color:white;
 font-size:13px;
 font-weight:700;
 transition:.2s;
}

.btn:hover{
 transform:translateY(-2px);
 filter:brightness(1.12);
}

.btn.secondary{
 background:#ffffff12;
 color:white;
 border:1px solid var(--line);
}

.btn.danger{
 background:#b93852;
}

.btn.green{
 background:#159b75;
}

.actions{
 display:flex;
 gap:8px;
 flex-wrap:wrap;
 margin-top:15px;
}

.field{
 margin-bottom:13px;
}

.field label{
 display:block;
 font-size:12px;
 color:#bdcbe3;
 margin-bottom:6px;
}

input,select{
 width:100%;
 padding:12px;
 background:#0d1830;
 border:1px solid #ffffff20;
 border-radius:11px;
 color:white;
 outline:none;
 font-size:13px;
}

input:focus,select:focus{
 border-color:var(--blue);
 box-shadow:0 0 0 3px #3185ff18;
}

select option{background:#121e37}

.formgrid{
 display:grid;
 grid-template-columns:repeat(2,minmax(0,1fr));
 gap:12px;
}

.empty{
 padding:30px 10px;
 text-align:center;
 color:var(--muted);
 font-size:13px;
}

.member-card{
 display:flex;
 align-items:center;
 gap:13px;
}

.avatar{
 width:43px;height:43px;
 flex-shrink:0;
 display:grid;
 place-items:center;
 border-radius:14px;
 background:linear-gradient(135deg,#2875ec,#27b8c4);
 font-size:19px;
 font-weight:800;
}

.notice{
 padding:13px 15px;
 background:#ffc85b12;
 border:1px solid #ffc85b25;
 border-radius:13px;
 color:#f5d998;
 font-size:12px;
 line-height:2;
 margin-bottom:17px;
}

.hidden{display:none!important}

footer{
 border-top:1px solid var(--line);
 padding:23px 12px;
 text-align:center;
 color:var(--muted);
 font-size:12px;
}

footer strong{
 color:#78aaff;
}

.toast{
 position:fixed;
 bottom:22px;
 right:50%;
 transform:translate(50%,20px);
 background:#1b3155;
 border:1px solid #ffffff22;
 color:white;
 padding:12px 20px;
 border-radius:13px;
 opacity:0;
 pointer-events:none;
 transition:.3s;
 z-index:20;
 font-size:13px;
 box-shadow:0 10px 30px #0005;
}

.toast.show{
 opacity:1;
 transform:translate(50%,0);
}

@media(max-width:760px){
 .grid{grid-template-columns:repeat(2,1fr)}
 .hero{padding:20px}
 .hero h2{font-size:19px}
 .card{padding:15px}
 .brand{gap:10px}
 .logo{width:48px;height:48px}
}

@media(max-width:420px){
 .formgrid{grid-template-columns:1fr}
 .status{font-size:10px}
 .stat strong{font-size:25px}
}
</style>
</head>

<body>

<header>
 <div class="container">
  <div class="top">
   <div class="brand">
    <div class="logo">م</div>
    <div>
     <h1>مسجد سادات حسینی</h1>
     <p>سامانه هوشمند اعضا، حضور و غیاب و امتیازات</p>
    </div>
   </div>
   <div class="status">
    <i></i> نسخه پایه - آماده توسعه
   </div>
  </div>

  <nav id="tabs">
   <button class="active" data-page="home">⌂ داشبورد</button>
   <button data-page="members">♙ اعضا</button>
   <button data-page="ranking">★ رتبه‌بندی</button>
   <button data-page="attendance">◷ حضور و غیاب</button>
   <button data-page="history">▤ تاریخچه</button>
   <button data-page="manage">⚙ مدیریت</button>
  </nav>
 </div>
</header>

<main class="container">

 <div class="notice">
  این نسخه، پایه نمایشی سامانه است. اطلاعات فعلاً فقط در حافظه همین مرورگر ذخیره می‌شوند؛ برای استفاده واقعی و مشترک اعضا باید دیتابیس و احراز هویت امن متصل شود.
 </div>

 <!-- DASHBOARD -->
 <section class="page" id="home">
  <div class="hero">
   <h2>به سامانه مسجد سادات حسینی خوش آمدید</h2>
   <p>مدیریت اعضا، ثبت فعالیت‌ها و مشاهده عملکرد در یک محیط یکپارچه</p>
  </div>

  <div class="grid">
   <div class="card stat">
    <small>تعداد اعضا</small>
    <strong id="totalMembers">۰</strong>
    <span class="symbol">♙</span>
   </div>
   <div class="card stat">
    <small>حاضرین آخرین جلسه</small>
    <strong id="totalPresent">۰</strong>
    <span class="symbol">✓</span>
   </div>
   <div class="card stat">
    <small>مجموع امتیازات</small>
    <strong id="totalPoints">۰</strong>
    <span class="symbol">★</span>
   </div>
   <div class="card stat">
    <small>تعداد سوابق ثبت‌شده</small>
    <strong id="totalHistory">۰</strong>
    <span class="symbol">▤</span>
   </div>
  </div>

  <div class="section card">
   <div class="section-title">
    <h2>برترین اعضا</h2>
    <span class="muted">رتبه‌بندی امتیازات</span>
   </div>
   <div id="topMembers"></div>
  </div>
 </section>

 <!-- MEMBERS -->
 <section class="page hidden" id="members">
  <div class="card">
   <div class="section-title">
    <h2>فهرست اعضا</h2>
    <span class="muted" id="memberCount">۰ عضو</span>
   </div>
   <div class="field">
    <input id="searchMember" placeholder="جست‌وجوی نام عضو...">
   </div>
   <div id="membersList"></div>
  </div>
 </section>

 <!-- RANKING -->
 <section class="page hidden" id="ranking">
  <div class="card">
   <div class="section-title">
    <h2>جدول رتبه‌بندی</h2>
    <span class="muted">بر اساس مجموع امتیاز</span>
   </div>
   <div id="rankingList"></div>
  </div>
 </section>

 <!-- ATTENDANCE -->
 <section class="page hidden" id="attendance">
  <div class="card">
   <div class="section-title">
    <h2>سوابق حضور و غیاب</h2>
   </div>
   <div id="attendanceList"></div>
  </div>
 </section>

 <!-- HISTORY -->
 <section class="page hidden" id="history">
  <div class="card">
   <div class="section-title">
    <h2>تاریخچه فعالیت‌ها</h2>
    <span class="muted">تغییر امتیاز و حضور</span>
   </div>
   <div id="historyList"></div>
  </div>
 </section>

 <!-- MANAGEMENT -->
 <section class="page hidden" id="manage">
  <div class="card">
   <h2>پنل مدیریت آزمایشی</h2>
   <p class="muted">این بخش فعلاً برای آزمایش عملکرد سایت است و هنوز قفل امنیتی واقعی ندارد.</p>
  </div>

  <div class="section card">
   <h2>افزودن عضو جدید</h2>
   <div class="formgrid">
    <div class="field">
     <label>نام و نام خانوادگی</label>
     <input id="newName" placeholder="نام عضو">
    </div>
    <div class="field">
     <label>امتیاز اولیه</label>
     <input id="newScore" type="number" value="0">
    </div>
   </div>
   <button class="btn green" id="addMember">+ افزودن عضو</button>
  </div>

  <div class="section card">
   <h2>ثبت حضور و غیاب</h2>
   <div class="formgrid">
    <div class="field">
     <label>انتخاب عضو</label>
     <select id="attendanceMember"></select>
    </div>
    <div class="field">
     <label>وضعیت حضور</label>
     <select id="attendanceStatus">
      <option>حاضر</option>
      <option>غایب</option>
      <option>با اجازه</option>
     </select>
    </div>
    <div class="field">
     <label>تاریخ جلسه</label>
     <input id="attendanceDate" type="date">
    </div>
   </div>
   <button class="btn green" id="saveAttendance">ثبت وضعیت</button>
  </div>

  <div class="section card">
   <h2>تغییر امتیاز عضو</h2>
   <div class="formgrid">
    <div class="field">
     <label>انتخاب عضو</label>
     <select id="scoreMember"></select>
    </div>
    <div class="field">
     <label>مقدار تغییر</label>
     <input id="scoreChange" type="number" placeholder="مثلاً ۵ یا ۳-">
    </div>
   </div>
   <div class="field">
    <label>دلیل تغییر امتیاز</label>
    <input id="scoreReason" placeholder="مثلاً همکاری در برنامه">
   </div>
   <button class="btn green" id="saveScore">ثبت تغییر امتیاز</button>
  </div>

  <div class="section card">
   <h2>حذف عضو</h2>
   <div class="field">
    <label>انتخاب عضو</label>
    <select id="removeMember"></select>
   </div>
   <button class="btn danger" id="deleteMember">حذف عضو</button>
  </div>
 </section>

</main>

<footer>
 مسجد سادات حسینی
 <br>
 طراحی و توسعه توسط <strong>گروهک سپیدار</strong>
</footer>

<div class="toast" id="toast"></div>

<script>
const $ = id => document.getElementById(id);

const STORAGE_KEY = "sep_idar_mosque_v1";

let data = {members:[],history:[]};

try{
 const saved = JSON.parse(localStorage.getItem(STORAGE_KEY));
 if(saved && Array.isArray(saved.members) && Array.isArray(saved.history)){
  data = saved;
 }
}catch(e){}

const fa = n => Number(n || 0).toLocaleString("fa-IR");

const safe = value => String(value).replace(/[&<>"']/g, c => ({
 "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"
})[c]);

function notify(message){
 $("toast").textContent = message;
 $("toast").classList.add("show");
 setTimeout(()=>$("toast").classList.remove("show"),2300);
}

function save(){
 localStorage.setItem(STORAGE_KEY,JSON.stringify(data));
 render();
}

function dateNow(){
 return new Date().toLocaleString("fa-IR");
}

function dateInput(){
 const d = new Date();
 return [
  d.getFullYear(),
  String(d.getMonth()+1).padStart(2,"0"),
  String(d.getDate()).padStart(2,"0")
 ].join("-");
}

function record(type,member,details){
 data.history.unshift({
  type,
  name:member.name,
  details,
  date:dateNow()
 });
}

function table(rows,headers){
 if(!rows.length) return '<div class="empty">هنوز اطلاعاتی ثبت نشده است.</div>';

 return `<div class="table-wrap">
 <table>
 <thead><tr>${headers.map(h=>`<th>${h}</th>`).join("")}</tr></thead>
 <tbody>${rows.join("")}</tbody>
 </table></div>`;
}

function fillSelect(id){
 const el=$(id);
 const old=el.value;
 el.innerHTML=data.members.map(m=>
  `<option value="${m.id}">${safe(m.name)}</option>`
 ).join("");
 if(data.members.some(m=>String(m.id)===old)) el.value=old;
}

function render(){
 const members=data.members;
 const sorted=[...members].sort((a,b)=>b.points-a.points);

 $("totalMembers").textContent=fa(members.length);
 $("totalPoints").textContent=fa(members.reduce((s,m)=>s+m.points,0));
 $("totalHistory").textContent=fa(data.history.length);

 const lastAttendance=data.history.filter(h=>h.type==="حضور و غیاب");
 const lastDate=lastAttendance[0]?.date;
 const lastMeeting=lastDate?lastAttendance.filter(h=>h.date===lastDate):[];
 $("totalPresent").textContent=fa(lastMeeting.filter(h=>h.details==="حاضر").length);

 $("topMembers").innerHTML=table(
  sorted.slice(0,5).map((m,i)=>`
   <tr>
    <td><span class="rank ${i===0?"first":""}">${fa(i+1)}</span></td>
    <td>${safe(m.name)}</td>
    <td><span class="badge">${fa(m.points)} امتیاز</span></td>
   </tr>
  `),
  ["رتبه","نام عضو","امتیاز"]
 );

 $("memberCount").textContent=fa(members.length)+" عضو";

 const search=$("searchMember").value.trim().toLowerCase();
 const filtered=members.filter(m=>m.name.toLowerCase().includes(search));

 $("membersList").innerHTML=filtered.length?
 filtered.map(m=>`
  <div class="card" style="margin-bottom:10px">
   <div class="member-card">
    <div class="avatar">${safe(m.name.slice(0,1))}</div>
    <div style="flex:1">
     <strong>${safe(m.name)}</strong>
     <div class="muted">${fa(m.points)} امتیاز</div>
    </div>
    <span class="badge">عضو</span>
   </div>
  </div>
 `).join(""):'<div class="empty">عضوی پیدا نشد.</div>';

 $("rankingList").innerHTML=table(
  sorted.map((m,i)=>`
   <tr>
    <td><span class="rank ${i===0?"first":""}">${fa(i+1)}</span></td>
    <td>${safe(m.name)}</td>
    <td>${fa(m.points)}</td>
   </tr>
  `),
  ["رتبه","نام عضو","امتیاز"]
 );

 const attendance=data.history.filter(h=>h.type==="حضور و غیاب");
 $("attendanceList").innerHTML=table(
  attendance.map(h=>`
   <tr>
    <td>${safe(h.name)}</td>
    <td><span class="badge ${h.details==="حاضر"?"green":h.details==="غایب"?"red":""}">${safe(h.details)}</span></td>
    <td>${safe(h.date)}</td>
   </tr>
  `),
  ["عضو","وضعیت","زمان ثبت"]
 );

 $("historyList").innerHTML=table(
  data.history.map(h=>`
   <tr>
    <td>${safe(h.name)}</td>
    <td>${safe(h.type)}</td>
    <td>${safe(h.details)}</td>
    <td>${safe(h.date)}</td>
   </tr>
  `),
  ["عضو","نوع فعالیت","جزئیات","زمان"]
 );

 ["attendanceMember","scoreMember","removeMember"].forEach(fillSelect);
}

$("tabs").addEventListener("click",e=>{
 const btn=e.target.closest("button[data-page]");
 if(!btn)return;

 document.querySelectorAll("nav button").forEach(b=>
  b.classList.toggle("active",b===btn)
 );

 document.querySelectorAll(".page").forEach(p=>
  p.classList.toggle("hidden",p.id!==btn.dataset.page)
 );
});

$("addMember").onclick=()=>{
 const name=$("newName").value.trim();
 const points=Number($("newScore").value);

 if(!name)return notify("نام عضو را وارد کن.");
 if(!Number.isFinite(points))return notify("امتیاز معتبر نیست.");
 if(data.members.some(m=>m.name===name))return notify("این عضو قبلاً ثبت شده است.");

 const member={
  id:Date.now()+Math.random(),
  name,
  points,
 };

 data.members.push(member);
 record("افزودن عضو",member,"عضو جدید اضافه شد");
 $("newName").value="";
 $("newScore").value="0";
 save();
 notify("عضو با موفقیت اضافه شد.");
};

$("saveAttendance").onclick=()=>{
 const member=data.members.find(m=>String(m.id)===$("attendanceMember").value);
 if(!member)return notify("ابتدا یک عضو اضافه کن.");

 const status=$("attendanceStatus").value;
 const date=$("attendanceDate").value;

 if(!date)return notify("تاریخ جلسه را انتخاب کن.");

 data.history.unshift({
  type:"حضور و غیاب",
  name:member.name,
  details:status,
  date:new Date(date+"T12:00:00").toLocaleDateString("fa-IR")
 });

 save();
 notify("حضور و غیاب ثبت شد.");
};

$("saveScore").onclick=()=>{
 const member=data.members.find(m=>String(m.id)===$("scoreMember").value);
 const change=Number($("scoreChange").value);
 const reason=$("scoreReason").value.trim();

 if(!member)return notify("عضو انتخاب نشده است.");
 if(!Number.isFinite(change)||change===0)return notify("مقدار تغییر را وارد کن.");
 if(!reason)return notify("دلیل تغییر امتیاز را بنویس.");
 if(member.points+change<0)return notify("امتیاز نمی‌تواند منفی شود.");

 member.points+=change;

 record(
  "تغییر امتیاز",
  member,
  (change>0?"+":"")+fa(change)+" | "+reason
 );

 $("scoreChange").value="";
 $("scoreReason").value="";
 save();
 notify("امتیاز به‌روزرسانی شد.");
};

$("deleteMember").onclick=()=>{
 const member=data.members.find(m=>String(m.id)===$("removeMember").value);
 if(!member)return notify("عضوی انتخاب نشده است.");

 if(!confirm("عضو "+member.name+" حذف شود؟"))return;

 data.members=data.members.filter(m=>m.id!==member.id);
 record("حذف عضو",member,"عضو از فهرست حذف شد");
 save();
 notify("عضو حذف شد.");
};

$("searchMember").addEventListener("input",render);

$("attendanceDate").value=dateInput();

render();
</script>

</body>
</html>
