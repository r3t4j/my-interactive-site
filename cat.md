<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مرحباً</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        #startButton {
            background-color: pink;
            border: none;
            padding: 20px 40px;
            font-size: 20px;
            cursor: pointer;
            border-radius: 10px;
        }
        #popup {
            display: none;
            position: absolute;
            background-color: white;
            border: 2px solid #000;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            left: 50%; /* initial left position */
            top: 50%; /* initial top position */
            transform: translate(-50%, -50%); /* center the popup */
        }
        #popup button {
            margin: 10px;
            padding: 10px;
            font-size: 16px;
            cursor: pointer;
        }
        #catImage {
            display: none;
            max-width: 100%;
            max-height: 500px;
        }
    </style>
</head>
<body>
    <button id="startButton">Start</button>
    <div id="popup">
        <p>Are you stupid?</p>
        <button id="noButton">No</button>
        <button id="yesButton">Yes</button>
    </div>
    <img id="catImage" src="https://i.imgur.com/uGcPmQW.jpeg" alt="Cute Cat">

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const startButton = document.getElementById('startButton');
            const popup = document.getElementById('popup');
            const noButton = document.getElementById('noButton');
            const yesButton = document.getElementById('yesButton');
            const catImage = document.getElementById('catImage');

            startButton.addEventListener('click', () => {
                popup.style.display = 'block'; // عرض المربع
                startButton.style.display = 'none'; // إخفاء زر "Start"
            });

            noButton.addEventListener('click', () => {
                movePopup();  // تحريك المربع عند الضغط على No
            });

            yesButton.addEventListener('click', () => {
                catImage.style.display = 'block';
                popup.style.display = 'none';
            });

            function movePopup() {
                let x = Math.random() * (window.innerWidth - 200);
                let y = Math.random() * (window.innerHeight - 100);
                popup.style.left = `${x}px`;
                popup.style.top = `${y}px`;
            }
        });
    </script>
</body>
</html>