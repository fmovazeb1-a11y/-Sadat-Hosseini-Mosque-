# -Sadat-Hosseini-Mosque-

<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>مسجد سادات حسینی</title>

<style>
*{box-sizing:border-box}
body{
 margin:0;
 font-family:Tahoma,sans-serif;
 background:#f1f5f8;
 color:#172b3a;
}
body:before{
 content:"مسجد سادات حسینی     مسجد سادات حسینی     مسجد سادات حسینی";
 position:fixed;
 inset:0;
 z-index:-1;
 opacity:.035;
 font-size:25px;
 line-height:5;
 transform:rotate(-15deg);
 pointer-events:none;
}
header{
 background:#102b3f;
 color:white;
 padding:25px 15px;
 text-align:center;
}
header h1{margin:0}
header p{color:#c8dce7}
nav{
 display:flex;
 justify-content:center;
 flex-wrap:wrap;
 gap:8px;
 padding:15px;
}
button{
 border:0;
 border-radius:9px;
 padding:11px 15px;
 cursor:pointer;
 font-family:inherit;
}
nav button{background:#dce8ee;color:#102b3f}
nav button.active,.primary{background:#176b87;color:white}
main{max-width:1000px;margin:auto;padding:15px}
.card{
 background:white;
 border:1px solid #e1e9ed;
 border-radius:15px;
 padding:18px;
 margin-bottom:15px;
}
.stats{
 display:grid;
 grid-template-columns:repeat(auto-fit,minmax(150px,1fr));
 gap:12px;
}
.stat strong{display:block;font-size:27px;color:#176b87}
.muted{color:#71818c;font-size:13px}
table{width:100%;border-collapse:collapse}
td,th{text-align:right;padding:12px 8px;border-bottom:1px solid #e5ecef}
input,select{
 width:100%;
 padding:12px;
 border:1px solid #dce5e9;
 border-radius:9px;
 font-family:inherit;
 margin:5px 0 12px;
}
.hidden{display:none}
.profile{
 cursor:pointer;
 color:#176b87;
 font-weight:bold;
}
.badge{
 display:inline-block;
 padding:4px 9px;
 border-radius:20px;
 background:#e5f3ef;
 color:#19745e;
 font-size:12px;
}
footer{text-align:center;padding:25px;color:#71818c;font-size:12px}
</style>
</head>

<body>

<header>
<h1>مسجد سادات حسینی</h1>
<p>سامانه مدیریت اعضا، حضور و غیاب و امتیازات</p>
</header>

<nav>
<button class="active" onclick="showPage('home',this)">داشبورد</button>
<button onclick="showPage('members',this)">اعضا</button>
<button onclick="showPage('ranking',this)">رتبه‌بندی</button>
<button onclick="showPage('attendance',this)">حضور و غیاب</button>
<button onclick="showPage('admin',this)">مدیریت</button>
</nav>

<main>

<section id="home">
<div class="stats">
<div class="card">تعداد اعضا<strong id="totalMembers">۰</strong></div>
<div class="card">مجموع امتیازات<strong id="totalPoints">۰</strong></div>
<div class="card">حاضرین<strong id="presentCount">۰</strong></div>
</div>
<div class="card">
<h3>سامانه مسجد سادات حسینی</h3>
<p>برای مشاهده سوابق هر عضو، وارد بخش اعضا شو و روی نام او بزن.</p>
</div>
</section>

<section id="members" class="hidden">
<div class="card">
<h2>فهرست اعضا</h2>
<div id="memberList"></div>
</div>
</section>

<section id="profile" class="hidden">
<div class="card">
<button onclick="showPage('members')">بازگشت به اعضا</button>
<h2 id="profileName"></h2>
<div class="stats">
<div class="card">امتیاز کل<strong id="profilePoints"></strong></div>
<div class="card">آخرین وضعیت<strong id="profileAttendance"></strong></div>
</div>
<h3>تاریخچه امتیازات</h3>
<div id="profileHistory"></div>
<h3>تاریخچه حضور و غیاب</h3>
<div id="profileAttendanceHistory"></div>
</div>
</section>

<section id="ranking" class="hidden">
<div class="card">
<h2>رتبه‌بندی اعضا</h2>
<div id="rankingList"></div>
</div>
</section>

<section id="attendance" class="hidden">
<div class="card">
<h2>وضعیت حضور و غیاب</h2>
<div id="attendanceList"></div>
</div>
</section>

<section id="admin" class="hidden">
<div class="card" id="loginBox">
<h2>ورود مدیریت</h2>
<input id="pin" type="password" maxlength="4" placeholder="رمز چهاررقمی">
<button class="primary" onclick="login()">ورود</button>
<p id="loginError"></p>
</div>

<div id="adminPanel" class="hidden">

<div class="card">
<h3>افزودن عضو</h3>
<input id="newName" placeholder="نام عضو">
<button class="primary" onclick="addMember()">افزودن</button>
</div>

<div class="card">
<h3>تغییر امتیاز</h3>
<select id="pointMember"></select>
<input id="pointAmount" type="number" placeholder="مقدار مثبت یا منفی">
<input id="pointReason" placeholder="دلیل تغییر امتیاز">
<button class="primary" onclick="changePoints()">ثبت امتیاز</button>
</div>

<div class="card">
<h3>ثبت حضور و غیاب</h3>
<select id="attendanceMember"></select>
<select id="attendanceStatus">
<option>حاضر</option>
<option>غایب</option>
<option>با اجازه</option>
</select>
<button class="primary" onclick="changeAttendance()">ثبت وضعیت</button>
</div>

<div class="card">
<h3>حذف عضو</h3>
<select id="removeMemberSelect"></select>
<button onclick="removeMember()">حذف عضو</button>
</div>

<button onclick="logout()">خروج از مدیریت</button>
</div>
</section>

</main>

<footer>ساخته شده توسط گروهک سپیدار</footer>

<script>
const ADMIN_PIN="1111";

let members=JSON.parse(
 localStorage.getItem("mosqueMembers")||"[]"
);

let isAdmin=false;

function persist(){
 localStorage.setItem("mosqueMembers",JSON.stringify(members));
 render();
}

function fa(n){
 return Number(n).toLocaleString("fa-IR");
}

function showPage(id,btn){
 document.querySelectorAll("main section").forEach(s=>s.classList.add("hidden"));
 document.getElementById(id).classList.remove("hidden");

 document.querySelectorAll("nav button").forEach(b=>b.classList.remove("active"));
 if(btn)btn.classList.add("active");
}

function login(){
 if(document.getElementById("pin").value===ADMIN_PIN){
  isAdmin=true;
  document.getElementById("loginBox").classList.add("hidden");
  document.getElementById("adminPanel").classList.remove("hidden");
 }else{
  document.getElementById("loginError").textContent="رمز اشتباه است.";
 }
}

function logout(){
 isAdmin=false;
 document.getElementById("adminPanel").classList.add("hidden");
 document.getElementById("loginBox").classList.remove("hidden");
 document.getElementById("pin").value="";
}

function addMember(){
 if(!isAdmin)return;
 const name=document.getElementById("newName").value.trim();
 if(!name)return alert("نام عضو را وارد کن.");

 members.push({
  id:Date.now(),
  name,
  points:0,
  attendance:"ثبت نشده",
  pointHistory:[],
  attendanceHistory:[]
 });

 document.getElementById("newName").value="";
 persist();
}

function changePoints(){
 if(!isAdmin)return;

 const id=Number(document.getElementById("pointMember").value);
 const amount=Number(document.getElementById("pointAmount").value);
 const reason=document.getElementById("pointReason").value.trim();

 const member=members.find(m=>m.id===id);
 if(!member||!amount||!reason)return alert("اطلاعات کامل نیست.");

 member.points+=amount;
 member.pointHistory.push({
  amount,
  reason,
  date:new Date().toLocaleString("fa-IR")
 });

 document.getElementById("pointAmount").value="";
 document.getElementById("pointReason").value="";
 persist();
}

function changeAttendance(){
 if(!isAdmin)return;

 const member=members.find(m=>m.id===Number(document.getElementById("attendanceMember").value));
 if(!member)return;

 const status=document.getElementById("attendanceStatus").value;
 member.attendance=status;

 member.attendanceHistory.push({
  status,
  date:new Date().toLocaleString("fa-IR")
 });

 persist();
}

function removeMember(){
 if(!isAdmin)return;
 const id=Number(document.getElementById("removeMemberSelect").value);
 const member=members.find(m=>m.id===id);
 if(!member)return;
 if(!confirm("این عضو حذف شود؟"))return;

 members=members.filter(m=>m.id!==id);
 persist();
}

function openProfile(id){
 const m=members.find(x=>x.id===id);
 if(!m)return;

 document.getElementById("profileName").textContent=m.name;
 document.getElementById("profilePoints").textContent=fa(m.points);
 document.getElementById("profileAttendance").textContent=m.attendance;

 document.getElementById("profileHistory").innerHTML=
 m.pointHistory.length?
 m.pointHistory.slice().reverse().map(h=>
 `<p>${h.amount>0?"+":""}${fa(h.amount)} امتیاز | ${h.reason}<br><small>${h.date}</small></p>`
 ).join(""):"<p>هنوز امتیازی ثبت نشده است.</p>";

 document.getElementById("profileAttendanceHistory").innerHTML=
 m.attendanceHistory.length?
 m.attendanceHistory.slice().reverse().map(h=>
 `<p>${h.status} — ${h.date}</p>`
 ).join(""):"<p>هنوز سابقه‌ای ثبت نشده است.</p>";

 showPage("profile");
}

function render(){
 const sorted=[...members].sort((a,b)=>b.points-a.points);

 document.getElementById("totalMembers").textContent=fa(members.length);
 document.getElementById("totalPoints").textContent=fa(members.reduce((s,m)=>s+m.points,0));
 document.getElementById("presentCount").textContent=fa(members.filter(m=>m.attendance==="حاضر").length);

 document.getElementById("memberList").innerHTML=
 members.length?members.map(m=>
 `<p><span class="profile" onclick="openProfile(${m.id})">${m.name}</span> <span class="badge">${fa(m.points)} امتیاز</span></p>`
 ).join(""):"هنوز عضوی ثبت نشده است.";

 document.getElementById("rankingList").innerHTML=
 sorted.map((m,i)=>`<p>${fa(i+1)}. ${m.name} — ${fa(m.points)} امتیاز</p>`).join("");

 document.getElementById("attendanceList").innerHTML=
 members.map(m=>`<p>${m.name} — ${m.attendance}</p>`).join("");

 ["pointMember","attendanceMember","removeMemberSelect"].forEach(id=>{
  document.getElementById(id).innerHTML=
  members.map(m=>`<option value="${m.id}">${m.name}</option>`).join("");
 });
}

render();
</script>
</body>
</html>
