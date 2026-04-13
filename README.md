<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ندى آرت — فن الطبيعة والعيون</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;700&family=Amiri:ital@1&display=swap" rel="stylesheet">

    <style>
        /* إعدادات الألوان والهوية البصرية */
        :root {
            --primary-purple: #7d5ba6;  /* البنفسجي */
            --bg-cream: #fdfaf5;       /* الكريمي */
            --text-dark: #333333;
            --accent-lavender: #a389c4;
        }

        /* تنسيقات عامة */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Cairo', sans-serif;
            background-color: var(--bg-cream);
            color: var(--text-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            width: 90%;
            max-width: 1100px;
            margin: 0 auto;
        }

        /* القائمة العلوية (Header) */
        header {
            background-color: rgba(253, 250, 245, 0.95);
            padding: 15px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Amiri', serif;
            font-size: 1.8rem;
            color: var(--primary-purple);
            text-decoration: none;
            font-weight: bold;
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-right: 25px;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-dark);
            font-weight: 500;
            transition: 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary-purple);
        }

        /* زر الجوال */
        .menu-toggle {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .menu-toggle span {
            height: 3px;
            width: 25px;
            background: var(--primary-purple);
            margin-bottom: 4px;
            border-radius: 2px;
        }

        /* القسم الرئيسي (Hero) */
        .hero {
            padding: 150px 0 80px;
            text-align: center;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 5vw, 4rem);
            margin-bottom: 20px;
            color: var(--primary-purple);
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
        }

        .btn {
            display: inline-block;
            padding: 12px 35px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: 0.3s;
            margin: 5px;
        }

        .btn-primary {
            background-color: var(--primary-purple);
            color: white;
        }

        .btn-secondary {
            border: 2px solid var(--primary-purple);
            color: var(--primary-purple);
        }

        /* قسم المعرض (Gallery) */
        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .gallery {
            padding: 80px 0;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }

        .gallery-item {
            position: relative;
            height: 350px;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: 0.5s;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .overlay {
            position: absolute;
            bottom: 0;
            width: 100%;
            padding: 20px;
            background: linear-gradient(transparent, rgba(0,0,0,0.7));
            color: white;
            text-align: right;
        }

        /* قسم الخدمات والتواصل */
        .contact {
            padding: 80px 0;
            background-color: #fff;
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .contact-form input, .contact-form select, .contact-form textarea {
            width: 100%;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 10px;
            font-family: inherit;
        }

        .submit-btn {
            background-color: var(--primary-purple);
            color: white;
            border: none;
            padding: 15px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
            font-size: 1.1rem;
        }

        footer {
            text-align: center;
            padding: 40px 0;
            background: var(--bg-cream);
            border-top: 1px solid #eee;
        }

        /* استعلامات الوسائط (للتجاوب مع الجوال) */
        @media (max-width: 768px) {
            .nav-links {
                display: none; /* سيتم تفعيلها بالجافاسكريبت */
                position: absolute;
                top: 70px;
                right: 0;
                width: 100%;
                background: var(--bg-cream);
                flex-direction: column;
                text-align: center;
                padding: 20px 0;
                box-shadow: 0 10px 10px rgba(0,0,0,0.05);
            }

            .nav-links.active {
                display: flex;
            }

            .nav-links li {
                margin: 15px 0;
            }

            .menu-toggle {
                display: flex;
            }

            .hero h1 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="container">
            <nav>
                <a href="#" class="logo">Nada Art</a>
                <div class="menu-toggle" id="mobile-menu">
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
                <ul class="nav-links">
                    <li><a href="#about">عني</a></li>
                    <li><a href="#gallery">أعمالي</a></li>
                    <li><a href="#services">خدماتي</a></li>
                    <li><a href="#contact">تواصل معي</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <p style="color: var(--primary-purple); font-weight: bold;">فن — طبيعة — عيون</p>
            <h1>حيث تلتقي الطبيعة بالفن</h1>
            <p>أرسم مشاعر الطبيعة وتفاصيل العيون بلمسات رقيقة من قلم الرصاص واللافندر.</p>
            <div>
                <a href="#gallery" class="btn btn-primary">استعرضي أعمالي</a>
                <a href="#contact" class="btn btn-secondary">طلب رسمة خاصة</a>
            </div>
        </div>
    </section>

    <section id="gallery" class="gallery">
        <div class="container">
            <div class="section-title">
                <span style="color: var(--primary-purple);">معرضي الخاص</span>
                <h2>لمسة القلم</h2>
            </div>
            <div class="gallery-grid">
                <div class="gallery-item">
                    <img src="https://via.placeholder.com/400x500/f0e6ff/7d5ba6?text=رسم+زهور" alt="رسم زهور">
                    <div class="overlay"><h3>دراسات نباتية - زهور</h3></div>
                </div>
                <div class="gallery-item">
                    <img src="https://via.placeholder.com/400x500/f0e6ff/7d5ba6?text=رسم+عيون" alt="رسم عيون">
                    <div class="overlay"><h3>بورتريه العيون الواقعي</h3></div>
                </div>
                <div class="gallery-item">
                    <img src="https://via.placeholder.com/400x500/f0e6ff/7d5ba6?text=لافندر" alt="لافندر">
                    <div class="overlay"><h3>جمال اللافندر</h3></div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="contact">
        <div class="container">
            <div class="section-title">
                <h2>لنرسم قصتكِ معاً</h2>
                <p>هل لديكِ فكرة لرسومات مخصصة؟ أنا هنا لتحويلها لواقع.</p>
            </div>
            <form class="contact-form">
                <input type="text" placeholder="الاسم الكريم" required>
                <input type="email" placeholder="بريدك الإلكتروني" required>
                <select required>
                    <option value="">اختاري نوع الرسمة...</option>
                    <option value="flowers">رسم زهور وطبيعة</option>
                    <option value="eyes">بورتريه عيون</option>
                    <option value="custom">تصميم مخصص</option>
                </select>
                <textarea rows="5" placeholder="تفاصيل الطلب..."></textarea>
                <button type="submit" class="submit-btn">أرسلي طلبك ✦</button>
            </form>
        </div>
    </section>

    <footer>
        <div class="container">
            <p class="logo" style="font-size: 1.2rem;">Nada Art Studio</p>
            <p>© 2026 ندى آرت. جميع الحقوق محفوظة.</p>
        </div>
    </footer>

    <script>
        // كود لتشغيل قائمة الجوال
        const menuToggle = document.getElementById('mobile-menu');
        const navLinks = document.querySelector('.nav-links');

        menuToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // إغلاق القائمة عند الضغط على رابط (للجوال)
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });
    </script>
</body>
</html>
