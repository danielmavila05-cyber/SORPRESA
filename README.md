<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Felicitaciones mi Jessi</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(to bottom right, #ffe6f0, #ffe6ff);
      font-family: 'Arial', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      flex-direction: column;
      position: relative;
    }

    .foto {
      width: 300px;
      height: auto;
      border-radius: 20px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.3);
      animation: latido 1.5s infinite;
      z-index: 2;
    }

    @keyframes latido {
      0%, 100% {
        transform: scale(1);
      }
      50% {
        transform: scale(1.08);
      }
    }

    .mensaje {
      margin-top: 20px;
      font-size: 28px;
      color: #d1006d;
      animation: flotar 3s ease-in-out infinite;
      z-index: 2;
    }

    @keyframes flotar {
      0%, 100% {
        transform: translateY(0px);
      }
      50% {
        transform: translateY(-10px);
      }
    }

    .corazon {
      position: absolute;
      width: 20px;
      height: 20px;
      background-color: red;
      transform: rotate(45deg);
      animation: flotarCorazon 8s linear infinite;
      opacity: 0.6;
      z-index: 1;
    }

    .corazon::before,
    .corazon::after {
      content: "";
      position: absolute;
      width: 20px;
      height: 20px;
      background-color: inherit;
      border-radius: 50%;
    }

    .corazon::before {
      top: -10px;
      left: 0;
    }

    .corazon::after {
      top: 0;
      left: -10px;
    }

    @keyframes flotarCorazon {
      0% {
        transform: translateY(100vh) rotate(45deg);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) rotate(45deg);
        opacity: 0;
      }
    }

    .boton {
      margin-top: 30px;
      padding: 12px 24px;
      background-color: #ff4da6;
      color: white;
      border: none;
      border-radius: 25px;
      font-size: 18px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      z-index: 2;
      transition: transform 0.2s;
    }

    .boton:hover {
      transform: scale(1.1);
    }

    .sorpresa {
      display: none;
      margin-top: 20px;
      font-size: 20px;
      color: #800080;
      animation: aparecer 1s ease-in-out;
    }

    @keyframes aparecer {
      from {
        opacity: 0;
        transform: scale(0.9);
      }
      to {
        opacity: 1;
        transform: scale(1);
      }
    }
  </style>
</head>
<body>

  <!-- Reproductor de música usando ruta absoluta -->
  <audio autoplay loop>
    <source src="file:///C:/Users/UNSCH-2025/Desktop/Nueva%20carpeta/musica.mp3" type="audio/mpeg">
    Tu navegador no soporta audio HTML5.
  </audio>

  <!-- Imagen usando ruta absoluta -->
  <img src="file:///C:/Users/UNSCH-2025/Desktop/Nueva%20carpeta/jessi.jpg" alt="Foto de Jessi" class="foto">

  <!-- Mensaje animado -->
  <div class="mensaje">Felicitaciones mi Jessi ❤️</div>

  <!-- Botón de sorpresa -->
  <button class="boton" onclick="mostrarSorpresa()">🎁 Ver Sorpresa</button>

  <!-- Mensaje de sorpresa -->
  <div class="sorpresa" id="sorpresa">
    Estoy tan orgulloso de ti, mi amor. Eres una contadora increíble y una persona aún más maravillosa. 💖
  </div>

  <!-- Corazones flotantes -->
  <script>
    const colores = ['#ff4d4d', '#ff66cc', '#ff9933', '#66ccff', '#cc66ff', '#00cc99'];

    for (let i = 0; i < 50; i++) {
      const corazon = document.createElement('div');
      corazon.classList.add('corazon');
      corazon.style.left = Math.random() * 100 + "vw";
      corazon.style.top = Math.random() * 100 + "vh";
      corazon.style.backgroundColor = colores[Math.floor(Math.random() * colores.length)];
      corazon.style.animationDuration = (Math.random() * 5 + 5) + "s";
      corazon.style.width = corazon.style.height = (Math.random() * 15 + 10) + "px";
      document.body.appendChild(corazon);
    }

    function mostrarSorpresa() {
      document.getElementById("sorpresa").style.display = "block";
    }
  </script>
</body>
</html>
