<html lang="vi">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>RiuHong | DRIPP GANG GANG </title>
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>
    <style>
        :root {
            --primary: #000000;
            --secondary: #ffffff;
            --accent: #d4af37;
            --text: #333;
        }
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: 'Montserrat', 'Arial', sans-serif;
            overflow-x: hidden;
            background: #fafafa;
            color: var(--text);
        }

        header {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(255,255,255,0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            transition: all 0.4s;
            border-bottom: 1px solid #eee;
        }
        header.scrolled {
            padding: 15px 5%;
            background: rgba(255,255,255,0.98);
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
        }
        .logo {
            font-size: 28px;
            font-weight: 700;
            color: var(--primary);
            letter-spacing: 2px;
        }
        nav {
            display: flex;
            gap: 40px;
            align-items: center;
        }
        nav a {
            color: var(--primary);
            text-decoration: none;
            font-weight: 500;
            position: relative;
            transition: 0.3s;
        }
        nav a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -8px;
            left: 50%;
            background: var(--primary);
            transition: 0.4s;
            transform: translateX(-50%);
        }
        nav a:hover::after { width: 100%; }

        .lang-switch {
            cursor: pointer;
            padding: 8px 16px;
            border: 1.5px solid var(--primary);
            border-radius: 30px;
            font-size: 14px;
            transition: 0.3s;
        }
        .lang-switch:hover {
            background: var(--primary);
            color: white;
        }

        .menu-toggle { display: none; font-size: 24px; cursor: pointer; }

        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.6)), 
                        url('https://scontent.fhan5-11.fna.fbcdn.net/v/t39.30808-6/577889305_1501696354491249_7658951385371762308_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=6ee11a&_nc_ohc=QKv17jZOt_gQ7kNvwEoAYfB&_nc_oc=Adlq6maxtoGiDxU3FqPkoH1wz2Tzx-W1QJtsX3IyTql2wJRJfuGQCWS_O_zjuiYkmSc&_nc_zt=23&_nc_ht=scontent.fhan5-11.fna&_nc_gid=i5onnj5xc-OdtQuGUl4m9w&oh=00_AfivB_RUUn1wmIW2LQsxUkOsdNXNM6cHmb1dCUmr7Jkniw&oe=692E678C') center/cover no-repeat;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: white;
            position: relative;
        }
        .hero h1 {
            font-size: 70px;
            font-weight: 700;
            letter-spacing: 5px;
            margin-bottom: 20px;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeUp 1s forwards 0.5s;
        }
        .hero p {
            font-size: 22px;
            margin-bottom: 40px;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeUp 1s forwards 0.8s;
        }
        .btn {
            padding: 14px 40px;
            background: transparent;
            color: white;
            border: 2px solid white;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: 0.4s;
            opacity: 0;
            animation: fadeUp 1s forwards 1.1s;
        }
        .btn:hover {
            background: white;
            color: black;
            transform: scale(1.05);
        }

        .products {
            padding: 120px 5%;
            text-align: center;
            background: white;
        }
        .section-title {
            font-size: 48px;
            margin-bottom: 80px;
            position: relative;
            display: inline-block;
        }
        .section-title::after {
            content: '';
            width: 80px;
            height: 3px;
            background: var(--primary);
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            max-width: 1400px;
            margin: 0 auto;
        }
        .item {
            position: relative;
            overflow: hidden;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.4s;
            background: white;
        }
        .item:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }
        .item img {
            width: 100%;
            height: 420px;
            object-fit: cover;
            transition: 0.6s;
        }
        .item:hover img {
            transform: scale(1.1);
        }
        .item-info {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            padding: 25px;
            background: linear-gradient(transparent, rgba(0,0,0,0.8));
            color: white;
            transform: translateY(20px);
            opacity: 0;
            transition: 0.4s;
        }
        .item:hover .item-info {
            transform: translateY(0);
            opacity: 1;
        }

        footer {
            background: var(--primary);
            color: white;
            padding: 80px 5% 40px;
            text-align: center;
        }
        .social-icons a {
            color: white;
            font-size: 28px;
            margin: 0 20px;
            transition: 0.3s;
        }
        .social-icons a:hover { 
            transform: translateY(-6px);
        }

        @keyframes fadeUp {
            to { opacity: 1; transform: translateY(0); }
        }

        @media (max-width: 768px) {
            .menu-toggle { display: block; }
            nav { 
                position: fixed;
                top: 0; right: -100%;
                width: 100%;
                height: 100vh;
                background: white;
                flex-direction: column;
                justify-content: center;
                transition: 0.4s;
            }
            nav.active { right: 0; }
            nav a { font-size: 24px; margin: 20px 0; }
            .hero h1 { font-size: 48px; }
            .hero p { font-size: 18px; }
        }
    </style>
</head>
<body>

    <header id="header">
        <div class="logo">RiuHong</div>
        <nav id="nav">
            <a href="#hero">Home</a>
            <a href="#products">Sản phẩm</a>
            <a href="#contact">Liên hệ</a>
            <span class="lang-switch" onclick="toggleLang()">VI / EN</span>
        </nav>
        <div class="menu-toggle" onclick="toggleMenu()">
            <i class="fas fa-bars"></i>
        </div>
    </header>

    <section class="hero" id="hero">
        <h1>RiuHong Fashion</h1>
        <p>Thời trang trẻ trung • Đậm chất riêng</p>
        <a href="#products" class="btn">Khám phá ngay</a>
    </section>

    <section class="products" id="products">
        <h2 class="section-title" data-aos="fade-up">Sản phẩm nổi bật</h2>
        <div class="grid">
            <div class="item" data-aos="fade-up" data-aos-delay="100">
                <img src="ảnh/Ảnh chụp màn hình 2025-11-27 215327.png" alt="Áo Croptop">
                <div class="item-info">
                    <h3>Áo Croptop Trắng</h3>
                    <p>450.000đ</p>
                </div>
            </div>
            <div class="item" data-aos="fade-up" data-aos-delay="200">
                <img src="https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?w=800" alt="Đầm công sở">
                <div class="item-info">
                    <h3>Đầm Công Sở Đen</h3>
                    <p>890.000đ</p>
                </div>
            </div>
            <div class="item" data-aos="fade-up" data-aos-delay="300">
                <img src="https://images.unsplash.com/photo-1503341504253-dff4815485f1?w=800" alt="Hoodie">
                <div class="item-info">
                    <h3>Hoodie Oversize</h3>
                    <p>680.000đ</p>
                </div>
            </div>
            <div class="item" data-aos="fade-up" data-aos-delay="400">
                <img src="ảnh/z7269443548905_43e0fa03e50582256b7d063bd7795e72.jpg" alt="Quần Jean">
                <div class="item-info">
                    <h3>Quần Jean Rách</h3>
                    <p>590.000đ</p>
                </div>
            </div>
        </div>
    </section>

    <!-- FOOTER ĐÃ THÊM ĐẦY ĐỦ LINK CHÍNH CHỦ -->
    <footer id="contact">
        <p>Email: pipomusic0306@gmail.com</p>
        <p>Số điện thoại: 0964 457 535</p>
        <p>Địa chỉ: Khâm Thiên, Đống Đa, Hà Nội</p>
        
        <div class="social-icons" style="margin-top: 40px;">
            <a href="https://www.facebook.com/RiuHong05/?locale=vi_VN" target="_blank" title="Facebook RiuHong">
                <i class="fab fa-facebook-f"></i>
            </a>
            <a href="https://www.instagram.com/riuhong05" target="_blank" title="Instagram RiuHong">
                <i class="fab fa-instagram"></i>
            </a>
            <a href="https://www.tiktok.com/@riuhong05" target="_blank" title="TikTok RiuHong">
                <i class="fab fa-tiktok"></i>
            </a>
        </div>
        
        <p style="margin-top: 40px; opacity: 0.7; font-size: 14px;">
            © 2025 RiuHong Fashion. All rights reserved.
        </p>
    </footer>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init({ duration: 1000, once: true });

        window.addEventListener('scroll', () => {
            document.getElementById('header').classList.toggle('scrolled', window.scrollY > 50);
        });

        function toggleMenu() {
            document.getElementById('nav').classList.toggle('active');
            document.querySelector('.menu-toggle i').classList.toggle('fa-times');
            document.querySelector('.menu-toggle i').classList.toggle('fa-bars');
        }

        let isVietnamese = true;
        function toggleLang() {
            const elements = {
                title: document.querySelector('.section-title'),
                heroTitle: document.querySelector('.hero h1'),
                heroDesc: document.querySelector('.hero p'),
                btn: document.querySelector('.btn'),
                items: document.querySelectorAll('.item-info h3'),
            };

            if (isVietnamese) {
                elements.title.innerText = "Featured Products";
                elements.heroTitle.innerText = "RiuHong Fashion";
                elements.heroDesc.innerText = "Youthful Style • Unique Personality";
                elements.btn.innerText = "Shop Now";
                elements.items[0].innerText = "White Croptop";
                elements.items[1].innerText = "Black Office Dress";
                elements.items[2].innerText = "Oversize Hoodie";
                elements.items[3].innerText = "Ripped Jeans";
            } else {
                location.reload();
            }
            isVietnamese = !isVietnamese;
        }
    </script>
</body>
</html>
