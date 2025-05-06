<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мои проекты | ch3rusha</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #3b82f6;
            --primary-dark: #2563eb;
            --secondary-color: #60a5fa;
            --accent-color: #06b6d4;
            --background-color: #0f172a;
            --card-bg: #1e293b;
            --card-hover-bg: #334155;
            --success-color: #10b981;
            --warning-color: #f59e0b;
            --danger-color: #ef4444;
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background-color: var(--background-color);
            font-family: 'Inter', sans-serif;
            color: #f8fafc;
            position: relative;
            min-height: 100vh;
            background-image: 
                radial-gradient(circle at 20% 20%, rgba(59, 130, 246, 0.2) 0%, transparent 25%),
                radial-gradient(circle at 80% 80%, rgba(6, 182, 212, 0.2) 0%, transparent 25%);
            background-attachment: fixed;
        }
        .container {
            max-width: 700px;
            margin: 0 auto;
            padding: 2rem 1.5rem;
        }
        .header {
            padding-bottom: 1rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        .disclaimer-banner {
            background-color: rgba(239, 68, 68, 0.1);
            border-left: 3px solid #ef4444;
            padding: 0.75rem 1rem;
            margin: 1.5rem 0;
            border-radius: 0 0.5rem 0.5rem 0;
            font-size: 0.875rem;
            line-height: 1.4;
        }
        .profile-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 2rem 0;
        }
        .profile-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            margin-bottom: 1.5rem;
            overflow: hidden;
            position: relative;
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            box-shadow: 0 10px 25px -5px rgba(59, 130, 246, 0.5), 
                        0 0 10px -2px rgba(6, 182, 212, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            font-weight: 700;
            color: white;
        }
        .profile-name {
            font-size: 2.25rem;
            font-weight: 700;
            margin-bottom: 0.25rem;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            text-align: center;
        }
        .profile-description {
            color: #94a3b8;
            text-align: center;
            margin-bottom: 2rem;
            font-size: 1rem;
        }
        .social-icons {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 2.5rem;
        }
        .social-icon {
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            transition: all 0.3s ease;
            font-size: 1.5rem;
            color: white;
            position: relative;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 
                        0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }
        .social-icon:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 
                        0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        .instagram {
            background: #E1306C;
        }
        .telegram {
            background: #0088cc;
        }
        .tiktok {
            background: #000000;
            position: relative;
            overflow: visible;
        }
        .tiktok::after {
            content: "Скоро";
            position: absolute;
            top: -25px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--warning-color);
            padding: 3px 8px;
            border-radius: 8px;
            font-size: 10px;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .tiktok:hover::after {
            opacity: 1;
        }
        .links-section {
            margin-top: 1rem;
        }
        .section-title {
            font-size: 1.25rem;
            font-weight: 600;
            margin-bottom: 1rem;
            color: #e2e8f0;
            display: flex;
            align-items: center;
        }
        .section-title:before,
        .section-title:after {
            content: "";
            flex-grow: 1;
            height: 1px;
            background: rgba(255, 255, 255, 0.1);
        }
        .section-title:before {
            margin-right: 0.75rem;
        }
        .section-title:after {
            margin-left: 0.75rem;
        }
        .links-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1rem;
            margin-bottom: 2rem;
        }
        .link-card {
            border-radius: 1rem;
            background: var(--card-bg);
            overflow: hidden;
            position: relative;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        .link-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.3), 
                        0 8px 10px -6px rgba(0, 0, 0, 0.2);
            background: var(--card-hover-bg);
            border-color: rgba(255, 255, 255, 0.1);
        }
        .link-content {
            padding: 1.25rem;
            display: flex;
            align-items: center;
        }
        .link-icon {
            width: 48px;
            height: 48px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 1rem;
            flex-shrink: 0;
            font-size: 1.25rem;
        }
        .link-info {
            flex-grow: 1;
        }
        .link-title {
            font-weight: 600;
            font-size: 1.1rem;
            margin-bottom: 0.25rem;
            color: #f1f5f9;
        }
        .link-subtitle {
            color: #94a3b8;
            font-size: 0.9rem;
        }
        .link-arrow {
            margin-left: auto;
            color: #94a3b8;
            transition: transform 0.3s ease;
        }
        .link-card:hover .link-arrow {
            transform: translateX(5px);
            color: #f1f5f9;
        }
        .order-section {
            margin-top: 3rem;
            padding: 1.5rem;
            border-radius: 1rem;
            background: linear-gradient(135deg, var(--card-bg), var(--card-hover-bg));
            border: 1px solid rgba(255, 255, 255, 0.05);
            position: relative;
            overflow: hidden;
        }
        .order-section::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(59, 130, 246, 0.1), rgba(6, 182, 212, 0.1));
            z-index: 0;
        }
        .order-content {
            position: relative;
            z-index: 1;
        }
        .order-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: #f1f5f9;
        }
        .order-description {
            margin-bottom: 1.5rem;
            color: #cbd5e1;
            line-height: 1.5;
        }
        .order-button {
            display: inline-flex;
            align-items: center;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            color: white;
            padding: 0.75rem 1.5rem;
            border-radius: 0.5rem;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 
                        0 2px 4px -1px rgba(0, 0, 0, 0.06);
            text-decoration: none;
            border: none;
            cursor: pointer;
        }
        .order-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.2), 
                        0 4px 6px -2px rgba(0, 0, 0, 0.1);
        }
        .order-button i {
            margin-right: 0.5rem;
        }
        .footer {
            margin-top: 3rem;
            text-align: center;
            color: #64748b;
            font-size: 0.875rem;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            padding-top: 1.5rem;
        }
        .badge {
            display: inline-block;
            padding: 0.25rem 0.5rem;
            border-radius: 9999px;
            font-size: 0.75rem;
            font-weight: 500;
            text-transform: uppercase;
            margin-left: 0.5rem;
            vertical-align: middle;
        }
        .badge-blue {
            background-color: rgba(59, 130, 246, 0.2);
            color: #93c5fd;
        }
        .badge-yellow {
            background-color: rgba(245, 158, 11, 0.2);
            color: #fcd34d;
        }
        .glowing-border {
            position: relative;
        }
        .glowing-border::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            border-radius: 1rem;
            z-index: -1;
            background: linear-gradient(-45deg, 
                var(--primary-color), 
                var(--secondary-color), 
                var(--accent-color), 
                var(--primary-dark));
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
            filter: blur(3px);
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .glowing-border:hover::after {
            opacity: 1;
        }
        @keyframes gradient {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1 class="text-3xl font-bold">Мои проекты</h1>
        </div>
        <!-- Маркировка Instagram -->
        <div class="disclaimer-banner">
            Instagram (принадлежит компании Meta, признанной экстремистской и запрещённой на территории РФ)
        </div>
        <div class="profile-container">
            <div class="profile-avatar">
                <div>KA</div>
            </div>
            <h1 class="profile-name">Kirill Alexandrovich</h1>
            <p class="profile-description">Мои профили и проекты</p>
            <!-- Социальные иконки -->
            <div class="social-icons">
                <a href="https://www.instagram.com/ch3rusha?igsh=MWJybmF5cGM4czN4YQ%3D%3D&utm_source=qr" target="_blank" class="social-icon instagram" title="Instagram (принадлежит компании Meta, признанной экстремистской и запрещённой на территории РФ)">
                    <i class="fab fa-instagram"></i>
                </a>
                <a href="https://t.me/+fkKummMFGdIwOWEy" target="_blank" class="social-icon telegram" title="Telegram">
                    <i class="fab fa-telegram-plane"></i>
                </a>
                <div class="social-icon tiktok" title="TikTok (Скоро)">
                    <i class="fab fa-tiktok"></i>
                </div>
            </div>
        </div>
        <div class="links-section">
            <h2 class="section-title">Мои проекты</h2>
            <div class="links-grid">
                <!-- Новый проект LinkCut -->
                <a href="https://linkcut.ru/" target="_blank" class="link-card glowing-border">
                    <div class="link-content">
                        <div class="link-icon" style="background: linear-gradient(135deg, #3b82f6, #06b6d4);">
                            <i class="fas fa-link text-white"></i>
                        </div>
                        <div class="link-info">
                            <h3 class="link-title">LinkCut <span class="badge badge-blue">ДОРАБАТЫВАЕТСЯ</span></h3>
                            <p class="link-subtitle">Сервис для сокращения ссылок</p>
                        </div>
                        <div class="link-arrow">
                            <i class="fas fa-chevron-right"></i>
                        </div>
                    </div>
                </a>
                <!-- Telegram Bot -->
                <a href="https://t.me/mf_coding_bot" target="_blank" class="link-card">
                    <div class="link-content">
                        <div class="link-icon" style="background: #0088cc;">
                            <i class="fab fa-telegram-plane text-white"></i>
                        </div>
                        <div class="link-info">
                            <h3 class="link-title">Мой Telegram Бот <span class="badge badge-yellow">В разработке</span></h3>
                            <p class="link-subtitle">mf_coding_bot</p>
                        </div>
                        <div class="link-arrow">
                            <i class="fas fa-chevron-right"></i>
                        </div>
                    </div>
                </a>
                <!-- WST (ВКонтакте) -->
                <a href="https://vk.com/wellstyle_team?from=groups" target="_blank" class="link-card">
                    <div class="link-content">
                        <div class="link-icon" style="background: #4C75A3;">
                            <i class="fab fa-vk text-white"></i>
                        </div>
                        <div class="link-info">
                            <h3 class="link-title">WST (ВКонтакте)</h3>
                            <p class="link-subtitle">wellstyle_team</p>
                        </div>
                        <div class="link-arrow">
                            <i class="fas fa-chevron-right"></i>
                        </div>
                    </div>
                </a>
                <!-- WST (Telegram) -->
                <a href="https://t.me/+3KgkX9ILGZ8xMWQy" target="_blank" class="link-card">
                    <div class="link-content">
                        <div class="link-icon" style="background: #0088cc;">
                            <i class="fab fa-telegram-plane text-white"></i>
                        </div>
                        <div class="link-info">
                            <h3 class="link-title">WST (Telegram)</h3>
                            <p class="link-subtitle">Канал проекта WST</p>
                        </div>
                        <div class="link-arrow">
                            <i class="fas fa-chevron-right"></i>
                        </div>
                    </div>
                </a>
            </div>
        </div>
        <!-- Плашка для заказа подобного сайта -->
        <div class="order-section">
            <div class="order-content">
                <h3 class="order-title">Хотите такой же сайт?</h3>
                <p class="order-description">
                    Закажите у меня персональную страницу со ссылками с возможностью настройки и добавления на собственный домен.
                </p>
                <a href="https://t.me/ch3rusha" target="_blank" class="order-button">
                    <i class="fab fa-telegram-plane"></i>
                    Написать в Telegram
                </a>
            </div>
        </div>
        <div class="footer">
            <p>© 2025 ch3rusha</p>
        </div>
    </div>
</body>
</html>
