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
            background: linear-gradient(to bottom, #0b1445, #1a237e, #3f51b5);
            color: #ff4081;
            margin: 0;
            padding: 20px;
            overflow: hidden;
            position: relative;
        }
        h1 {
            font-size: 28px;
            margin-top: 50px;
            color: white;
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
        /* เอฟเฟกต์ดาวหาง */
        .comet {
            position: absolute;
            width: 5px;
            height: 5px;
            background-color: pink;
            box-shadow: 0 0 15px pink;
            border-radius: 50%;
            animation: comet 2.5s linear infinite;
        }
        @keyframes shootingStar {
            0% { transform: translate(100vw, -10vh); opacity: 1; }
            100% { transform: translate(-10vw, 100vh); opacity: 0; }
        }
        @keyframes comet {
            0% { transform: translate(120vw, -20vh) scaleX(1); opacity: 1; }
            100% { transform: translate(-20vw, 120vh) scaleX(2); opacity: 0; }
        }
    </style>
</head>
<body>

    <h1>สุขสันต์วันวาเลนไทน์นะที่รัก! 💘</h1>
    <button onclick="showSurprise()">💌 กดเพื่อเซอร์ไพรส์</button>

    <div id="message" class="hidden">ฉันรักเธอนะ! ❤️</div>

    <div id="player"></div>

    <script>
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
                videoId: 'jx28LXc3Yvw',
                playerVars: { 'autoplay': 0, 'loop': 1, 'playlist': 'jx28LXc3Yvw' }
            });
        }

        function showSurprise() {
            document.getElementById('message').style.display = "block";
            playMusic();
        }

        function playMusic() {
            if (player) {
                player.playVideo();
            }
        }

        // ดาวตกต่อเนื่อง + ดาวหาง
        function createShootingStars() {
            setInterval(() => {
                let star = document.createElement("div");
                let isComet = Math.random() > 0.7; // 30% เป็นดาวหาง
                star.classList.add(isComet ? "comet" : "shooting-star");
                star.style.left = Math.random() * 100 + "vw";
                star.style.top = Math.random() * 50 + "vh";
                document.body.appendChild(star);
                setTimeout(() => star.remove(), 2500);
            }, 500); // เพิ่มความถี่ให้ถี่ขึ้น (0.5 วินาที)
        }

        createShootingStars();
    </script>

</body>
</html>
