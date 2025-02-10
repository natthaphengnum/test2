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
    <button onclick="playMusic()">🎵 กดเพื่อเปิดเพลง</button>
    
    <div class="record-container">
        <div class="record">
            <img src="https://yt3.googleusercontent.com/ytc/AIdro_mOnqMkA1pfhFtKyvH7aMlFsx5OaOeQH5RbGykb7w=s900-c-k-c0x00ffffff-no-rj" alt="Album Cover">
        </div>
    </div>
    <p class="
