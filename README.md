<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<title>صيدلية الدكتور هشام البلاصي</title>

<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;800&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Cairo',sans-serif}
body{background:#f4f8fb;color:#0f2929}

/* ===== NAVBAR ===== */
nav{
position:fixed;top:0;width:100%;z-index:1000;
background:#ffffffcc;backdrop-filter:blur(10px);
display:flex;justify-content:center;gap:30px;
padding:15px;box-shadow:0 5px 20px rgba(0,0,0,.05)
}
nav a{
text-decoration:none;color:#ff5722;font-weight:700;
padding:6px 16px;border-radius:10px
}
nav a:hover{background:#ff5722;color:#fff}

/* ===== HERO ===== */
.hero{
height:90vh;margin-top:70px;
background:linear-gradient(135deg,#ff5722,#ffca28);
display:flex;align-items:center;justify-content:center;
text-align:center;color:#fff;border-radius:0 0 40px 40px
}
.hero h1{font-size:48px}
.hero p{font-size:20px;margin-top:10px}

/* ===== SECTIONS ===== */
section{
padding:60px 8%;margin:50px auto;
background:#fff;border-radius:30px;
box-shadow:0 10px 30px rgba(0,0,0,.08)
}
h2{text-align:center;font-size:34px;margin-bottom:30px;color:#ff5722}

/* ===== SERVICES ===== */
.services{
display:grid;
grid-template-columns:repeat(auto-fill,minmax(220px,1fr));
gap:20px;
text-align:center;
}
.service-card{
background:white;padding:20px;border-radius:15px;
box-shadow:0 5px 15px rgba(0,0,0,.1);
transition:.3s;cursor:pointer;
}
.service-card:hover{transform:translateY(-6px)}
.service-card i{font-size:40px;color:#ff5722;margin-bottom:10px}
.service-card h3{margin-top:10px;color:#ff5722}

/* ===== SEARCH + CART ===== */
.search-cart{
display:flex;justify-content:center;gap:15px;
margin-bottom:30px;flex-wrap:wrap
}
.search-cart input{
padding:12px;width:260px;border-radius:10px;
border:1px solid #ccc
}
.cart-btn{
background:#ffca28;border:none;padding:12px 18px;
border-radius:10px;cursor:pointer;font-weight:700
}

/* ===== PRODUCTS ===== */
.products{
display:grid;
grid-template-columns:repeat(auto-fill,minmax(220px,1fr));
gap:20px
}
.card{
background:white;padding:15px;border-radius:15px;
box-shadow:0 5px 15px rgba(0,0,0,.1);
transition:.3s;text-align:center
}
.card:hover{transform:translateY(-6px)}
.card i{font-size:30px;color:#ff5722}
.card button{
margin-top:10px;width:100%;padding:10px;
border:none;background:#ff5722;color:white;
border-radius:8px;cursor:pointer
}
.price{color:green;font-weight:bold;margin:8px 0}

/* ===== CART ===== */
#cart{
position:fixed;top:0;left:-100%;
width:350px;height:100%;
background:white;z-index:999;
box-shadow:5px 0 20px rgba(0,0,0,.3);
padding:20px;transition:.4s;overflow:auto
}
.cart-item{
display:flex;justify-content:space-between;
border-bottom:1px solid #ddd;padding:8px 0
}
.total{font-weight:bold;color:#ff5722;margin-top:10px}
.close{
background:red;color:white;border:none;
padding:10px;width:100%;
border-radius:8px;margin-top:10px
}

/* ===== CONSULTATION ===== */
.consult-card{
max-width:600px;margin:auto
}
.consult-card input,
.consult-card textarea,
.consult-card select{
width:100%;padding:12px;margin:6px 0;
border-radius:10px;border:1px solid #ccc
}
.consult-card button{
width:100%;padding:12px;background:#ff5722;
color:white;border:none;border-radius:10px
}

/* ===== FOOTER ===== */
footer{
background:#ff5722;color:white;
text-align:center;padding:20px;
border-radius:25px;margin:40px
}

/* ===== EFFECTS ON PRESS ===== */
.card:active, .service-card:active, .card button:active{
    background-color: #e0e0e0; /* خلفية رمادية عند الضغط */
    box-shadow: none; /* إزالة الظل عند الضغط */
}

/* For smooth transition of background color */
.card, .service-card, .card button{
    transition: background-color 0.2s ease, box-shadow 0.2s ease;
}
</style>
</head>

<body>

<nav>
<a href="#home">الرئيسية</a>
<a href="#services">خدمات الصيدلية</a>
<a href="#medicines">الأدوية</a>
<a href="#consult">الاستشارات</a>
<a href="#contact">تواصل</a>
</nav>

<div class="hero" id="home">
<div>
<h1>صيدلية الدكتور هشام البلاصي</h1>
<p>رعاية صحية | أدوية أصلية | استشارات موثوقة</p>
</div>
</div>

<!-- CART -->
<div id="cart">
<h2>🛒 سلة الشراء</h2>
<div id="cartItems"></div>
<div class="total">الإجمالي: <span id="total">0</span> جنيه</div>
<button class="close" onclick="toggleCart()">إغلاق</button>
</div>

<!-- SERVICES -->
<section id="services">
<h2>🩹 خدمات الصيدلية</h2>
<div class="services">
<div class="service-card" onclick="scrollToSection('consult')">
<i class="fas fa-heartbeat"></i>
<h3>قياس الضغط والسكر</h3>
</div>
<div class="service-card" onclick="alert('قسم الأجهزة الطبية قريباً')">
<i class="fas fa-stethoscope"></i>
<h3>أجهزة طبية</h3>
</div>
<div class="service-card" onclick="alert('جميع الأدوية أصلية 100%')">
<i class="fas fa-pills"></i>
<h3>أدوية أصلية</h3>
</div>
<div class="service-card" onclick="alert('لوازم للطوارئ متوفرة')">
<i class="fas fa-first-aid"></i>
<h3>لوازم للطوارئ</h3>
</div>
<div class="service-card" onclick="scrollToSection('consult')">
<i class="fas fa-user-md"></i>
<h3>استشارات طبية</h3>
</div>
</div>
</section>

<!-- MEDICINES -->
<section id="medicines">
<h2>💊 الأدوية</h2>

<div class="search-cart">
<input type="text" id="search" placeholder="🔍 ابحث عن دواء">
<button class="cart-btn" onclick="toggleCart()">🛒 السلة (<span id="count">0</span>)</button>
</div>

<div class="products" id="products"></div>
</section>

<!-- CONSULT -->
<section id="consult">
<h2>👨‍⚕️ الاستشارات الطبية</h2>

<div class="card consult-card">
<p>أرسل استشارتك وسيتم الرد عليك من صيدلي مختص</p>

<input type="text" id="cname" placeholder="الاسم بالكامل">
<input type="text" id="cphone" placeholder="رقم الهاتف">

<select id="ctype">
<option>نوع الاستشارة</option>
<option>أدوية</option>
<option>أطفال</option>
<option>ضغط وسكر</option>
<option>نزلات برد</option>
<option>أخرى</option>
</select>

<textarea id="cmsg" rows="4" placeholder="اكتب استشارتك هنا..."></textarea>

<button onclick="sendConsultation()">📩 إرسال الاستشارة</button>
<p id="result" style="text-align:center;color:green"></p>
</div>
</section>

<section id="contact">
<h2>📞 تواصل معنا</h2>
<div class="card">01020541367</div>
</section>

<footer>
© 2026 صيدلية الدكتور هشام البلاصي – صحتك تهمنا 💙
</footer>

<script>
// === فئات الأدوية مع أيقونات ===
const categories = [
    {type:"مسكن", icon:"pills", list:["Panadol","Brufen","Novalgin","Voltaren","Aspirin"]},
    {type:"ضغط", icon:"capsules", list:["Enalapril","Losartan","Amlodipine","Captopril","Hydrochlorothiazide"]},
    {type:"سكر", icon:"prescription-bottle-medical", list:["Metformin","Glibenclamide","Insulin","Glimepiride","Sitagliptin"]},
    {type:"أخرى", icon:"syringe", list:["Augmentin","Clexane","Ventolin Syrup","Omeprazole","Cetirizine"]}
];

// توليد 500 دواء
let products = [];
for(let i=0;i<500;i++){
    let cat = categories[i % categories.length]; 
    let med = cat.list[i % cat.list.length]; 
    let name = `${med} ${Math.floor(i/20)+1}`; 
    let price = Math.floor(Math.random()*200)+20;
    products.push({n:name, p:price, i:cat.icon});
}

// === CART ===
let cart=[], total=0;

// عرض المنتجات
function renderProducts(){
    let box = document.getElementById("products");
    box.innerHTML="";
    products.forEach(x=>{
        box.innerHTML+=`
        <div class="card">
            <i class="fas fa-${x.i}"></i>
            <h3>${x.n}</h3>
            <div class="price">${x.p} جنيه</div>
            <button onclick="addToCart('${x.n}',${x.p})">➕ أضف للسلة</button>
        </div>`;
    });
}

// إضافة للسلة
function addToCart(n,p){
    cart.push({n,p}); 
    total+=p; 
    updateCart();
}

// تحديث السلة
function updateCart(){
    let box=document.getElementById("cartItems");
    box.innerHTML="";
    cart.forEach(c=>{
        box.innerHTML+=`
        <div class="cart-item">
            <span>${c.n}</span><span>${c.p}ج</span>
        </div>`;
    });
    document.getElementById("total").innerText = total;
    document.getElementById("count").innerText = cart.length;
}

// فتح وإغلاق السلة
function toggleCart(){
    let cartDiv = document.getElementById("cart");
    cartDiv.style.left = (cartDiv.style.left=="0px")?"-100%":"0px";
}

// البحث
document.getElementById("search").addEventListener("keyup",()=>{
    let v = document.getElementById("search").value.toLowerCase();
    document.querySelectorAll(".products .card").forEach(c=>{
        c.style.display = c.innerText.toLowerCase().includes(v) ? "block" : "none";
    });
});

// الاستشارة
function sendConsultation(){
    if(!cname.value||!cphone.value||!cmsg.value){
        alert("يرجى ملء جميع البيانات"); return;
    }
    result.innerText="✅ تم إرسال الاستشارة بنجاح";
    cname.value=cphone.value=cmsg.value="";
}

// تمرير إلى قسم الاستشارات
function scrollToSection(id){
    document.getElementById(id).scrollIntoView({behavior:"smooth"});
}

renderProducts();
</script>

</body>
</html>
