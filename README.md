# valentine-site
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine?</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ffe6e6;
            font-family: Arial, sans-serif;
            text-align: center;
            background-image: url('eiffel-tower.jpg');
            background-size: cover;
            background-position: center;
        }
        h1 {
            color: #ff4d6d;
        }
        .buttons {
            position: relative;
            display: flex;
            gap: 20px;
            margin-top: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 18px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            transition: 0.3s ease-in-out;
        }
        .yes {
            background-color: #ff4d6d;
            color: white;
        }
        .no {
            background-color: #ccc;
            color: black;
            position: absolute;
        }
        .hidden {
            display: none;
        }
        img {
            max-width: 300px;
            border-radius: 10px;
            margin-bottom: 20px;
        }
        .fallback {
            font-size: 20px;
            color: #444;
            margin-top: 10px;
        }
        .harry-potter {
            font-family: 'Harry Potter', sans-serif;
            font-size: 24px;
            color: #ffcc00;
            margin-top: 10px;
        }
        .cricket-bat {
            width: 100px;
            height: auto;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div id="start-screen">
        <div id="image-container">
            <img src="DSC_1327.JPG" alt="Wearing glasses" onerror="showFallback('start')">
            <p id="fallback-start" class="fallback hidden">😎 Imagine me looking cool with glasses</p>
        </div>
        <h1 class="harry-potter">Will you be my Valentine? ⚡</h1>
        <div class="buttons">
            <button class="yes" onclick="showWin()">Yes</button>
            <button class="no" onmouseover="moveButton()">No</button>
        </div>
        <img src="cricket-bat.png" class="cricket-bat" alt="Cricket Bat" onerror="showFallback('cricket')">
    </div>
    
    <div id="win-screen" class="hidden">
        <div id="win-image-container">
            <img src="WIN_20240704_23_59_18_Pro.jpg" alt="Flexing bicep" onerror="showFallback('win')">
            <p id="fallback-win" class="fallback hidden">💪 I'll take care of you 🖤</p>
        </div>
        <h1>I'll take care of you 🖤</h1>
    </div>

    <script>
        function moveButton() {
            const noButton = document.querySelector('.no');
            const x = Math.random() * (window.innerWidth - 100);
            const y = Math.random() * (window.innerHeight - 50);
            noButton.style.left = `${x}px`;
            noButton.style.top = `${y}px`;
        }

        function showWin() {
            document.getElementById('start-screen').classList.add('hidden');
            document.getElementById('win-screen').classList.remove('hidden');
        }

        function showFallback(type) {
            document.getElementById(`fallback-${type}`).classList.remove('hidden');
        }
    </script>
</body>
</html>
