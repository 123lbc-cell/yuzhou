<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>九星连珠</title>
    <style>
        /* 基础样式 */
        body {
            margin: 0;
            height: 100vh;
            overflow: hidden;
            background: #000; /* 纯黑色背景 */
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
        }

        /* 动态星星背景 */
        .star-background {
            position: absolute;
            width: 100%;
            height: 100%;
            background: transparent;
            overflow: hidden;
        }

        .star-background::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100%" height="100%"><circle cx="50" cy="50" r="1" fill="white" /></svg>');
            animation: twinkle 5s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }

        /* 行星样式 */
        .star {
            position: absolute;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            box-shadow: 0 0 10px currentColor, 0 0 20px currentColor, 0 0 30px currentColor;
            animation: glow infinite;
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .star:hover {
            transform: scale(1.2);
            box-shadow: 0 0 20px currentColor, 0 0 40px currentColor, 0 0 60px currentColor;
        }

        /* 行星发光动画 */
        @keyframes glow {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }

        /* 行星名字样式 */
        .star-name {
            position: absolute;
            color: #fff;
            font-family: Arial, sans-serif;
            font-size: 14px;
            display: none;
            white-space: nowrap;
            background: rgba(0, 0, 0, 0.7);
            padding: 5px 10px;
            border-radius: 5px;
            pointer-events: none;
        }

        /* 流星样式 */
        .meteor {
            position: absolute;
            width: 2px;
            height: 2px;
            background: linear-gradient(to right, rgba(255, 255, 255, 0), rgba(255, 255, 255, 1));
            border-radius: 50%;
            box-shadow: 0 0 10px #fff, 0 0 20px #fff;
            animation: meteorFly linear infinite;
        }

        /* 流星动画 */
        @keyframes meteorFly {
            0% {
                transform: translate(-100px, -100px) rotate(45deg);
                opacity: 1;
            }
            100% {
                transform: translate(200px, 200px) rotate(45deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <!-- 动态星星背景 -->
    <div class="star-background"></div>

    <!-- 九颗行星 -->
    <div class="star" style="top: 50%; left: 10%; animation-duration: 1s; color: #ff6b6b;" data-name="水星"></div>
    <div class="star" style="top: 45%; left: 20%; animation-duration: 1.5s; color: #ffcc00;" data-name="金星"></div>
    <div class="star" style="top: 40%; left: 30%; animation-duration: 2s; color: #00ccff;" data-name="地球"></div>
    <div class="star" style="top: 35%; left: 40%; animation-duration: 2.5s; color: #ff00ff;" data-name="火星"></div>
    <div class="star" style="top: 30%; left: 50%; animation-duration: 3s; color: #00ff99;" data-name="木星"></div>
    <div class="star" style="top: 25%; left: 60%; animation-duration: 3.5s; color: #ff9900;" data-name="土星"></div>
    <div class="star" style="top: 20%; left: 70%; animation-duration: 4s; color: #cc00ff;" data-name="天王星"></div>
    <div class="star" style="top: 15%; left: 80%; animation-duration: 4.5s; color: #00ffcc;" data-name="海王星"></div>
    <div class="star" style="top: 10%; left: 90%; animation-duration: 5s; color: #ff0066;" data-name="冥王星"></div>

    <!-- 行星名字显示区域 -->
    <div id="star-name-display" class="star-name"></div>

    <script>
        const stars = document.querySelectorAll('.star');
        const starNameDisplay = document.getElementById('star-name-display');

        // 点击行星显示名字
        stars.forEach(star => {
            star.addEventListener('click', (event) => {
                event.stopPropagation(); // 阻止事件冒泡
                const name = star.getAttribute('data-name');
                starNameDisplay.textContent = name;
                starNameDisplay.style.display = 'block';
                starNameDisplay.style.top = `${star.offsetTop + 20}px`;
                starNameDisplay.style.left = `${star.offsetLeft + 20}px`;
            });
        });

        // 点击页面其他区域隐藏名字
        document.addEventListener('click', () => {
            starNameDisplay.style.display = 'none';
        });

        // 流星生成函数
        function createMeteor() {
            const meteor = document.createElement('div');
            meteor.className = 'meteor';
            meteor.style.top = `${Math.random() * 100}%`;
            meteor.style.left = `${Math.random() * 100}%`;
            meteor.style.animationDuration = `${Math.random() * 2 + 1}s`; // 随机速度
            document.body.appendChild(meteor);
            setTimeout(() => {
                meteor.remove();
            }, 3000);
        }

        // 定时生成流星
        setInterval(createMeteor, 500);
    </script>
</body>
</html>
