<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Date on July 19?</title>
  <style>
    body {
      background: linear-gradient(to bottom right, #ffe0e9, #fff5f7);
      font-family: 'Segoe UI', sans-serif;
      text-align: center;
      padding: 50px;
      color: #ff4d6d;
      overflow: hidden;
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
      transition: background-color 0.3s, transform 0.3s;
      margin: 10px;
      position: relative;
    }
    button:hover {
      background-color: #ff4d6d;
    }
    #no-button {
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      transition: top 0.3s, left 0.3s;
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
  </style>
</head>
<body>
  <div class="date-card">
    <div class="heart">❤️</div>
    <h1>Will you go on a date with me?</h1>
    <h2>📅 July 19th</h2>
    <button onclick="alert('Yay!! ❤️ Can’t wait!')">Yes</button>
    <button id="no-button">No</button>
    <div class="mandarin-fruit" id="mandarin">
      🍊<span>Mandarin is watching you!</span>
    </div>
  </div>

  <script>
    const noBtn = document.getElementById('no-button');
    const card = document.querySelector('.date-card');
    const mandarin = document.getElementById('mandarin');

    let attempts = 0;

    card.addEventListener('mousemove', (e) => {
      const rect = card.getBoundingClientRect();
      const btnRect = noBtn.getBoundingClientRect();
      const mouseX = e.clientX;
      const mouseY = e.clientY;

      const distance = Math.hypot(mouseX - btnRect.x, mouseY - btnRect.y);

      if (distance < 120) {
        attempts++;
        let newLeft = Math.random() * (rect.width - 100);
        let newTop = Math.random() * (rect.height - 60);

        if (attempts > 5) {
          // Hide behind the mandarin fruit
          const mandarinRect = mandarin.getBoundingClientRect();
          newLeft = mandarin.offsetLeft + 20;
          newTop = mandarin.offsetTop - 10;
        }

        noBtn.style.left = `${newLeft}px`;
        noBtn.style.top = `${newTop}px`;
      }
    });
  </script>
</body>
</html>



 
