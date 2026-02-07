<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Dipanjali</title>
    <style>
        :root {
            --rose-red: #ff4d6d;
            --stem-green: #2d6a4f;
        }

        body {
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: radial-gradient(circle at center, #1a0a0d 0%, #000000 100%);
            overflow: hidden;
            font-family: 'Palatino', serif;
        }

        /* Floating Stars Background */
        .stars {
            position: absolute;
            width: 100%;
            height: 100%;
            background: transparent;
            z-index: 0;
        }

        /* The Rose Construction */
        .rose {
            position: relative;
            transform: scale(1.2);
            margin-bottom: 40px;
            animation: float 3s ease-in-out infinite;
        }

        .flower {
            position: relative;
            width: 50px;
            height: 50px;
            background: var(--rose-red);
            border-radius: 50%;
            box-shadow: 0 0 20px var(--rose-red);
        }

        .flower::after {
            content: '';
            position: absolute;
            width: 50px;
            height: 50px;
            background: var(--rose-red);
            border-radius: 50% 0 50% 50%;
            transform: rotate(-45deg);
            top: -10px;
        }

        .stem {
            width: 4px;
            height: 100px;
            background: var(--stem-green);
            margin: 0 auto;
            position: relative;
        }

        .leaf {
            width: 30px;
            height: 15px;
            background: var(--stem-green);
            border-radius: 50% 0;
            position: absolute;
            left: 4px;
            top: 30px;
            transform: rotate(-20deg);
        }

        /* Content Card */
        .container {
            z-index: 10;
            text-align: center;
            color: white;
            padding: 20px;
        }

        h1 {
            font-size: 2.5rem;
            margin: 10px 0;
            background: linear-gradient(to right, #ff4d6d, #ffb3c1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            opacity: 0;
            animation: fadeIn 2s forwards 1s;
        }

        .typing-container {
            font-size: 1.2rem;
            min-height: 3em;
            max-width: 300px;
            margin: 0 auto;
            color: #ffb3c1;
            line-height: 1.5;
        }

        /* Animations */
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-15px) rotate(2deg); }
        }

        @keyframes fadeIn {
            to { opacity: 1; }
        }

        /* The Heart beat button */
        .btn {
            margin-top: 30px;
            padding: 12px 25px;
            background: var(--rose-red);
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            box-shadow: 0 0 15px var(--rose-red);
            transition: 0.3s;
            opacity: 0;
            animation: fadeIn 2s forwards 4s;
        }

        .btn:hover {
            transform: scale(1.1);
            box-shadow: 0 0 25px var(--rose-red);
        }
    </style>
</head>
<body>

    <div class="stars" id="starField"></div>

    <div class="container">
        <div class="rose">
            <div class="flower"></div>
            <div class="stem"><div class="leaf"></div></div>
        </div>

        <h1>Happy Rose Day, Dipanjali</h1>
        
        <div class="typing-container" id="text"></div>

        <button class="btn" onclick="revealExtra()">Click for a surprise</button>
    </div>

    <script>
        // Typing Effect
        const message = "A million roses wouldn't be enough to show you how much you mean to me. You are my forever bloom, Dipanjali.";
        let i = 0;
        function typeWriter() {
            if (i < message.length) {
                document.getElementById("text").innerHTML += message.charAt(i);
                i++;
                setTimeout(typeWriter, 50);
            }
        }
        
        // Start typing after a delay
        setTimeout(typeWriter, 2000);

        // Generate stars
        const starField = document.getElementById('starField');
        for (let i = 0; i < 100; i++) {
            const star = document.createElement('div');
            star.style.position = 'absolute';
            star.style.left = Math.random() * 100 + '%';
            star.style.top = Math.random() * 100 + '%';
            star.style.width = '2px';
            star.style.height = '2px';
            star.style.background = 'white';
            star.style.borderRadius = '50%';
            star.style.opacity = Math.random();
            starField.appendChild(star);
        }

        function revealExtra() {
            alert("I love you more than words can say, Dipanjali! ❤️");
        }
    </script>
</body>
</html>
