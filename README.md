# test2
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>💖 Surprise for You 💖</title>
    <style>
        body {
            text-align: center;
            font-family: 'Arial', sans-serif;
            background-color: #ffcccc; /* พื้นหลังสีแดงอ่อน */
            color: #ff4081;
            margin: 0;
            padding: 20px;
            overflow: hidden; /* ป้องกันการเลื่อนหน้าจอ */
            position: relative;
        }
        h1 {
            font-size: 28px;
            margin-top: 50px;
        }
        .hidden {
            display: none;
        }
        button {
            background-color: #ff4081;
            color: white;
            border: none;
            padding: 15px 20px;
            font-size: 18px;
            cursor: pointer;
            border-radius: 8px;
            margin-top: 20px;
        }
        button:hover {
            background-color: #e91e63;
        }
        #message {
            font-size: 22px;
            font-weight: bold;
            white-space: pre-line;
            display: inline-block;
        }

        /* เอฟเฟกต์หัวใจลอย */
        .heart {
            position: absolute;
            color: red;
            font-size: 24px;
            animation: floatUp 4s linear infinite;
        }
        @keyframes floatUp {
            0% {
                transform: translateY(0);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh);
                opacity: 0;
            }
        }

        /* เอฟเฟกต์ดาวตก */
        .shooting-star {
            position: absolute;
            width: 5px;
            height: 5px;
            background-color: pink;
            box-shadow: 0 0 8px pink;
            border-radius: 50%;
            animation: shootingStar 2s linear infinite;
        }
        @keyframes shootingStar {
            0% {
                transform: translate(100vw, -10vh);
                opacity: 1;
            }
            100% {
                transform: translate(-10vw, 100vh);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <h1>สุขสันต์วันวาเลนไทน์นะที่รัก! 💘</h1>
    <p>ฉันมีบางอย่างอยากบอกเธอ...</p>
    <button onclick="showMessage()">กดเพื่อดูเซอร์ไพรส์! 🎁</button>
    
    <p id="message" class="hidden"></p>

    <button onclick="playMusic()">🎵 กดเพื่อเปิดเพลง</button>
    <div id="player"></div>

    <script>
        function showMessage() {
            const message = "รักเธอที่สุดเลยนะ 💖\nขอบคุณที่อยู่ด้วยกันเสมอ 💕\nขอให้วันนี้เป็นวันที่พิเศษของเรา!";
            let i = 0;
            const textDisplay = document.getElementById("message");
            textDisplay.classList.remove("hidden");
            textDisplay.innerHTML = "";

            function typeWriter() {
                if (i < message.length) {
                    textDisplay.innerHTML += message.charAt(i);
                    i++;
                    setTimeout(typeWriter, 50);
                }
            }
            typeWriter();
        }

        // โหลด YouTube API
        var tag = document.createElement('script');
        tag.src = "https://www.youtube.com/iframe_api";
        var firstScriptTag = document.getElementsByTagName('script')[0];
        firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

        var player;
        function onYouTubeIframeAPIReady() {
            player = new YT.Player('player', {
                height: '0',
                width: '0',
                videoId: 'jx28LXc3Yvw', // ใส่ ID วิดีโอ YouTube
                playerVars: { 'autoplay': 0, 'loop': 1, 'playlist': 'jx28LXc3Yvw' }
            });
        }

        function playMusic() {
            if (player) {
                player.playVideo(); // เล่นเพลงเมื่อกดปุ่ม
                startHearts(); // เริ่มหัวใจลอยขึ้น
                startShootingStars(); // เริ่มดาวตก
            }
        }

        // ฟังก์ชันสร้างหัวใจลอยขึ้น
        function startHearts() {
            setInterval(() => {
                let heart = document.createElement("div");
                heart.className = "heart";
                heart.innerHTML = "❤️";
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.fontSize = Math.random() * 20 + 20 + "px";
                heart.style.animationDuration = Math.random() * 3 + 2 + "s";
                document.body.appendChild(heart);

                setTimeout(() => {
                    heart.remove();
                }, 4000);
            }, 300);
        }

        // ฟังก์ชันสร้างดาวตก
        function startShootingStars() {
            setInterval(() => {
                let star = document.createElement("div");
                star.className = "shooting-star";
                star.style.left = Math.random() * 100 + "vw";
                star.style.top = Math.random() * 50 + "vh";
                star.style.animationDuration = Math.random() * 2 + 1 + "s";
                document.body.appendChild(star);

                setTimeout(() => {
                    star.remove();
                }, 2000);
            }, 500);
        }
    </script>

</body>
</html>
