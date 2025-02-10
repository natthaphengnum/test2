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
            background: linear-gradient(to bottom, #0b1445, #1a237e, #3f51b5); /* พื้นหลังท้องฟ้ากลางคืน */
            color: #ff4081;
            margin: 0;
            padding: 20px;
            overflow: hidden;
            position: relative;
        }

        /* ก้อนเมฆลอย */
        .cloud {
            position: absolute;
            top: 10%;
            width: 100px;
            height: 50px;
            background: white;
            border-radius: 50%;
            opacity: 0.8;
            animation: moveClouds 20s linear infinite;
            box-shadow: 30px 10px 20px rgba(255, 255, 255, 0.5);
        }

        @keyframes moveClouds {
            0% { transform: translateX(-10vw); }
            100% { transform: translateX(110vw); }
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

        /* ดาวตก */
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
    <button onclick="showSurprise()">💌 กดเพื่อเซอร์ไพรส์</button>

    <div id="message" class="hidden">ฉันรักเธอนะ! ❤️</div>

    <div id="player"></div>

    <!-- ก้อนเมฆ -->
    <div class="cloud" style="top: 10%; left: 5%; width: 150px; height: 70px;"></div>
    <div class="cloud" style="top: 20%; left: 20%;"></div>
    <div class="cloud" style="top: 30%; left: 50%;"></div>
    <div class="cloud" style="top: 40%; left: 80%;"></div>

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

        // ดาวตกต่อเนื่อง
        function createShootingStars() {
            setInterval(() => {
                let star = document.createElement("div");
                star.classList.add("shooting-star");
                star.style.left = Math.random() * 100 + "vw";
                star.style.top = Math.random() * 50 + "vh";
                document.body.appendChild(star);
                setTimeout(() => star.remove(), 2000);
            }, 1000);
        }

        // ทำให้ดาวตกตลอดเวลา
        createShootingStars();

    </script>

</body>
</html>
