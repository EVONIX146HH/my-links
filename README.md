<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мои ссылки</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.0.0/css/all.min.css">
    <style>
        body {
            background: linear-gradient(135deg, #121212 0%, #1e1e2e 100%);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            color: white;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 40px 20px;
        }
        .gradient-border {
            position: relative;
            border-radius: 16px;
            background: #272a3d;
            overflow: hidden;
            z-index: 1;
        }
        .gradient-border::before {
            content: "";
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #ff3399, #ff9933, #33ff99, #3399ff);
            z-index: -1;
            border-radius: 18px;
            animation: borderGlow 3s ease infinite;
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
            overflow: hidden;
        }
        .social-icon::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, #ff3399, #ff9933, #33ff99, #3399ff);
            opacity: 0;
            transition: opacity 0.3s ease;
            z-index: -1;
        }
        .social-icon:hover::before {
            opacity: 1;
        }
        .instagram {
            background: radial-gradient(circle at 30% 107%, #fdf497 0%, #fdf497 5%, #fd5949 45%, #d6249f 60%, #285AEB 90%);
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
            background: #ff3399;
            padding: 3px 8px;
            border-radius: 8px;
            font-size: 10px;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .tiktok:hover::after {
            opacity: 1;
        }
        .link-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .link-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }
        @keyframes borderGlow {
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
        .profile-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid;
            border-image: linear-gradient(45deg, #ff3399, #ff9933, #33ff99, #3399ff) 1;
        }
        .animated-bg {
            position: absolute;
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
            background: radial-gradient(circle, transparent 20%, #121212 80%), 
                        radial-gradient(circle, #1e1e2e 20%, transparent 80%);
            background-size: 20px 20px;
            background-position: 0 0, 10px 10px;
            opacity: 0.05;
            animation: bgMove 15s linear infinite;
        }
        @keyframes bgMove {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }
    </style>
</head>
<body>
    <div class="animated-bg"></div>
    <div class="container">
        <div class="flex flex-col items-center mb-8">
            <div class="w-32 h-32 rounded-full overflow-hidden mb-4 gradient-border">
                <div class="w-full h-full flex items-center justify-center text-4xl font-bold bg-gradient-to-r from-purple-500 to-pink-500 bg-clip-text text-transparent">
                    CH
                </div>
            </div>
            <h1 class="text-3xl font-bold mb-1">Kirill Alexandrovich</h1>
            <p class="text-gray-400 text-center mb-6">Мои профили и проекты</p>
            <!-- Social Icons -->
            <div class="flex justify-center gap-6 mb-8">
                <a href="https://www.instagram.com/ch3rusha?igsh=MWJybmF5cGM4czN4YQ%3D%3D&utm_source=qr" target="_blank" class="social-icon instagram">
                    <i class="fab fa-instagram text-white"></i>
                </a>
                <a href="https://t.me/+fkKummMFGdIwOWEy" target="_blank" class="social-icon telegram">
                    <i class="fab fa-telegram-plane text-white"></i>
                </a>
                <div class="social-icon tiktok">
                    <i class="fab fa-tiktok text-white"></i>
                </div>
            </div>
            <!-- Link Cards -->
            <div class="w-full space-y-4">
                <a href="https://t.me/mf_coding_bot" target="_blank" class="block">
                    <div class="gradient-border">
                        <div class="link-card p-4 bg-gray-800 bg-opacity-80">
                            <div class="flex items-center">
                                <div class="w-10 h-10 rounded-full bg-blue-500 flex items-center justify-center mr-4">
                                    <i class="fab fa-telegram-plane text-white"></i>
                                </div>
                                <div>
                                    <h3 class="font-bold">Мой Telegram Бот (в разработке)</h3>
                                    <p class="text-gray-400 text-sm">mf_coding_bot</p>
                                </div>
                                <div class="ml-auto">
                                    <i class="fas fa-chevron-right text-gray-400"></i>
                                </div>
                            </div>
                        </div>
                    </div>
                </a>
                <a href="https://vk.com/wellstyle_team?from=groups" target="_blank" class="block">
                    <div class="gradient-border">
                        <div class="link-card p-4 bg-gray-800 bg-opacity-80">
                            <div class="flex items-center">
                                <div class="w-10 h-10 rounded-full bg-blue-600 flex items-center justify-center mr-4">
                                    <i class="fab fa-vk text-white"></i>
                                </div>
                                <div>
                                    <h3 class="font-bold">WST (ВКонтакте)</h3>
                                    <p class="text-gray-400 text-sm">wellstyle_team</p>
                                </div>
                                <div class="ml-auto">
                                    <i class="fas fa-chevron-right text-gray-400"></i>
                                </div>
                            </div>
                        </div>
                    </div>
                </a>
                <a href="https://t.me/+3KgkX9ILGZ8xMWQy" target="_blank" class="block">
                    <div class="gradient-border">
                        <div class="link-card p-4 bg-gray-800 bg-opacity-80">
                            <div class="flex items-center">
                                <div class="w-10 h-10 rounded-full bg-blue-500 flex items-center justify-center mr-4">
                                    <i class="fab fa-telegram-plane text-white"></i>
                                </div>
                                <div>
                                    <h3 class="font-bold">WST (Telegram)</h3>
                                    <p class="text-gray-400 text-sm">Канал проекта WST</p>
                                </div>
                                <div class="ml-auto">
                                    <i class="fas fa-chevron-right text-gray-400"></i>
                                </div>
                            </div>
                        </div>
                    </div>
                </a>
            </div>
            <div class="mt-12 text-center text-gray-500 text-sm">
                <p>© 2025 ch3rusha</p>
            </div>
        </div>
    </div>
</body>
</html>
