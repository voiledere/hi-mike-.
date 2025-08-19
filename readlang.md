<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To My Dearest Mike ❤️</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }

        .container {
            text-align: center;
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
            animation: fadeIn 1.5s ease-in-out;
            max-width: 600px;
        }

        h1 {
            font-size: 2.5rem;
            color: #e91e63;
            margin-bottom: 20px;
        }

        p {
            font-size: 1.2rem;
            color: #444;
            line-height: 1.6;
        }

        .heart {
            font-size: 3rem;
            animation: pulse 1s infinite;
            color: #ff1744;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.3); }
            100% { transform: scale(1); }
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Confetti canvas */
        canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
    </style>
</head>
<body>
    <canvas id="confetti"></canvas>
    <div class="container">
        <h1>To My Dearest Mike ❤️</h1>
        <p>
            You are the light of my world and you have made me the happiest.  
            You made me feel seen, heard, accepted and loved.  
            If you think you are not lovable, too much and childish; you are wrong.  
            You are the one who brings out the best in me and you make me smile talaga.  
            Hays, I am speechless but we talked about this earlier,  
            I hope you felt it and I hope this one will put a smile on your cute baby face.  
            Hahah. I love you so much, dearest Mike. Happy Monthsary again!  
        </p>
        <div class="heart">❤️</div>
    </div>

    <script>
        // Confetti Animation
        const confetti = document.getElementById('confetti');
        const ctx = confetti.getContext('2d');
        confetti.width = window.innerWidth;
        confetti.height = window.innerHeight;

        const pieces = [];
        const colors = ['#fce18a', '#ff726d', '#b48def', '#f4306d', '#3dd1e7'];

        function createPiece() {
            return {
                x: Math.random() * confetti.width,
                y: Math.random() * confetti.height - confetti.height,
                size: Math.random() * 10 + 5,
                color: colors[Math.floor(Math.random() * colors.length)],
                speed: Math.random() + 1
            };
        }

        function update() {
            ctx.clearRect(0, 0, confetti.width, confetti.height);
            pieces.forEach(p => {
                p.y += p.speed;
                if (p.y > confetti.height) {
                    p.y = 0 - p.size;
                    p.x = Math.random() * confetti.width;
                }
                ctx.fillStyle = p.color;
                ctx.fillRect(p.x, p.y, p.size, p.size);
            });
            requestAnimationFrame(update);
        }

        for (let i = 0; i < 150; i++) {
            pieces.push(createPiece());
        }

        update();
    </script>
</body>
</html>
