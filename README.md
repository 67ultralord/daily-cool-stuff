# daily-cool-stuff
check read me

<!DOCTYPE html>
<html>
<head>
    <title>Research Portal</title>
    <style>
        body { margin: 0; font-family: sans-serif; background: #111; color: white; display: flex; flex-direction: column; height: 100vh; overflow: hidden; }
        .nav { padding: 10px; background: #222; display: flex; gap: 10px; z-index: 100; }
        input { flex: 1; padding: 8px; border-radius: 4px; border: 1px solid #444; background: #333; color: white; }
        button { padding: 8px 15px; background: #007bff; color: white; border: none; border-radius: 4px; cursor: pointer; }
        iframe { flex: 1; width: 100%; border: none; }
    </style>
</head>
<body>
    <div class="nav">
        <input type="text" id="urlInput" placeholder="Paste YouTube link here...">
        <button onclick="loadVideo()">Watch</button>
    </div>
    <iframe id="player" src="https://www.youtube-nocookie.com/embed/e_eQQjfhR_k" allowfullscreen></iframe>

    <script>
        function loadVideo() {
            let input = document.getElementById('urlInput').value;
            let videoId = "";
            
            if (input.includes('v=')) {
                videoId = input.split('v=')[1].split('&')[0];
            } else if (input.includes('be/')) {
                videoId = input.split('be/')[1].split('?')[0];
            } else {
                alert("Please paste a valid YouTube link!");
                return;
            }
            
            document.getElementById('player').src = "https://www.youtube-nocookie.com/embed/" + videoId;
        }
    </script>
</body>
</html>
