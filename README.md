# san-valentin
i love you babe
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>¿Quieres ser mi San Valentín? 💖</title>
  <style>
    body {
      margin: 0;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background-image: url('https://images.unsplash.com/photo-1518791841217-8f162f1e1131');
      background-size: cover;
      background-position: center;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
    }
    .card {
      background: rgba(255, 255, 255, 0.9);
      padding: 30px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
      max-width: 320px;
      position: relative;
      z-index: 10;
    }
    h1 {
      font-size: 1.8rem;
      color: #e91e63;
    }
    p {
      font-size: 1rem;
    }
    button {
      margin-top: 15px;
      padding: 12px 20px;
      font-size: 1rem;
      border: none;
      border-radius: 12px;
      cursor: pointer;
    }
    #yes {
      background-color: #ff69b4;
      color: white;
    }
    #no {
      background-color: #ccc;
      color: #333;
      cursor: not-allowed;
    }
    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background-color: #ff69b4;
      transform: rotate(-45deg);
      animation: floatUp 4s linear infinite;
    }
    .heart::before, .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background-color: #ff69b4;
      border-radius: 50%;
    }
    .heart::before {
      top: -10px;
      left: 0;
    }
    .heart::after {
      top: 0;
      left: 10px;
    }
    @keyframes floatUp {
      0% { transform: translateY(0) rotate(-45deg); opacity: 1; }
      100% { transform: translateY(-500px) rotate(-45deg); opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>💌 Oye amor 💌</h1>
    <p>Desde lejos, pero con todo mi corazón…</p>
    <p><strong>¿Quieres ser mi San Valentín, mi [apodo de ella]? 💘</strong></p>
    <button id="yes">Sí 💖</button>
    <button id="no">No 🙈</button>
    <p id="msg"></p>
  </div>

  <!-- Música (YouTube, sin descargar contenido protegido) -->
  <iframe id="music" width="0" height="0"
    src="https://www.youtube.com/embed/8JjG0U9vK5c?enablejsapi=1&autoplay=0"
    frameborder="0"
    allow="autoplay"></iframe>

  <script>
    const yesBtn = document.getElementById('yes');
    const msg = document.getElementById('msg');

    yesBtn.addEventListener('click', () => {
      msg.innerHTML = '🐱💘 Sabía que dirías que sí. Te amo muchísimo, [apodo de ella] 💘🐱';
      const iframe = document.getElementById('music');
      iframe.contentWindow.postMessage('{"event":"command","func":"playVideo","args":""}', '*');
      startHearts();
    });

    function startHearts() {
      for (let i = 0; i < 30; i++) {
        const heart = document.createElement('div');
        heart.classList.add('heart');
        heart.style.left = Math.random() * window.innerWidth + 'px';
        heart.style.animationDuration = 3 + Math.random() * 2 + 's';
        heart.style.opacity = Math.random();
        document.body.appendChild(heart);
        setTimeout(() => {
          heart.remove();
        }, 4000);
      }
    }
  </script>
</body>
</html>
