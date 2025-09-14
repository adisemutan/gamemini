<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Game Klik Cepat</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background: #f0f8ff;
      margin: 0;
      height: 100vh;
      overflow: hidden;
    }
    h1 {
      margin-top: 20px;
    }
    #gameArea {
      position: relative;
      width: 100%;
      height: 80vh;
      border: 2px solid #333;
      margin-top: 20px;
      background: #fff;
      overflow: hidden;
    }
    #target {
      position: absolute;
      padding: 15px 25px;
      background: #4caf50;
      color: white;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      display: none;
    }
    #score {
      font-size: 20px;
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <h1>🎯 Game Klik Cepat</h1>
  <p>Klik tombol hijau sebelum pindah!</p>
  <div id="score">Skor: 0</div>
  <div id="gameArea">
    <button id="target">Klik!</button>
  </div>

  <script>
    const target = document.getElementById("target");
    const scoreDisplay = document.getElementById("score");
    const gameArea = document.getElementById("gameArea");
    let score = 0;

    function randomPosition() {
      const areaWidth = gameArea.clientWidth - target.offsetWidth;
      const areaHeight = gameArea.clientHeight - target.offsetHeight;
      const x = Math.floor(Math.random() * areaWidth);
      const y = Math.floor(Math.random() * areaHeight);
      target.style.left = x + "px";
      target.style.top = y + "px";
      target.style.display = "block";
    }

    target.addEventListener("click", () => {
      score++;
      scoreDisplay.textContent = "Skor: " + score;
      randomPosition();
    });

    // Munculkan tombol setiap 1 detik di posisi acak
    setInterval(randomPosition, 1000);
  </script>
</body>
</html>
