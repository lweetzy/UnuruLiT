
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>You so pretty asf? 💘</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <style>
    body {
      margin: 0;
      background: linear-gradient(to bottom right, #ffb6c1, #ffe4e1);
      font-family: 'Segoe UI', cursive;
      text-align: center;
      color: #d6336c;
    }
    h1 {
      margin-top: 100px;
      font-size: 42px;
    }
    p {
      font-size: 24px;
    }
    .buttons {
      margin-top: 30px;
    }
    button {
      font-size: 20px;
      padding: 10px 20px;
      margin: 10px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      background-color: #ff69b4;
      color: white;
      transition: 0.3s;
    }
    button:hover {
      background-color: #ff85c1;
    }
    #response {
      margin-top: 30px;
      font-size: 24px;
      font-weight: bold;
    }
    .hearts {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      pointer-events: none;
    }
    .heart {
      color: #ff69b4;
      font-size: 24px;
      position: absolute;
      animation: float 6s ease-in infinite;
    }
    @keyframes float {
      0% { transform: translateY(0) rotate(0deg); opacity: 1; }
      100% { transform: translateY(-100vh) rotate(720deg); opacity: 0; }
    }
  </style>
</head>
<body>

  <h1>Will You Be my girlfrend 💖</h1>
  <p>Ci huurhun bi huurhun 2 uula huurhun hamtdaa 3 dahi huurhuniig buteehu ?</p>

  <div class="buttons">
    <button onclick="sayYes()">Yes 💖</button>
    <button onclick="sayNo()">No 💔</button>
  </div>

  <div id="response"></div>
  <div class="hearts" id="hearts"></div>

  <script>
    function sayYes() {
      document.getElementById("response").innerHTML = "💘 Thank you, my love! You made me the happiest person alive! 💘";
    }

    function sayNo() {
      document.getElementById("response").innerHTML = "⚠️ Error: You can't say no to this much love 😭";
      alert("System crash: Too much heartbreak detected 💔");
    }
    // Heart animation
    const hearts = document.getElementById('hearts');

    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (2 + Math.random() * 3) + 's';
      heart.textContent = '💗';
      hearts.appendChild(heart);
      setTimeout(() => heart.remove(), 6000);
    }

    setInterval(createHeart, 300);
  </script>

</body>
</html>


 
