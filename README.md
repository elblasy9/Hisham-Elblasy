<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>صيدلية الدكتور هشام البلاصي</title>

    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; }
        body { background: #f4f8fb; color: #0f2929; }

        /* ===== NAVBAR ===== */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            background: #ffffffcc;
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: center;
            gap: 30px;
            padding: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, .05);
        }
        nav a {
            text-decoration: none;
            color: #1565c0;
            font-weight: 700;
            padding: 6px 16px;
            border-radius: 10px;
        }
        nav a:hover { background: #1565c0; color: #fff; }

        /* ===== HERO ===== */
        .hero {
            height: 90vh;
            margin-top: 70px;
            background: linear-gradient(135deg, #1565c0, #22d3ee);
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: #fff;
            border-radius: 0 0 40px 40px;
        }
        .hero h1 { font-size: 48px; }
        .hero p { font-size: 20px; margin-top: 10px; }

        /* ===== SECTIONS ===== */
        section {
            padding: 60px 8%;
            margin: 50px auto;
            background: #fff;
            border-radius: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, .08);
        }
        h2 { text-align: center; font-size: 34px; margin-bottom: 30px; color: #1565c0; }

        /* ===== SERVICES ===== */
        .services {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 20px;
            text-align: center;
        }
        .service-card {
            background: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, .1);
            transition: .3s;
            cursor: pointer;
        }
        .service-card:hover { transform: translateY(-6px); }
        .service-card i { font-size: 40px; color: #1565c0; margin-bottom: 10px; }
        .service-card h3 { margin-top: 10px; color: #1565c0; }

        /* ===== SEARCH + CART ===== */
        .search-cart {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }
        .search-cart input {
            padding: 12px;
            width: 260px;
            border-radius: 10px;
            border: 1px solid #ccc;
        }
        .cart-btn {
            background: #ffca28;
            border: none;
            padding: 12px 18px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 700;
        }

        /* ===== PRODUCTS ===== */
        .products {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 20px;
        }
        .card {
            background: white;
            padding: 15px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, .1);
            transition: .3s;
            text-align: center;
        }
        .card:hover { transform: translateY(-6px); }
        .card i { font-size: 30px; color: #1565c0; }
        .card button {
            margin-top: 10px;
            width: 100%;
            padding: 10px;
            border: none;
            background: #1565c0;
            color: white;
            border-radius: 8px;
            cursor: pointer;
        }
        .price { color: green; font-weight: bold; margin: 8px 0; }

        /* ===== CART ===== */
        #cart {
            position: fixed;
            top: 0;
            left: -100%;
            width: 350px;
            height: 100%;
            background: white;
            z-index: 999;
            box-shadow: 5px 0 20px rgba(0, 0, 0, .3);
            padding: 20px;
            transition: .4s;
            overflow: auto;
        }
        .cart-item {
            display: flex;
            justify-content: space-between;
            border-bottom: 1px solid #ddd;
            padding: 8px 0;
        }
        .total {
            font-weight: bold;
            color: #1565c0;
            margin-top: 10px;
        }
        .close {
            background: red;
            color: white;
            border: none;
            padding: 10px;
            width: 100%;
            border-radius: 8px;
            margin-top: 10px;
        }

        /* ===== CONSULTATION ===== */
        .consult-card {
            max-width: 600px;
            margin: auto;
        }
        .consult-card input,
        .consult-card textarea,
        .consult-card select {
            width: 100%;
            padding: 12px;
            margin: 6px 0;
            border-radius: 10px;
            border: 1px solid #ccc;
        }
        .consult-card button {
            width: 100%;
            padding: 12px;
            background: #1565c0;
            color: white;
            border: none;
            border-radius: 10px;
        }

        /* ===== FOOTER ===== */
        footer {
            background: #0d47a1;
            color: white;
            text-align: center;
            padding: 20px;
            border-radius: 25px;
            margin: 40px;
        }

        /* ===== ADMIN PANEL ===== */
        #admin-panel {
            display: none;
            background-color: #ffffff;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
            max-width: 800px;
            margin: auto;
            text-align: right;
        }
        #admin-panel input, #admin-panel select, #admin-panel textarea {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border-radius: 10px;
            border: 1px solid #ccc;
        }
        #admin-panel button {
            background: #1565c0;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
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
    <a href="#" onclick="openAdminPanel()">لوحة التحكم</a>
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
    <h2>🩺 خدمات الصيدلية</h2>
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
        <div class="service-card" onclick="alert('يمكنك مسح الرشوتة ضوئيًا عبر إرسال صورة')">
            <i class="fas fa-camera"></i>
            <h3>مسح ضوئي للرشوتة</h3>
        </div>
        <div class="service-card" onclick="alert('قريباً عروض و خصومات خاصة!')">
            <i class="fas fa-gift"></i>
            <h3>عروض و خصومات</h3>
        </div>
        <div class="service-card" onclick="alert('قريباً سيتم توفير خدمة العيانات الشخصية!')">
            <i class="fas fa-clinic-medical"></i>
            <h3>عناية شخصية</h3>
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

<!-- لوحة التحكم (Admin Panel) -->
<div id="admin-panel">
    <h2>لوحة التحكم</h2>
    <label for="med-name">اسم الدواء:</label>
    <input type="text" id="med-name" placeholder="أدخل اسم الدواء">

    <label for="med-price">السعر:</label>
    <input type="number" id="med-price" placeholder="أدخل سعر الدواء">

    <label for="med-category">فئة الدواء:</label>
    <select id="med-category">
        <option value="مسكن">مسكن</option>
        <option value="ضغط">ضغط</option>
        <option value="سكر">سكر</option>
        <option value="أخرى">أخرى</option>
    </select>

    <label for="med-type">نوع الدواء:</label>
    <select id="med-type">
        <option value="حقن">حقن</option>
        <option value="دواء شرب">دواء شرب</option>
        <option value="حبوب">حبوب</option>
    </select>

    <button onclick="addMedicine()">إضافة دواء</button>

    <h3>العروض والخصومات:</h3>
    <label for="offer-name">اسم العرض:</label>
    <input type="text" id="offer-name" placeholder="أدخل اسم العرض">

    <label for="offer-description">وصف العرض:</label>
    <textarea id="offer-description" placeholder="أدخل تفاصيل العرض"></textarea>

    <button onclick="addOffer()">إضافة عرض</button>

    <h3>الأدوية الحالية:</h3>
    <div id="medicine-list"></div>
</div>

<script>
// --- إعدادات لوحة التحكم ---
let medicines = [];  // مصفوفة لتخزين الأدوية

function openAdminPanel() {
    let password = prompt("أدخل كلمة المرور للوصول إلى لوحة التحكم:");
    if (password === "H2001") {
        document.getElementById("admin-panel").style.display = "block";
        displayMedicines();  // عرض الأدوية عند فتح لوحة التحكم
    } else {
        alert("كلمة المرور غير صحيحة");
    }
}

function addMedicine() {
    let name = document.getElementById("med-name").value;
    let price = document.getElementById("med-price").value;
    let category = document.getElementById("med-category").value;
    let type = document.getElementById("med-type").value;

    if (name && price && category && type) {
        medicines.push({ name, price, category, type });
        displayMedicines();
        alert(`تم إضافة الدواء: ${name} (${type}) بسعر ${price} جنيه`);
        document.getElementById("med-name").value = '';
        document.getElementById("med-price").value = '';
        document.getElementById("med-category").value = 'مسكن';
        document.getElementById("med-type").value = 'حقن';
    } else {
        alert("من فضلك، تأكد من ملء جميع الحقول");
    }
}

function displayMedicines() {
    let medicineListContainer = document.getElementById("medicine-list");
    medicineListContainer.innerHTML = "";  // تفريغ قائمة الأدوية

    medicines.forEach((medicine, index) => {
        let medicineItem = document.createElement("div");
        medicineItem.innerHTML = `
            <p><strong>${medicine.name}</strong> - ${medicine.type} - ${medicine.category} - ${medicine.price} جنيه</p>
            <button onclick="editMedicine(${index})">تعديل</button>
            <button onclick="deleteMedicine(${index})">حذف</button>
        `;
        medicineListContainer.appendChild(medicineItem);
    });
}

function deleteMedicine(index) {
    medicines.splice(index, 1);  // حذف الدواء من المصفوفة
    displayMedicines();  // إعادة عرض الأدوية بعد الحذف
    alert("تم حذف الدواء");
}

function editMedicine(index) {
    let medicine = medicines[index];
    
    // تعبئة الحقول بالقيم الحالية للدواء
    document.getElementById("med-name").value = medicine.name;
    document.getElementById("med-price").value = medicine.price;
    document.getElementById("med-category").value = medicine.category;
    document.getElementById("med-type").value = medicine.type;

    // تعديل الزر ليكون زر تحديث بدل إضافة دواء
    let addButton = document.querySelector("button[onclick='addMedicine()']");
    addButton.textContent = "تحديث الدواء";
    addButton.setAttribute("onclick", `updateMedicine(${index})`);
}

function updateMedicine(index) {
    let name = document.getElementById("med-name").value;
    let price = document.getElementById("med-price").value;
    let category = document.getElementById("med-category").value;
    let type = document.getElementById("med-type").value;

    if (name && price && category && type) {
        medicines[index] = { name, price, category, type };  // تحديث الدواء في المصفوفة
        displayMedicines();  // إعادة عرض الأدوية بعد التحديث
        alert(`تم تحديث الدواء: ${name}`);
        
        // إعادة الزر لوضعه الأساسي
        let addButton = document.querySelector("button[onclick='updateMedicine()']");
        addButton.textContent = "إضافة دواء";
        addButton.setAttribute("onclick", "addMedicine()");
        
        // مسح الحقول بعد التحديث
        document.getElementById("med-name").value = '';
        document.getElementById("med-price").value = '';
        document.getElementById("med-category").value = 'مسكن';
        document.getElementById("med-type").value = 'حقن';
    } else {
        alert("من فضلك، تأكد من ملء جميع الحقول");
    }
}
</script>
</body>
</html>
