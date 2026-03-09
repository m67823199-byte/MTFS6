<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>جيم نيوز - أخبار الألعاب</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        :root {
            --primary: #ff6b35;
            --secondary: #f7931e;
            --dark: #0f0f1a;
            --darker: #080810;
            --card: #1a1a2e;
            --card-hover: #252542;
            --text: #e0e0e0;
            --text-muted: #888;
            --accent: #ff3366;
        }
        body {
            font-family: 'Tajawal', sans-serif;
            background: linear-gradient(135deg, var(--darker) 0%, var(--dark) 100%);
            color: var(--text);
            min-height: 100vh;
            overflow-x: hidden;
        }
     .bg-pattern {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                radial-gradient(circle at 20% 50%, rgba(255, 107, 53, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(247, 147, 30, 0.1) 0%, transparent 50%);
            pointer-events: none;
            z-index: -1;
        }
        header {
            background: rgba(15, 15, 26, 0.95);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(255, 107, 53, 0.2);
            position: sticky;
            top: 0;
            z-index: 1000;
            padding: 1rem 0;
        }
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
        }
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }
        .logo {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            text-decoration: none;
            color: var(--text);
        }
        .logo-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            box-shadow: 0 4px 20px rgba(255, 107, 53, 0.4);
            animation: pulse 2s infinite;
        }
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        .logo-text {
            font-size: 1.8rem;
            font-weight: 900;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }
        .nav-links a {
            color: var(--text-muted);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
            padding: 0.5rem 0;
        }
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            transition: width 0.3s ease;
        }
        .nav-links a:hover {
            color: var(--primary);
        }
        .nav-links a:hover::after {
            width: 100%;
        }
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--text);
            font-size: 1.5rem;
            cursor: pointer;
        }
        .hero {
            padding: 4rem 0;
        }
        .hero-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }
        .hero-text h1 {
            font-size: 3.5rem;
            font-weight: 900;
            line-height: 1.2;
            margin-bottom: 1.5rem;
            background: linear-gradient(135deg, #fff 0%, var(--primary) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .hero-text p {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
            line-height: 1.8;
        }
        .cta-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }
        .btn {
            padding: 1rem 2rem;
            border-radius: 50px;
            font-weight: 700;
            text-decoration: none;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            border: none;
            cursor: pointer;
            font-family: inherit;
            font-size: 1rem;
        }
        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            box-shadow: 0 4px 20px rgba(255, 107, 53, 0.4);
        }
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 30px rgba(255, 107, 53, 0.6);
        }
        .btn-secondary {
            background: transparent;
            color: var(--text);
            border: 2px solid rgba(255, 107, 53, 0.3);
        }
        .btn-secondary:hover {
            border-color: var(--primary);
            background: rgba(255, 107, 53, 0.1);
        }
        .hero-image {
            position: relative;
        }
        .hero-image img {
            width: 100%;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 107, 53, 0.2);
        }
        .section-title {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 2rem;
            font-size: 2rem;
            font-weight: 800;
        }
        .section-title::before {
            content: '';
            width: 4px;
            height: 40px;
            background: linear-gradient(180deg, var(--primary), var(--secondary));
            border-radius: 2px;
        }
        .news-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }
        .news-card {
            background: var(--card);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.4s ease;
            cursor: pointer;
        }
        .news-card:hover {
            transform: translateY(-10px);
            border-color: rgba(255, 107, 53, 0.3);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
        }
        .news-image {
            width: 100%;
            height: 220px;
            object-fit: cover;
            transition: transform 0.4s ease;
        }
        .news-card:hover .news-image {
            transform: scale(1.05);
        }
        .news-content {
            padding: 1.5rem;
        }
        .news-category {
            display: inline-block;
            padding: 0.4rem 1rem;
            background: rgba(255, 107, 53, 0.2);
            color: var(--primary);
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }
        .news-title {
            font-size: 1.3rem;
            font-weight: 800;
            margin-bottom: 0.75rem;
            line-height: 1.4;
            color: #fff;
        }
        .news-excerpt {
            color: var(--text-muted);
            line-height: 1.7;
            margin-bottom: 1rem;
        }
        .news-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: var(--text-muted);
            font-size: 0.9rem;
        }
        .news-meta span {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        .featured-news {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 2rem;
            margin-bottom: 4rem;
        }
        .featured-main {
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            height: 500px;
        }
        .featured-main img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .featured-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            padding: 3rem;
            background: linear-gradient(to top, rgba(0,0,0,0.9) 0%, transparent 100%);
        }
        .featured-badge {
            display: inline-block;
            padding: 0.5rem 1.5rem;
            background: var(--accent);
            color: white;
            border-radius: 20px;
            font-weight: 700;
            margin-bottom: 1rem;
            animation: glow 2s infinite;
        }
        @keyframes glow {
            0%, 100% { box-shadow: 0 0 5px var(--accent); }
            50% { box-shadow: 0 0 20px var(--accent), 0 0 40px var(--accent); }
        }
        .featured-title {
            font-size: 2rem;
            font-weight: 900;
            margin-bottom: 1rem;
            color: white;
        }
        .featured-sidebar {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }
        .sidebar-item {
            background: var(--card);
            border-radius: 15px;
            padding: 1.5rem;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.3s ease;
            cursor: pointer;
        }
        .sidebar-item:hover {
            background: var(--card-hover);
            border-color: rgba(255, 107, 53, 0.3);
            transform: translateX(-5px);
        }
        .sidebar-item h4 {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            color: white;
        }
        .sidebar-item .time {
            color: var(--text-muted);
            font-size: 0.9rem;
        }
        .games-section {
            margin-bottom: 4rem;
        }
        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
        }
        .game-card {
            background: var(--card);
            border-radius: 15px;
            padding: 1.5rem;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.3s ease;
            cursor: pointer;
        }
        .game-card:hover {
            transform: translateY(-5px);
            border-color: var(--primary);
            box-shadow: 0 10px 30px rgba(255, 107, 53, 0.2);
        }
        .game-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 20px;
            margin: 0 auto 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: white;
        }
        .game-card h3 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
        }
        .game-card p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }
        footer {
            background: var(--darker);
            border-top: 1px solid rgba(255, 107, 53, 0.2);
            padding: 3rem 0 2rem;
            margin-top: 4rem;
        }
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 2rem;
        }
        .footer-section h3 {
            color: var(--primary);
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }
        .footer-section p, .footer-section a {
            color: var(--text-muted);
            text-decoration: none;
            line-height: 2;
            transition: color 0.3s ease;
        }
        .footer-section a:hover {
            color: var(--primary);
        }
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }
        .social-links a {
            width: 45px;
            height: 45px;
            background: var(--card);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text);
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        .social-links a:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-3px);
        }
        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            color: var(--text-muted);
        }
        @media (max-width: 968px) {
            .hero-content {
                grid-template-columns: 1fr;
                text-align: center;
            }
            .hero-text h1 {
                font-size: 2.5rem;
            }
            .featured-news {
                grid-template-columns: 1fr;
            }
            .featured-main {
                height: 400px;
            }
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background: var(--dark);
                flex-direction: column;
                padding: 2rem;
                gap: 1.5rem;
                border-top: 1px solid rgba(255, 107, 53, 0.2);
            }
            .nav-links.active {
                display: flex;
            }
            .mobile-menu-btn {
                display: block;
            }
        }
        @media (max-width: 600px) {
            .container {
                padding: 0 1rem;
            }
            .hero-text h1 {
                font-size: 2rem;
            }
            .news-grid {
                grid-template-columns: 1fr;
            }
            .games-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            .featured-main {
                height: 300px;
            }
            .featured-overlay {
                padding: 1.5rem;
            }
            .featured-title {
                font-size: 1.3rem;
            }
        }
        .scroll-top {
            position: fixed;
            bottom: 30px;
            left: 30px;
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            cursor: pointer;
            opacity: 0;
            transition: all 0.3s ease;
            z-index: 999;
            border: none;
            font-size: 1.2rem;
        }
        .scroll-top.visible {
            opacity: 1;
        }
        .scroll-top:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(255, 107, 53, 0.4);
        }
    </style>
</head>
<body>
    <div class="bg-pattern"></div>
    <header>
        <div class="container">
            <nav>
                <a href="#" class="logo">
                    <div class="logo-icon">
                        <i class="fas fa-gamepad"></i>
                    </div>
                    <span class="logo-text">جيم نيوز</span>
                </a>
                <ul class="nav-links" id="navLinks">
                    <li><a href="#home">الرئيسية</a></li>
                    <li><a href="#news">أخبار</a></li>
                    <li><a href="#reviews">مراجعات</a></li>
                    <li><a href="#games">ألعاب</a></li>
                    <li><a href="#videos">فيديو</a></li>
                </ul>
                <button class="mobile-menu-btn" onclick="toggleMenu()">
                    <i class="fas fa-bars"></i>
                </button>
            </nav>
        </div>
    </header>
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>عالم الألعاب بين يديك</h1>
                    <p>أحدث أخبار الألعاب، المراجعات الحصرية، وتغطيات مباشرة لأكبر الأحداث في عالم الجيمنج. كن أول من يعلم!</p>
                    <div class="cta-buttons">
                        <a href="#news" class="btn btn-primary">
                            <i class="fas fa-newspaper"></i>
                            اقرأ الأخبار
                        </a>
                        <a href="#" class="btn btn-secondary">
                            <i class="fas fa-play"></i>
                            شاهد الفيديوهات
                        </a>
                    </div>
                </div>
                <div class="hero-image">
                    <img src="https://images.unsplash.com/photo-1542751371-adc38448a05e?w=800&q=80" alt="Gaming Setup">
                </div>
            </div>
        </div>
    </section>
    <section class="featured-news container" id="news">
        <div class="featured-main">
            <img src="https://images.unsplash.com/photo-1538481199705-c710c4e965fc?w=1200&q=80" alt="Featured News">
            <div class="featured-overlay">
                <span class="featured-badge">خبر عاجل</span>
                <h2 class="featured-title">إعلان رسمي عن الجيل الجديد من منصات الألعاب المستقبلية</h2>
                <p>تفاصيل حصرية عن المواصفات وموعد الإطلاق</p>
            </div>
        </div>    
        <div class="featured-sidebar">
            <div class="sidebar-item">
                <span class="news-category">بلايستيشن</span>
                <h4>حصريات بلايستيشن 5 القادمة هذا العام</h4>
                <span class="time"><i class="far fa-clock"></i> منذ ساعتين</span>
            </div>
            <div class="sidebar-item">
                <span class="news-category">اكسبوكس</span>
                <h4>خدمة جيم باس تضيف 5 ألعاب جديدة</h4>
                <span class="time"><i class="far fa-clock"></i> منذ 4 ساعات</span>
            </div>
            <div class="sidebar-item">
                <span class="news-category">نينتندو</span>
                <h4>شائعات جديدة حول سويتش 2</h4>
                <span class="time"><i class="far fa-clock"></i> منذ 6 ساعات</span>
            </div>
        </div>
    </section>
    <section class="container">
        <h2 class="section-title">أحدث الأخبار</h2>
        <div class="news-grid">
            <article class="news-card">
                <img src="https://images.unsplash.com/photo-1552820728-8b83bb6b2b0a?w=600&q=80" alt="News" class="news-image">
                <div class="news-content">
                    <span class="news-category">أكشن</span>
                    <h3 class="news-title">كشف النقاب عن لعبة Assassin's Creed الجديدة رسمياً</h3>
                    <p class="news-excjhshssysg
