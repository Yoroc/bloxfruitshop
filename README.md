<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blox Fruits Shop & Mirage Timer</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: #f0f8ff;
            color: #333;
            text-align: center;
        }
        header {
            background: #4caf50;
            color: white;
            padding: 1rem 0;
        }
        .container {
            margin: 2rem auto;
            padding: 1rem;
            max-width: 800px;
            background: white;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
        }
        .shop {
            margin: 2rem 0;
        }
        .timer {
            font-size: 2rem;
            margin: 2rem 0;
            color: #ff5722;
        }
        .footer {
            margin-top: 2rem;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>
    <header>
        <h1>Blox Fruits Shop & Mirage Timer</h1>
    </header>
    <div class="container">
        <section class="shop">
            <h2>Blox Fruits Storage Shop</h2>
            <ul>
                <li><strong>Dragon Fruit</strong> - 1,500 Robux</li>
                <li><strong>Leopard Fruit</strong> - 3,000 Robux</li>
                <li><strong>Shadow Fruit</strong> - 1,200 Robux</li>
                <li><strong>Venom Fruit</strong> - 2,000 Robux</li>
            </ul>
        </section>
        <section class="timer">
            <h2>Mirage Island Timer</h2>
            <p id="countdown">Loading...</p>
        </section>
    </div>
    <footer class="footer">
        <p>Created by Yoroc. Powered by GitHub Pages.</p>
    </footer>
    <script>
        function startTimer(duration, display) {
            let timer = duration, hours, minutes, seconds;
            setInterval(() => {
                hours = Math.floor(timer / 3600);
                minutes = Math.floor((timer % 3600) / 60);
                seconds = timer % 60;

                hours = hours < 10 ? "0" + hours : hours;
                minutes = minutes < 10 ? "0" + minutes : minutes;
                seconds = seconds < 10 ? "0" + seconds : seconds;

                display.textContent = `${hours}:${minutes}:${seconds}`;

                if (--timer < 0) {
                    timer = duration; // Reset timer
                }
            }, 1000);
        }

        window.onload = () => {
            const mirageDuration = 3600; // Example: 1 hour in seconds
            const display = document.querySelector('#countdown');
            startTimer(mirageDuration, display);
        };
    </script>
</body>
</html>
