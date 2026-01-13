<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ateş'ten Sakura'ya</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            overflow-x: hidden;
            background: linear-gradient(-45deg, #ffeef8, #ffe5f0, #ffd5e5, #ffb7d5);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Parlama efekti */
        .sparkle {
            position: fixed;
            width: 4px;
            height: 4px;
            background: white;
            border-radius: 50%;
            pointer-events: none;
            animation: sparkleAnim 2s ease-in-out infinite;
            box-shadow: 0 0 10px #fff, 0 0 20px #fff, 0 0 30px #ff69b4;
            z-index: 1;
        }

        @keyframes sparkleAnim {
            0%, 100% { opacity: 0; transform: scale(0); }
            50% { opacity: 1; transform: scale(1); }
        }

        /* Sakura yaprakları */
        .petal {
            position: fixed;
            width: 20px;
            height: 20px;
            background: radial-gradient(ellipse at center, #ffb7d5 0%, #ffa0c9 50%, #ff8fb5 100%);
            border-radius: 50% 0 50% 0;
            opacity: 0.9;
            pointer-events: none;
            animation: fall linear infinite;
            z-index: 1;
            filter: drop-shadow(0 0 5px rgba(255, 105, 180, 0.5));
        }

        @keyframes fall {
            0% {
                transform: translateY(-100px) rotate(0deg) translateX(0);
                opacity: 1;
            }
            50% {
                transform: translateY(50vh) rotate(180deg) translateX(100px);
            }
            100% {
                transform: translateY(100vh) rotate(360deg) translateX(0);
                opacity: 0;
            }
        }

        /* Büyük sakura yaprakları */
        .petal-large {
            width: 30px;
            height: 30px;
            animation-duration: 8s;
        }

        /* Kalp şekilleri */
        .floating-heart {
            position: fixed;
            font-size: 30px;
            color: #ff1493;
            pointer-events: none;
            animation: floatUp 6s ease-in infinite;
            z-index: 1;
            opacity: 0.7;
            filter: drop-shadow(0 0 10px rgba(255, 20, 147, 0.8));
        }

        @keyframes floatUp {
            0% {
                transform: translateY(100vh) scale(0);
                opacity: 0;
            }
            20% {
                opacity: 0.7;
            }
            100% {
                transform: translateY(-100px) scale(1.5);
                opacity: 0;
            }
        }

        .container {
            position: relative;
            z-index: 2;
            max-width: 750px;
            margin: 50px 20px;
            background: rgba(255, 255, 255, 0.98);
            padding: 70px 60px;
            border-radius: 30px;
            box-shadow: 
                0 0 60px rgba(255, 105, 180, 0.4),
                0 0 100px rgba(255, 20, 147, 0.3),
                inset 0 0 80px rgba(255, 182, 193, 0.1);
            backdrop-filter: blur(20px);
            border: 3px solid rgba(255, 182, 193, 0.4);
            animation: containerPulse 3s ease-in-out infinite, fadeIn 2s ease-in-out;
            transform-style: preserve-3d;
        }

        @keyframes containerPulse {
            0%, 100% {
                box-shadow: 
                    0 0 60px rgba(255, 105, 180, 0.4),
                    0 0 100px rgba(255, 20, 147, 0.3),
                    inset 0 0 80px rgba(255, 182, 193, 0.1);
            }
            50% {
                box-shadow: 
                    0 0 80px rgba(255, 105, 180, 0.6),
                    0 0 120px rgba(255, 20, 147, 0.5),
                    inset 0 0 100px rgba(255, 182, 193, 0.2);
            }
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: scale(0.8) rotateX(20deg);
            }
            to {
                opacity: 1;
                transform: scale(1) rotateX(0deg);
            }
        }

        .header {
            text-align: center;
            margin-bottom: 50px;
            position: relative;
        }

        .sakura-icon {
            font-size: 80px;
            animation: iconFloat 3s ease-in-out infinite;
            filter: drop-shadow(0 0 20px rgba(255, 105, 180, 0.8));
            display: inline-block;
        }

        @keyframes iconFloat {
            0%, 100% {
                transform: translateY(0) rotate(0deg) scale(1);
            }
            25% {
                transform: translateY(-15px) rotate(-5deg) scale(1.1);
            }
            50% {
                transform: translateY(0) rotate(0deg) scale(1.15);
            }
            75% {
                transform: translateY(-15px) rotate(5deg) scale(1.1);
            }
        }

        h1 {
            color: #d946a6;
            font-size: 42px;
            margin: 25px 0 15px;
            font-weight: normal;
            letter-spacing: 3px;
            text-shadow: 
                0 0 10px rgba(255, 105, 180, 0.5),
                0 0 20px rgba(255, 105, 180, 0.3),
                2px 2px 4px rgba(0, 0, 0, 0.1);
            animation: titleGlow 2s ease-in-out infinite;
        }

        @keyframes titleGlow {
            0%, 100% {
                text-shadow: 
                    0 0 10px rgba(255, 105, 180, 0.5),
                    0 0 20px rgba(255, 105, 180, 0.3),
                    2px 2px 4px rgba(0, 0, 0, 0.1);
            }
            50% {
                text-shadow: 
                    0 0 20px rgba(255, 105, 180, 0.8),
                    0 0 40px rgba(255, 105, 180, 0.5),
                    2px 2px 4px rgba(0, 0, 0, 0.1);
            }
        }

        .subtitle {
            color: #e879b9;
            font-size: 20px;
            font-style: italic;
            animation: subtitleFade 3s ease-in-out infinite;
        }

        @keyframes subtitleFade {
            0%, 100% { opacity: 0.8; }
            50% { opacity: 1; }
        }

        .divider {
            width: 150px;
            height: 3px;
            background: linear-gradient(to right, transparent, #ff69b4, #ff1493, #ff69b4, transparent);
            margin: 40px auto;
            animation: dividerPulse 2s ease-in-out infinite;
            box-shadow: 0 0 10px rgba(255, 105, 180, 0.5);
        }

        @keyframes dividerPulse {
            0%, 100% {
                width: 150px;
                box-shadow: 0 0 10px rgba(255, 105, 180, 0.5);
            }
            50% {
                width: 180px;
                box-shadow: 0 0 20px rgba(255, 105, 180, 0.8);
            }
        }

        .letter-content {
            color: #4a4a4a;
            font-size: 19px;
            line-height: 2.2;
            text-align: justify;
            margin-bottom: 35px;
            position: relative;
        }

        .letter-content p {
            margin-bottom: 30px;
            animation: slideInGlow 1.5s ease-out forwards;
            opacity: 0;
            position: relative;
            padding: 15px;
            border-radius: 10px;
            transition: all 0.3s ease;
        }

        .letter-content p:hover {
            background: rgba(255, 182, 193, 0.1);
            transform: translateX(10px);
            box-shadow: -5px 0 15px rgba(255, 105, 180, 0.2);
        }

        .letter-content p:nth-child(1) { animation-delay: 0.5s; }
        .letter-content p:nth-child(2) { animation-delay: 1s; }
        .letter-content p:nth-child(3) { animation-delay: 1.5s; }
        .letter-content p:nth-child(4) { animation-delay: 2s; }

        @keyframes slideInGlow {
            from {
                opacity: 0;
                transform: translateY(30px) translateX(-20px);
                filter: blur(5px);
            }
            to {
                opacity: 1;
                transform: translateY(0) translateX(0);
                filter: blur(0);
            }
        }

        .signature {
            text-align: right;
            margin-top: 50px;
            font-size: 28px;
            color: #d946a6;
            font-style: italic;
            animation: signatureWrite 4s ease-in-out;
            text-shadow: 0 0 10px rgba(255, 105, 180, 0.5);
        }

        @keyframes signatureWrite {
            from {
                opacity: 0;
                transform: translateX(100px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .heart {
            display: inline-block;
            color: #ff1493;
            animation: heartbeatStrong 1.2s ease-in-out infinite;
            font-size: 24px;
            margin: 0 5px;
            filter: drop-shadow(0 0 10px rgba(255, 20, 147, 0.8));
        }

        @keyframes heartbeatStrong {
            0%, 100% {
                transform: scale(1);
            }
            10% {
                transform: scale(1.3);
            }
            20% {
                transform: scale(1);
            }
            30% {
                transform: scale(1.3);
            }
            40% {
                transform: scale(1);
            }
        }

        .footer {
            text-align: center;
            margin-top: 50px;
            padding-top: 35px;
            border-top: 2px solid rgba(255, 105, 180, 0.3);
            color: #e879b9;
            font-style: italic;
            font-size: 16px;
            animation: footerGlow 3s ease-in-out infinite;
        }

        @keyframes footerGlow {
            0%, 100% {
                text-shadow: 0 0 5px rgba(255, 105, 180, 0.3);
            }
            50% {
                text-shadow: 0 0 15px rgba(255, 105, 180, 0.6);
            }
        }

        /* Işık patlaması efekti */
        .light-burst {
            position: fixed;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(255, 255, 255, 0.8) 0%, transparent 70%);
            pointer-events: none;
            animation: burst 3s ease-out infinite;
            z-index: 0;
        }

        @keyframes burst {
            0% {
                transform: scale(0);
                opacity: 1;
            }
            100% {
                transform: scale(4);
                opacity: 0;
            }
        }

        /* Kelebek efekti */
        .butterfly {
            position: fixed;
            font-size: 25px;
            pointer-events: none;
            animation: butterflyFly 15s linear infinite;
            z-index: 1;
            filter: drop-shadow(0 0 5px rgba(255, 105, 180, 0.5));
        }

        @keyframes butterflyFly {
            0% {
                transform: translate(-100px, 100vh) rotate(0deg);
            }
            25% {
                transform: translate(30vw, 50vh) rotate(90deg);
            }
            50% {
                transform: translate(60vw, 20vh) rotate(180deg);
            }
            75% {
                transform: translate(80vw, 60vh) rotate(270deg);
            }
            100% {
                transform: translate(110vw, -100px) rotate(360deg);
            }
        }

        /* Yıldız efekti */
        .star {
            position: fixed;
            width: 3px;
            height: 3px;
            background: white;
            border-radius: 50%;
            pointer-events: none;
            animation: twinkle 2s ease-in-out infinite;
            box-shadow: 0 0 10px #fff, 0 0 20px #ff69b4;
            z-index: 1;
        }

        @keyframes twinkle {
            0%, 100% {
                opacity: 0;
                transform: scale(0);
            }
            50% {
                opacity: 1;
                transform: scale(1.5);
            }
        }
    </style>
</head>
<body>
    <!-- Işık patlamaları -->
    <div class="light-burst" style="top: 10%; left: 20%; animation-delay: 0s;"></div>
    <div class="light-burst" style="top: 60%; left: 70%; animation-delay: 1s;"></div>
    <div class="light-burst" style="top: 80%; left: 30%; animation-delay: 2s;"></div>

    <div class="container">
        <div class="header">
            <div class="sakura-icon">🌸</div>
            <h1>Sevgili Sakura'm</h1>
            <p class="subtitle">En Değerli Hazinemsin</p>
        </div>

        <div class="divider"></div>

        <div class="letter-content">
            <p>
                Hayatıma renk katan, kalbime huzur veren sen... Her sabah gözlerimi açtığımda aklıma gelen ilk şey sensin. Gülüşün benim için bahar sabahlarının en taze çiçekleri gibi, her seferinde içimi ısıtıyor, ruhumun en derin köşelerine kadar mutluluk dolduruyor.
            </p>
            
            <p>
                Seninle geçirdiğim her an, benim için bir hazine. Sessizce yan yana oturduğumuz anlar bile kelimelerle anlatılamayacak kadar değerli. Varlığın bile yeterli bana, çünkü sen sadece bir insan değilsin benim için; sen benim huzurumun, mutluluğumun ve umudumun kaynağısın. Seni düşündükçe yüreğim sakura yapraklarının rüzgarda dans ettiği gibi hafifliyor.
            </p>
            
            <p>
                Adın bile ne kadar güzel... Sakura. Tıpkı baharın gelişini müjdeleyen o narin, zarif çiçekler gibi. Sen de hayatıma öyle girdin işte; sessizce, zarif bir şekilde, ama öyle derin bir iz bıraktın ki, artık sensiz bir hayat düşünemiyorum bile. Her bakışında masumiyeti, her sözünde sevgiyi, her dokunuşunda sıcaklığı buluyorum.
            </p>
            
            <p>
                Bu mektubun her kelimesi, yüreğimin en derin yerinden geliyor. Seni seviyorum Sakura, kelimelerle ifade edilemeyecek kadar çok. Ve bilmeni istiyorum ki, sen benim için her şeyden daha kıymetlisin. Hayatımın baharı, kalbimin tek sahibi sensin. <span class="heart">♥</span>
            </p>
        </div>

        <div class="signature">
            Sonsuz sevgiyle,<br>
            Ateş <span class="heart">♥</span>
        </div>

        <div class="footer">
            Her anımız bir hazine, seninle her gün bahar 🌸
        </div>
    </div>

    <script>
        // Sakura yapraklarını oluştur
        function createPetal() {
            const petal = document.createElement('div');
            const isLarge = Math.random() > 0.7;
            petal.className = isLarge ? 'petal petal-large' : 'petal';
            petal.style.left = Math.random() * 100 + 'vw';
            petal.style.animationDuration = (Math.random() * 4 + 4) + 's';
            petal.style.animationDelay = Math.random() * 3 + 's';
            document.body.appendChild(petal);

            setTimeout(() => petal.remove(), 12000);
        }

        // Yüzen kalpler oluştur
        function createFloatingHeart() {
            const heart = document.createElement('div');
            heart.className = 'floating-heart';
            heart.textContent = '💕';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDelay = Math.random() * 3 + 's';
            document.body.appendChild(heart);

            setTimeout(() => heart.remove(), 6000);
        }

        // Parlama efekti oluştur
        function createSparkle() {
            const sparkle = document.createElement('div');
            sparkle.className = 'sparkle';
            sparkle.style.left = Math.random() * 100 + 'vw';
            sparkle.style.top = Math.random() * 100 + 'vh';
            sparkle.style.animationDelay = Math.random() * 2 + 's';
            document.body.appendChild(sparkle);

            setTimeout(() => sparkle.remove(), 2000);
        }

        // Kelebek oluştur
        function createButterfly() {
            const butterfly = document.createElement('div');
            butterfly.className = 'butterfly';
            butterfly.textContent = '🦋';
            butterfly.style.animationDelay = Math.random() * 5 + 's';
            document.body.appendChild(butterfly);

            setTimeout(() => butterfly.remove(), 15000);
        }

        // Yıldız oluştur
        function createStar() {
            const star = document.createElement('div');
            star.className = 'star';
            star.style.left = Math.random() * 100 + 'vw';
            star.style.top = Math.random() * 100 + 'vh';
            star.style.animationDelay = Math.random() * 2 + 's';
            document.body.appendChild(star);

            setTimeout(() => star.remove(), 2000);
        }

        // Sürekli efekt oluştur
        setInterval(createPetal, 200);
        setInterval(createFloatingHeart, 2000);
        setInterval(createSparkle, 500);
        setInterval(createButterfly, 8000);
        setInterval(createStar, 800);

        // Sayfa yüklendiğinde ilk efektler
        for (let i = 0; i < 25; i++) {
            setTimeout(createPetal, i * 100);
        }
        for (let i = 0; i < 15; i++) {
            setTimeout(createSparkle, i * 150);
        }
        for (let i = 0; i < 10; i++) {
            setTimeout(createStar, i * 200);
        }
        createButterfly();
        createButterfly();

        // Mouse hareketiyle parıltı efekti
        document.addEventListener('mousemove', (e) => {
            if (Math.random() > 0.9) {
                const sparkle = document.createElement('div');
                sparkle.className = 'sparkle';
                sparkle.style.left = e.pageX + 'px';
                sparkle.style.top = e.pageY + 'px';
                sparkle.style.position = 'absolute';
                document.body.appendChild(sparkle);
                setTimeout(() => sparkle.remove(), 2000);
            }
        });
    </script>
</body>
</html>
