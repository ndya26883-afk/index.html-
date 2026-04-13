<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ندى آرت — فن الطبيعة والعيون</title>
    <link rel="stylesheet" href="style.css">
    <link href="https://fonts.googleapis.com/css2?family=Amiri&family=Cairo:wght@300;400;700&display=swap" rel="stylesheet">
</head>
<body>

    <nav class="navbar">
        <div class="container">
            <a href="#" class="logo">Nada Art Studio</a>
            <ul class="nav-links">
                <li><a href="#gallery">أعمالي</a></li>
                <li><a href="#services">خدماتي</a></li>
                <li><a href="#about">عني</a></li>
                <li><a href="#contact">تواصلي</a></li>
            </ul>
        </div>
    </nav>

    <header class="hero">
        <div class="container">
            <p class="subtitle">فن — طبيعة — عيون</p>
            <h1>حيث تلتقي *الطبيعة* بالفن</h1>
            <p class="description">لوحات بالرصاص تنبض بالحياة — من أناقة الزهور البرية إلى عمق العيون الإنسانية.</p>
            <div class="hero-btns">
                <a href="#gallery" class="btn primary">استعرضي أعمالي</a>
                <a href="#contact" class="btn secondary">طلب رسمة</a>
            </div>
        </div>
    </header>

    <section id="gallery" class="gallery">
        <div class="container">
            <span class="section-tag">معرضي</span>
            <h2>لمسة *القلم*</h2>
            <div class="gallery-grid">
                <div class="gallery-item">
                    <img src="images/flower1.jpg" alt="رسم زهور">
                    <div class="overlay"><h3>رسم زهور</h3></div>
                </div>
                <div class="gallery-item">
                    <img src="images/eye1.jpg" alt="رسم عيون">
                    <div class="overlay"><h3>بورتريه عيون</h3></div>
                </div>
                <div class="gallery-item">
                    <img src="images/lavender.jpg" alt="لافندر">
                    <div class="overlay"><h3>لافندر</h3></div>
                </div>
                </div>
        </div>
    </section>

    <section id="contact" class="contact">
        <div class="container">
            <h2>لنرسم *قصتك* معًا</h2>
            <form class="contact-form">
                <input type="text" placeholder="الاسم" required>
                <input type="email" placeholder="البريد الإلكتروني" required>
                <select>
                    <option value="">اختاري نوع الرسمة...</option>
                    <option value="flowers">رسم زهور وطبيعة</option>
                    <option value="eyes">بورتريه عيون</option>
                    <option value="custom">تصميم مخصص</option>
                </select>
                <textarea placeholder="رسالتك" rows="5"></textarea>
                <button type="submit" class="btn primary">أرسلي طلبك ✦</button>
            </form>
        </div>
    </section>

    <footer>
        <p>© 2025 Nada Art Studio · جميع الحقوق محفوظة</p>
    </footer>

</body>
</html>
/* إعدادات عامة */
:root {
    --primary-color: #7d5ba6; /* بنفسجي لافندر */
    --bg-color: #fdfaf5;      /* كريمي هادئ */
    --text-color: #333;
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Cairo', sans-serif;
    background-color: var(--bg-color);
    color: var(--text-color);
    line-height: 1.6;
}

.container {
    width: 90%;
    max-width: 1100px;
    margin: 0 auto;
}

/* القائمة العلوية المتجاوبة */
.navbar {
    background: rgba(255, 255, 255, 0.9);
    padding: 1rem 0;
    position: sticky;
    top: 0;
    z-index: 1000;
}

.navbar .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.nav-links {
    display: flex;
    list-style: none;
}

.nav-links li a {
    text-decoration: none;
    color: var(--text-color);
    margin-right: 20px;
    font-weight: bold;
}

/* القسم الرئيسي (Hero) */
.hero {
    text-align: center;
    padding: 100px 0;
}

.hero h1 {
    font-size: 3rem;
    margin-bottom: 20px;
}

.btn {
    padding: 12px 30px;
    text-decoration: none;
    border-radius: 25px;
    display: inline-block;
    margin: 10px;
    transition: 0.3s;
}

.primary { background: var(--primary-color); color: white; border: none; }
.secondary { border: 1px solid var(--primary-color); color: var(--primary-color); }

/* معرض الأعمال (Grid) */
.gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
    padding: 40px 0;
}

.gallery-item {
    position: relative;
    overflow: hidden;
    border-radius: 10px;
    height: 300px;
}

.gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

/* --- التحكم في الأجهزة الصغيرة (الجوال) --- */
@media (max-width: 768px) {
    .navbar .container {
        flex-direction: column;
    }

    .nav-links {
        margin-top: 15px;
    }

    .nav-links li a {
        margin: 0 10px;
        font-size: 0.9rem;
    }

    .hero h1 {
        font-size: 2rem;
    }

    .hero-btns {
        display: flex;
        flex-direction: column;
    }

    .gallery-grid {
        grid-template-columns: 1fr; /* عرض صورة واحدة في الصف للجوال */
    }

    .contact-form {
        width: 100%;
    }
}

/* قسم التواصل */
.contact-form {
    display: flex;
    flex-direction: column;
    max-width: 600px;
    margin: 0 auto;
    gap: 15px;
}

.contact-form input, .contact-form select, .contact-form textarea {
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
    font-family: inherit;
}

footer {
    text-align: center;
    padding: 40px 0;
    font-size: 0.9rem;
    color: #888;
}
