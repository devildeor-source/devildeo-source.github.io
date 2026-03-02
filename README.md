 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>For Someone Special</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300&display=swap" rel="stylesheet">
    <style>
        body, html {
            margin: 0; padding: 0;
            width: 100%; height: 100%;
            overflow: hidden;
            background: #000;
        }

        /* Video-like background */
        #bg {
            position: fixed;
            width: 100%; height: 100%;
            background: url('https://images.unsplash.com/photo-1522383225653-ed111181a951?auto=format&fit=crop&w=1080&q=80') no-repeat center center;
            background-size: cover;
            transition: all 1.2s ease;
            z-index: -1;
        }

        /* The Card */
        .card-container {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .card {
            width: 85%;
            height: 60%;
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 20px;
            position: relative;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
            text-align: center;
            padding: 20px;
            color: white;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        h1 { font-family: 'Dancing Script', cursive; font-size: 2.5rem; margin: 10px 0; color: #ffb7c5; }
        p { font-family: 'Poppins', sans-serif; font-size: 1.1rem; line-height: 1.6; }

        /* Falling Petals */
        .petal {
            position: absolute;
            background-color: #ffb7c5;
            border-radius: 150% 0 150% 0;
            opacity: 0.6;
            pointer-events: none;
            animation: fall linear infinite;
        }

        @keyframes fall {
            0% { transform: translateY(-10vh) rotate(0deg); }
            100% { transform: translateY(110vh) rotate(360deg); }
        }

        .btn {
            margin-top: 20px;
            padding: 10px 25px;
            background: #ffb7c5;
            border: none;
            border-radius: 25px;
            color: #4a0e2e;
            font-weight: bold;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <div id="bg"></div>

    <div class="card-container">
        <div class="card" id="card">
            <div id="content">
                <h1>Happy Birthday! 🌸</h1>
                <p>To the person who makes life beautiful.</p>
                <button class="btn" onclick="nextPage()">Click for Surprise</button>
            </div>
        </div>
    </div>

    <script>
        function nextPage() {
            const bg = document.getElementById('bg');
            const content = document.getElementById('content');
            
            // Animate background change like the video transition
            bg.style.backgroundImage = "url('https://images.unsplash.com/photo-1493976040374-85c8e12f0c0e?auto=format&fit=crop&w=1080&q=80')";
            
            content.innerHTML = `
                <h1 style="animation: fadeIn 1s">Forever Special 💖</h1>
                <p style="animation: fadeIn 1.5s">May your year be full of blooms and joy!</p>
            `;
        }

        function createPetal() {
            const petal = document.createElement('div');
            petal.classList.add('petal');
            const size = Math.random() * 7 + 5 + 'px';
            petal.style.width = size;
            petal.style.height = size;
            petal.style.left = Math.random() * 100 + 'vw';
            petal.style.animationDuration = Math.random() * 2 + 3 + 's';
            document.body.appendChild(petal);
            setTimeout(() => petal.remove(), 5000);
        }
        setInterval(createPetal, 200);
    </script>
</body>
</html>
