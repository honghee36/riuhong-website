<html lang="vi">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>RiuHong Fashion</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            scroll-behavior: smooth;
            background-color: #ffffff;
        }
        header {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 15px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(0,0,0,0.4);
            backdrop-filter: blur(5px);
            z-index: 1000;
        }
        header h1 {
            color: white;
            margin: 0;
            letter-spacing: 3px;
            font-size: 24px;
        }
        nav a {
            color: white;
            margin-left: 20px;
            text-decoration: none;
            transition: 0.3s;
        }
        nav a:hover {
            color: black;
            background: white;
            padding: 5px 10px;
            border-radius: 6px;
            transition: 0.3s;
        }
        .lang-switch {
            cursor: pointer;
            padding: 6px 10px;
            border-radius: 6px;
            border: 1px solid white;
            transition: 0.3s;
        }
        .lang-switch:hover {
            background: white;
            color: black;
        }

        .hero {
            height: 100vh;
            background: url('ảnh/Ảnh\ chụp\ màn\ hình\ 2025-11-27\ 215312.png') center/cover no-repeat;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            text-shadow: 2px 2px 4px black;
            font-size: 50px;
            font-weight: bold;
        }

        .products {
            padding: 100px 40px;
            text-align: center;
        }
        .products h2 {
            font-size: 36px;
            margin-bottom: 20px;
        }
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }
        .item {
            border-radius: 10px;
            padding: 20px;
            background: #f5f5f5;
            transition: 0.3s;
        }
        .item:hover {
            transform: translateY(-5px);
            background: #eaeaea;
        }
        .item img {
            width: 100%;
            border-radius: 10px;
        }

        footer {
            padding: 50px;
            background: black;
            color: white;
            text-align: center;
            font-size: 18px;
        }
        .icon:hover {
            filter: invert(1);
            transition: 0.3s;
        }
    </style>
</head>
<body>
    <header>
        <h1>RiuHong</h1>
        <nav>
            <a href="#hero">Home</a>
            <a href="#products">Sản phẩm</a>
            <a href="#contact">Liên hệ</a>
            <span class="lang-switch" onclick="toggleLang()">VI/EN</span>
        </nav>
    </header>

    <section class="hero" id="hero">RiuHong Fashion</section>

    <section class="products" id="products">
        <h2>Sản phẩm nổi bật</h2>
        <div class="grid">
            <div class="item"><img src="ảnh/z7269443548066_cb0c89a7e99da9f2278c4f1dabd1f6ab.jpg"><p>Hoodie black</p></div>
            <div class="item"><img src="ảnh/z7269443548905_43e0fa03e50582256b7d063bd7795e72.jpg"><p>Jean Loe Black</p></div>
            <div class="item"><img src="ảnh/z7269607360000_a1954f888ec76ee1558e26e903283947.jpg"><p>Áo Paradax</p></div>
            <div class="item"><img src="ảnh/z7269607799977_ca1ff7a3c701a7f7f2cda0a526f425c7.jpg"><p>FULL SET TAM đẢO</p></div>
        </div>
    </section>

    <footer id="contact">
        <p>Email: pipomusic0306@gmail.com</p>
        <p>Số điện thoại: 0964457535</p>
        <p>Địa chỉ: Khâm Thiên</p>
    </footer>

    <script>
        function toggleLang() {
            const lang = document.documentElement.lang;
            if (lang === 'vi') {
                document.documentElement.lang = 'en';
                document.querySelector('h2').innerText = 'Featured Products';
                document.querySelector('.hero').innerText = 'RiuHong Fashion';
                document.querySelectorAll('.item p')[0].innerText = 'Croptop';
                document.querySelectorAll('.item p')[1].innerText = 'Office Dress';
                document.querySelectorAll('.item p')[2].innerText = 'Hoodie';
                document.querySelectorAll('.item p')[3].innerText = 'Jeans';
                document.querySelector('footer').innerHTML = `
                    <p>Email: pipomusic0306@gmail.com</p>
                    <p>Phone: 0964457535</p>
                    <p>Address: Kham Thien</p>`;
            } else {
                location.reload();
            }
        }
    </script>
</body>
</html>
