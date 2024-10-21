<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Diwali!</title>
    <style>
        body {
            background-color: #000;
            color: white;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: 'Arial', sans-serif;
        }
        .container {
            text-align: center;
        }
        .firework {
            position: absolute;
            border-radius: 50%;
            pointer-events: none;
            opacity: 0.8;
            animation: explode 1s forwards;
        }
        @keyframes explode {
            0% {
                transform: scale(0);
                opacity: 0.8;
            }
            50% {
                transform: scale(1);
                opacity: 1;
            }
            100% {
                transform: scale(0);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Happy Diwali!</h1>
        <button id="firecrackerButton">🎆 Light Firecracker</button>
        <div id="fireworkContainer"></div>
    </div>
    <script>
        document.getElementById('firecrackerButton').addEventListener('click', createFirecracker);

        function createFirecracker() {
            const fireworkContainer = document.getElementById('fireworkContainer');
            const firework = document.createElement('div');
            firework.className = 'firework';
            firework.style.width = `${Math.random() * 50 + 20}px`;
            firework.style.height = firework.style.width;
            firework.style.backgroundColor = getRandomColor();
            firework.style.left = `${Math.random() * window.innerWidth}px`;
            firework.style.top = `${Math.random() * window.innerHeight}px`;
            fireworkContainer.appendChild(firework);

            // Remove firework after animation ends
            firework.addEventListener('animationend', () => {
                fireworkContainer.removeChild(firework);
            });
        }

        function getRandomColor() {
            const letters = '0123456789ABCDEF';
            let color = '#';
            for (let i = 0; i < 6; i++) {
                color += letters[Math.floor(Math.random() * 16)];
            }
            return color;
        }
    </script>
</body>
</html>


<!---
bindeshmishra/bindeshmishra is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
