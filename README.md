<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>7.19 nd zawtai yu undaahai ?</title>
  <style>
    body {
      margin: 0;
      background: linear-gradient(to bottom right, #ffe0e9, #fff5f7);
      font-family: 'Segoe UI', sans-serif;
      text-align: center;
      color: #ff4d6d;
      overflow: hidden;
    }
    .container {
      padding: 60px 20px;
      position: relative;
      z-index: 2;
    }
    h1 {
      font-size: 3em;
      margin-bottom: 10px;
    }
    h2 {
      font-size: 2em;
      margin-bottom: 30px;
    }
    .heart {
      font-size: 3em;
      color: #ff4d6d;
      animation: pulse 1.2s infinite;
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }
    .date-card {
      background: #fff0f5;
      border: 2px solid #ffb6c1;
      border-radius: 20px;
      display: inline-block;
      padding: 30px;
      box-shadow: 0 10px 20px rgba(255, 105, 135, 0.2);
      position: relative;
    }
    button {
      background-color: #ff6b81;
      color: white;
      border: none;
      padding: 15px 30px;
      font-size: 1.2em;
      border-radius: 30px;
      cursor: pointer;
      transition: background-color 0.3s;
      margin: 10px;
    }
    button:hover {
      background-color: #ff4d6d;
    }
    #no-button {
      position: absolute;
      left: 50%;
      top: 200px;
      transform: translateX(-50%);
    }
    .mandarin-fruit {
      font-size: 2.5em;
      margin-top: 60px;
      color: orange;
      position: relative;
    }
    .mandarin-fruit span {
      font-size: 1.2em;
      color: #333;
      display: block;
    }
    .floating {
      position: absolute;
      animation: float 10s linear infinite;
      opacity: 0.7;
      z-index: 1;
    }
    @keyframes float {
      0% { transform: translateY(100vh) scale(0.5); opacity: 0; }
      50% { opacity: 1; }
      100% { transform: translateY(-100vh) scale(1.2); opacity: 0; }
    }
    #music {
      display: none;
    }
  </style>
</head>
<body>

<!-- Floating emojis -->
<script>
  const emojis = ['❤️', '🍊', '💖', '🍊', '💕'];
  for (let i = 0; i < 30; i++) {
    const emoji = document.createElement('div');
    emoji.classList.add('floating');
    emoji.style.left = `${Math.random() * 100}vw`;
    emoji.style.top = `${Math.random() * 100}vh`;
    emoji.style.fontSize = `${20 + Math.random() * 30}px`;
    emoji.innerText = emojis[Math.floor(Math.random() * emojis.length)];
    emoji.style.animationDuration = `${8 + Math.random() * 5}s`;
    document.body.appendChild(emoji);
  }
</script>

<!-- Main content -->
<div class="container">
  <div class="date-card">
    <div class="heart">❤️</div>
    <h1>19 nd zawtai bol bolzoo nd ywahku biz Undaahai</h1>
    <h2>📅 July 19th</h2>
    <button id="yes-button">Yes</button>
    <button id="no-button">No</button>
    <div class="mandarin-fruit" id="mandarin">🍊<span>Huurhun Mandarin!</span></div>
  </div>
</div>

<!-- No button runaway script -->
<script>
  const noBtn = document.getElementById('no-button');
  const card = document.querySelector('.date-card');
  let attempts = 0;

  card.addEventListener('mousemove', (e) => {
    const rect = card.getBoundingClientRect();
    const btnRect = noBtn.getBoundingClientRect();
    const mouseX = e.clientX;
    const mouseY = e.clientY;
    const distance = Math.hypot(mouseX - btnRect.x, mouseY - btnRect.y);

    if (distance < 100) {
      attempts++;
      let newLeft = Math.random() * (rect.width - 100);
      let newTop = Math.random() * (rect.height - 60);

      if (attempts > 5) {
        const mandarin = document.getElementById('mandarin');
        newLeft = mandarin.offsetLeft + 30;
        newTop = mandarin.offsetTop - 10;
      }

      noBtn.style.left = `${newLeft}px`;
      noBtn.style.top = `${newTop}px`;
    }
  });
</script>

<!-- Yes button confetti and surprise -->
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
<script>
  const yesBtn = document.getElementById('yes-button');
  yesBtn.addEventListener('click', () => {
    // Confetti blast
    confetti({
      particleCount: 150,
      spread: 100,
      origin: { y: 0.6 },
    });

    // Delay for surprise message
    setTimeout(() => {
      alert("💌 Herwee 12 ni oroi gertee harij chadwal 13nd ch uulzaj magadgu shu oilgooroi za <3  🍧🌸✨");
    }, 600);
  });
</script>

<!-- YouTube autoplay music -->
<iframe
  id="music"
  width="0"
  height="0"
  src="https://www.youtube.com/embed/lYoWuaw5nSk?autoplay=1&loop=1&playlist=lYoWuaw5nSk"
  frameborder="0"
  allow="autoplay"
></iframe>

</body>
</html>



 
