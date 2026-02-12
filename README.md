<!DOCTYPE html>
<html>
<head>
    <title>Happy Valentine's Day ❤️</title>
    <style>
        body {
            text-align: center;
            background-color: #ffccd5;
            font-family: Arial, sans-serif;
            overflow: hidden;
        }

        h1 {
            color: #d6336c;
            margin-top: 100px;
        }

        button {
            padding: 15px 25px;
            font-size: 18px;
            background-color: #ff4d6d;
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            margin: 10px;
        }

        button:hover {
            background-color: #c9184a;
        }

        .heart {
            position: fixed;
            font-size: 24px;
            animation: floatUp 3s linear forwards;
        }

        @keyframes floatUp {
            from {
                transform: translateY(0);
                opacity: 1;
            }
            to {
                transform: translateY(-200px);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <h1>Will You Be My Valentine? ❤️</h1>

    <button onclick="showLove()">Yes 💖</button>
    <button id="noBtn" onmouseover="moveButton()">No 😢</button>
    <br>
    <button onclick="downloadLetter()">Download Love Letter 💌</button>

    <script>
        function showLove() {
            alert("Yay! I Love You ❤️😍");

            for (let i = 0; i < 15; i++) {
                const heart = document.createElement("div");
                heart.classList.add("heart");
                heart.innerHTML = "❤️";
                heart.style.left = Math.random() * window.innerWidth + "px";
                heart.style.top = window.innerHeight + "px";
                document.body.appendChild(heart);

                setTimeout(() => heart.remove(), 3000);
            }
        }

        function moveButton() {
            const button = document.getElementById("noBtn");
            const x = Math.random() * (window.innerWidth - 100);
            const y = Math.random() * (window.innerHeight - 50);

            button.style.position = "absolute";
            button.style.left = x + "px";
            button.style.top = y + "px";
        }

        function downloadLetter() {
            const text = 
`My Love ❤️

Happy Valentine's Day!

You mean the world to me.
Every moment with you is special,
and I am so lucky to have you in my life.

Forever yours 💖`;

            const blob = new Blob([text], { type: "text/plain" });
            const link = document.createElement("a");
            link.href = URL.createObjectURL(blob);
            link.download = "Love_Letter.txt";
            link.click();
        }
    </script>

</body>
</html>
