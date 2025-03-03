<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>三人游 - 颜文字播放器</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #f7f7f7;
        }
        .player {
            margin-top: 50px;
            display: inline-block;
            padding: 20px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .cd {
            font-size: 50px;
            display: block;
            transition: transform 0.5s ease-in-out;
        }
        .progress {
            margin: 10px 0;
        }
        .lyrics {
            display: none;
            margin-top: 20px;
            font-size: 14px;
            color: #666;
        }
        .rotate {
            animation: spin 2s linear infinite;
        }
        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
    </style>
</head>
<body>

    <div class="player">
        <div class="cd" ondblclick="rotateCD()">💿</div>
        <button onclick="togglePlay()">▶️</button>
        <div class="progress" onclick="fastForward()">▰▰▰▱</div>
        <button onclick="showLyrics()">♡</button>
        <audio id="audio" src="https://your-audio-url.com/sanrenyou.mp3"></audio>
        <div class="lyrics">🎵 我们的爱~ 差一点变成阻碍 🎵</div>
    </div>

    <script>
        const audio = document.getElementById("audio");
        const cd = document.querySelector(".cd");
        const lyrics = document.querySelector(".lyrics");

        function togglePlay() {
            if (audio.paused) {
                audio.play();
            } else {
                audio.pause();
            }
        }

        function fastForward() {
            audio.currentTime += 10;
        }

        function showLyrics() {
            lyrics.style.display = lyrics.style.display === "none" ? "block" : "none";
        }

        function rotateCD() {
            cd.classList.toggle("rotate");
        }
    </script>

</body>
</html>
