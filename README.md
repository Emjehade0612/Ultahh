# Ultahh
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Selamat Ulang Tahun Pipiii!</title>
    <style>
        body {
            background-color: #2c3e50;
            color: #ecf0f1;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            height: 100vh;
            margin: 0;
            font-family: 'Arial', sans-serif;
            text-align: center;
            overflow: hidden;
        }
        h1 {
            font-size: 4em;
            margin: 0;
            animation: bounce 1s infinite;
        }
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0);
            }
            40% {
                transform: translateY(-20px);
            }
            60% {
                transform: translateY(-10px);
            }
        }
        .balloons {
            position: absolute;
            top: 10%;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
        }
        .balloon {
            width: 50px;
            height: 70px;
            border-radius: 50% 50% 0 0;
            display: inline-block;
            margin: 10px;
            position: relative;
            animation: float 3s ease-in-out infinite;
        }
        @keyframes float {
            0% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0); }
        }
        .balloon:after {
            content: '';
            width: 5px;
            height: 30px;
            background-color: #34495e;
            position: absolute;
            bottom: -30px;
            left: 50%;
            transform: translateX(-50%);
        }
        .confetti {
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            pointer-events: none;
        }
        .confetti-piece {
            width: 10px;
            height: 10px;
            background-color: #f39c12;
            position: absolute;
            animation: fall linear infinite;
        }
        @keyframes fall {
            0% { transform: translateY(0); }
            100% { transform: translateY(100vh); }
        }
    </style>
</head>
<body>
    <div class="balloons">
        <div class="balloon" style="background-color: #e74c3c;"></div>
        <div class="balloon" style="background-color: #f1c40f;"></div>
        <div class="balloon" style="background-color: #2ecc71;"></div>
        <div class="balloon" style="background-color: #3498db;"></div>
        <div class="balloon" style="background-color: #9b59b6;"></div>
    </div>
    <h1>Selamat Ulang Tahun Pipiii!!!</h1>
    <div class="confetti"></div>
    <script>
        // Generate confetti
        function createConfetti() {
            const confettiContainer = document.querySelector('.confetti');
            for (let i = 0; i < 100; i++) {
                const confetti = document.createElement('div');
                confetti.className = 'confetti-piece';
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.backgroundColor = `hsl(${Math.random() * 360}, 100%, 50%)`;
                confetti.style.animationDuration = Math.random() * 1 + 2 + 's';
                confetti.style.animationDelay = Math.random() * 5 + 's';
                confettiContainer.appendChild(confetti);
            }
        }

        // Play sound on click
        const audio = new Audio('https://www.soundjay.com/button/sounds/button-16.mp3');
        document.body.addEventListener('click', function() {
            audio.currentTime = 0; // Restart sound on each click
            audio.play();
            alert('Selamat Ulang Tahun Pipiii! Semoga semua harapanmu terwujud!');
        });

        createConfetti();
    </script>
</body>
</html>
