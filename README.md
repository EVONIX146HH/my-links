<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мои ссылки | ch3rusha</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.0.0/css/all.min.css">
    <!-- Добавляем современный шрифт -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #3b82f6;
            --primary-dark: #2563eb;
            --secondary-color: #64748b;
            --background-dark: #0f172a;
            --card-bg: #1e293b;
            --card-hover-bg: #334155;
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --accent-color: #38bdf8;
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: linear-gradient(135deg, var(--background-dark) 0%, #1a1a2e 100%);
            font-family: 'Montserrat', sans-serif;
            min-height: 100vh;
            color: var(--text-primary);
            position: relative;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 40px 20px;
        }
        .disclaimer-banner {
            background-color: rgba(239, 68, 68, 0.1);
            border-left: 3px solid #ef4444;
            padding: 10px 15px;
            margin-bottom: 20px;
            border-radius: 0 8px 8px 0;
            font-size: 14px;
            line-height: 1.4;
        }
        .profile-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-bottom: 2rem;
            position: relative;
        }
        .profile-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            margin-bottom: 1.5rem;
            position: relative;
            overflow: hidden;
            border: 3px solid var(--accent-color);
            box-shadow: 0 0 20px rgba(56, 189, 248, 0.3);
        }
        .avatar-content {
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            font-size: 2.5rem;
            font-weight: bold;
            color: white;
        }
        .profile-name {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 0.25rem;
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            text-align: center;
        }
        .profile-description {
            color: var(--text-secondary);
            text-align: center;
            margin-bottom: 1.5rem;
            font-size: 1rem;
        }
        .social-icons {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }
        .social-icon {
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            transition: all 0.3s ease;
            font-size: 28px;
            position: relative;
            color: white;
        }
        .social-icon:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
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
            background: var(--primary-color);
            padding: 3px 8px;
            border-radius: 8px;
            font-size: 10px;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .tiktok:hover::after {
            opacity: 1;
        }
        .link-cards {
            width: 100%;
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }
        .link-card {
            border-radius: 16px;
            background: var(--card-bg);
            overflow: hidden;
            position: relative;
            transition: all 0.3s ease;
            border: 1px solid rgba(56, 189, 248, 0.1);
        }
        .link-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
            background: var(--card-hover-bg);
            border-color: var(--accent-color);
        }
        .link-content {
            padding: 1rem;
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
        }
        .link-info {
            flex-grow: 1;
        }
        .link-title {
            font-weight: 600;
            font-size: 1.1rem;
            margin-bottom: 0.25rem;
        }
        .link-subtitle {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }
        .link-arrow {
            margin-left: auto;
            color: var(--text-secondary);
            transition: transform 0.3s ease;
        }
        .link-card:hover .link-arrow {
            transform: translateX(5px);
            color: var(--accent-color);
        }
        .footer {
            margin-top: 3rem;
            text-align: center;
            color: var(--text-secondary);
            font-size: 0.875rem;
            opacity: 0.6;
        }
        .animated-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }
        .animated-bg::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: 
                radial-gradient(circle, rgba(56, 189, 248, 0.03) 20%, transparent 70%),
                radial-gradient(circle, rgba(59, 130, 246, 0.02) 20%, transparent 70%);
            background-size: 50px 50px;
            background-position: 0 0, 25px 25px;
            animation: bgMove 30s linear infinite;
        }
        @keyframes bgMove {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }
        /* Адаптивный дизайн */
        @media (max-width: 480px) {
            .container {
                padding: 20px 16px;
            }
            .profile-name {
                font-size: 1.8rem;
            }
            .social-icon {
                width: 50px;
                height: 50px;
                font-size: 24px;
            }
            .link-icon {
                width: 40px;
                height: 40px;
            }
        }
    </style>
</head>
<body>
    <div class="animated-bg"></div>
    <div class="container">
        <!-- Добавляем маркировку Instagram -->
        <div class="disclaimer-banner">
            Instagram (принадлежит компании Meta, признанной экстремистской и запрещённой на территории РФ)
        </div>
        <div class="profile-container">
            <div class="profile-avatar">
                <div class="avatar-content">CH</div>
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
            <!-- Карточки ссылок -->
            <div class="link-cards">
                <a href="https://t.me/mf_coding_bot" target="_blank" class="link-card">
                    <div class="link-content">
                        <div class="link-icon" style="background: #0088cc;">
                            <i class="fab fa-telegram-plane text-white text-xl"></i>
                        </div>
                        <div class="link-info">
                            <h3 class="link-title">Мой Telegram Бот (в разработке)</h3>
                            <p class="link-subtitle">mf_coding_bot</p>
                        </div>
                        <div class="link-arrow">
                            <i class="fas fa-chevron-right"></i>
                        </div>
                    </div>
                </a>
                <a href="https://vk.com/wellstyle_team?from=groups" target="_blank" class="link-card">
                    <div class="link-content">
                        <div class="link-icon" style="background: #4C75A3;">
                            <i class="fab fa-vk text-white text-xl"></i>
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
                <a href="https://t.me/+3KgkX9ILGZ8xMWQy" target="_blank" class="link-card">
                    <div class="link-content">
                        <div class="link-icon" style="background: #0088cc;">
                            <i class="fab fa-telegram-plane text-white text-xl"></i>
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
            <div class="footer">
                <p>© 2025 ch3rusha</p>
            </div>
        </div>
    </div>
</body>
</html>
