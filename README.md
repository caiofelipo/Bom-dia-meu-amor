
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Lírio do Amor 🌸</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(to top, #fff0f5, #ffe4e1);
      font-family: 'Arial', sans-serif;
      overflow: hidden;
    }

    svg {
      width: 500px;
      height: 500px;
      cursor: pointer;
      transition: opacity 1s ease-in-out;
    }

    .petal {
      cursor: pointer;
      transition: opacity 0.3s, transform 0.3s;
    }

    .petal:hover {
      opacity: 0.8;
      transform: scale(1.05);
    }

    .petal.clicked {
      opacity: 0.4;
      pointer-events: none;
    }

    .label {
      font-size: 14px;
      font-weight: bold;
      fill: #5a2d2d;
      pointer-events: none;
    }

    .message {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0);
      font-size: 3em;
      text-align: center;
      color: #d6336c;
      font-weight: bold;
      opacity: 0;
      transition: all 1s ease-in-out;
    }

    .message.show {
      opacity: 1;
      transform: translate(-50%, -50%) scale(1);
    }
  </style>
</head>
<body>
  <!-- Flor SVG -->
  <svg id="flower" viewBox="0 0 500 500">
    <defs>
      <radialGradient id="petalGradient" cx="50%" cy="50%" r="70%">
        <stop offset="0%" stop-color="#fff" />
        <stop offset="70%" stop-color="#ff69b4" />
        <stop offset="100%" stop-color="#d6336c" />
      </radialGradient>
      <radialGradient id="centerGradient" cx="50%" cy="50%" r="70%">
        <stop offset="0%" stop-color="#fffacd" />
        <stop offset="100%" stop-color="#ffd700" />
      </radialGradient>
    </defs>

    <!-- pétalas -->
    <ellipse class="petal" data-message="Você é minha alegria" cx="250" cy="120" rx="60" ry="140" fill="url(#petalGradient)" />
    <text x="250" y="60" text-anchor="middle" class="label">Clique aqui</text>

    <ellipse class="petal" data-message="Meu coração é seu" cx="380" cy="180" rx="60" ry="140" transform="rotate(60 380 180)" fill="url(#petalGradient)" />
    <text x="420" y="120" text-anchor="middle" class="label">Clique aqui</text>

    <ellipse class="petal" data-message="Ao seu lado tudo é paz" cx="370" cy="320" rx="60" ry="140" transform="rotate(120 370 320)" fill="url(#petalGradient)" />
    <text x="420" y="360" text-anchor="middle" class="label">Clique aqui</text>

    <ellipse class="petal" data-message="Você é meu sonho bom" cx="250" cy="380" rx="60" ry="140" fill="url(#petalGradient)" />
    <text x="250" y="470" text-anchor="middle" class="label">Clique aqui</text>

    <ellipse class="petal" data-message="Te amar é viver" cx="130" cy="320" rx="60" ry="140" transform="rotate(240 130 320)" fill="url(#petalGradient)" />
    <text x="80" y="360" text-anchor="middle" class="label">Clique aqui</text>

    <ellipse class="petal" data-message="Você é meu sempre" cx="120" cy="180" rx="60" ry="140" transform="rotate(300 120 180)" fill="url(#petalGradient)" />
    <text x="80" y="120" text-anchor="middle" class="label">Clique aqui</text>

    <!-- centro da flor -->
    <circle cx="250" cy="250" r="50" fill="url(#centerGradient)" />
  </svg>

  <!-- Mensagem final -->
  <div class="message" id="message">❤️ Bom dia, amor! Eu te amo ❤️</div>

  <script>
    const petals = document.querySelectorAll('.petal');
    const flower = document.getElementById('flower');
    const message = document.getElementById('message');
    let clickedCount = 0;

    petals.forEach(petal => {
      petal.addEventListener('click', () => {
        alert(petal.dataset.message);
        petal.classList.add('clicked');
        clickedCount++;

        if (clickedCount === petals.length) {
          flower.style.opacity = 0;
          setTimeout(() => {
            flower.style.display = "none";
            message.classList.add("show");
          }, 1000);
        }
      });
    });
  </script>
</body>
</html>
