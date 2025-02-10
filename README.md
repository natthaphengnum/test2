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

        /* เอฟเฟกต์ดาว
