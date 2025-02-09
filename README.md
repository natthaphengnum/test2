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
            background-color: #ffe6f2;
            color: #ff4081;
            margin: 0;
            padding: 20px;
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
    </style>
</head>
<body>

    <h1>สุขสันต์วันวาเลนไทน์นะที่รัก! 💘</h1>
    <p>ฉันมีบางอย่างอยากบอกเธอ...</p>
    <button onclick="showMessage()">กดเพื่อดูเซอร์ไพรส์! 🎁</button>
    
    <p id="message" class="hidden"></p>

    <button onclick="playMusic()">🎵 กดเพื่อเปิดเพลง</button>
    <iframe id="youtubePlayer" width="0" height="0" src="https://www.youtube.com/embed/jx28LXc3Yvw?enablejsapi=1" frameborder="0" allow="autoplay"></iframe>

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

        function playMusic() {
            var iframe = document.getElementById("youtubePlayer");
            iframe.src += "&autoplay=1";
        }
    </script>

</body>
</html>
