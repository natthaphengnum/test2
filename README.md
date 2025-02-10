# You Are My Valentine
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

        /* แผ่นเสียงหมุน */
        .record-container {
            position: relative;
            width: 200px;
            height: 200px;
            margin: 20px auto;
        }
        .record {
            width: 100%;
            height: 100%;
            background: url('https://cdn.pixabay.com/photo/2020/04/16/21/21/vinyl-5054260_1280.png') no-repeat center;
            background-size: cover;
            border-radius: 50%;
            animation: spin 4s linear infinite;
        }
        .record img {
            position: absolute;
            width: 80px;
            height: 80px;
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        .song-title {
            font-size: 18px;
            font-weight: bold;
            margin-top: 10px;
            color: white;
        }

        /* ข้อความเซอร์ไพรส์ */
        #message {
            font-size: 22px;
            font-weight: bold;
            color: white;
            margin-top: 20px;
            display: none;
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
    <button onclick="showSurprise()">💌 กดเพื่อเซอร์ไพรส์</button>

    <div id="message" class="hidden">ฉันรักเธอนะ! ❤️</div>

    <div class="record-container">
        <div class="record">
            <img src="https://yt3.googleusercontent.com/ytc/AIdro_mOnqMkA1pfhFtKyvH7aMlFsx5OaOeQH5RbGykb7w=s900-c-k-c0x00ffffff-no-rj" alt="Album Cover">
        </div>
    </div>
    <p class="song-title">💖 เพลง: The Loveliest Time - Carly Rae Jepsen 💖</p>

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
                videoId: 'jx28LXc3Yvw', // ใส่ ID วิดีโอ YouTube
                playerVars: { 'autoplay': 0, 'loop': 1, 'playlist': 'jx28LXc3Yvw' }
            });
        }

        function showSurprise() {
            document.getElementById('message').style.display = "block";
            playMusic();
            createFloatingHearts();
        }

        function playMusic() {
            if (player) {
                player.playVideo();
            }
        }

        // หัวใจลอยขึ้น
        function createFloatingHearts() {
            setInterval(() => {
                let heart = document.createElement("div");
                heart.innerHTML = "❤️";
                heart.classList.add("heart");
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.top = "100vh";
                heart.style.position = "absolute";
                heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
                document.body.appendChild(heart);
                setTimeout(() => heart.remove(), 4000);
            }, 500);
        }

        // ดาวตก (ทำให้ตกตลอดเวลา)
        function createShootingStars() {
            setInterval(() => {
                let star = document.createElement("div");
                star.classList.add("shooting-star");
                star.style.left = Math.random() * 100 + "vw";
                star.style.top = Math.random() * 50 + "vh";
                document.body.appendChild(star);
                setTimeout(() => star.remove(), 2000);
            }, 1000); // ดาวตกทุกๆ 1 วินาที
        }

        // ทำให้ดาวตกตลอดเวลาเมื่อโหลดหน้าเว็บ
        createShootingStars();
    </script>

</body>
</html>
