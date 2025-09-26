<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Burbujas con Frases</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ffb3b3, #ff8080);
      font-family: Arial, sans-serif;
      overflow: hidden;
    }

    .container {
      text-align: center;
      position: relative;
    }

    .heart-btn {
      width: 80px;
      height: 80px;
      background: #ff3366;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      border: none;
      outline: none;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      transition: transform 0.2s ease;
      z-index: 10;
    }

    .heart-btn:hover {
      transform: scale(1.1);
    }

    .heart {
      width: 40px;
      height: 40px;
      background-color: red;
      transform: rotate(-45deg);
      position: relative;
    }

    .heart::before,
    .heart::after {
      content: "";
      width: 40px;
      height: 40px;
      background-color: red;
      border-radius: 50%;
      position: absolute;
    }

    .heart::before {
      top: -20px;
      left: 0;
    }

    .heart::after {
      left: 20px;
      top: 0;
    }

    .bubble {
      position: absolute;
      bottom: 100px;
      background: rgba(255, 51, 102, 0.9);
      color: white;
      padding: 10px 20px;
      border-radius: 20px;
      font-size: 16px;
      white-space: nowrap;
      opacity: 0;
      animation: floatUp 3s ease forwards;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0);
        opacity: 0;
      }
      20% {
        opacity: 1;
      }
      100% {
        transform: translateY(-150px);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <div class="container">
    <button class="heart-btn" onclick="crearBurbuja()">
      <div class="heart"></div>
    </button>
  </div>

  <script>
    const frases = [
      "Bonito por dentro y por fuera.",
      "Tu vibra ilumina mis días.",
      "Eres único.",
      "Tu sonrisa me alegra el día.",
      "siempre buen gusto.",
      "tu amor me llena el corazón.",
      "estoy enamoradisima de ti.",
      "solo tú me haces sentir tantas cosas.",
      "te veo y me vuelvo loca.",
      "te quiero siempre a mi lado.",
      "te aprecio de la manera más sincera.",
      "quédate por siempre.",
      "lo daría todo por ti.",
      "eres lo más hermoso que he visto.",
      "te amo.",
      "confío en ti.",
      "tengo ojos solo para ti.",
      "eres el más dulce.",
      "mi chico.",
      "amo tu sonrisa.",
      "quiero hacerte el más feliz del mundo.",
      "te anhelo.", 
      "te deseo.",
      "te sueño.",
      "siempre puedes contar conmigo.",
      "te adoro.",
      "tus besos me dan vida.",
      "pienso en ti 24/7.",
      "eres mi mejor compañia.",
      "vales por mil.",
      "eres mi calma.",
      "mi mejor amigo.",
      "el mejor pololo que existe.",
      "no tienes competencia ni comparación.", 
      "amor tu personalidad.",
      "contigo soy yo.",
      "no tienes que cargar con todo solo.", 
      "no me veo sin ti.",
      "amo tus detalles.",
      "siempre te esucho.",
      "mis ojos brillan de amor por ti.",
      "amo tus apodos.",
      "siempre te cuidaré.",
      "eres mi prioridad.",
      "tenemos una conexión especial.",
      "el destino nos unió.",
      "si me faltas se derrumba mi mundo.",
      "contigo todo me nace.",
      "contigo estoy dispuesta.",
      "te amo más de lo que demuestro.",
      "amo reír contigo.",
      "amo tu tacto.",
      "eres mi tipo ideal.",
      
      
    ];

    let indice = 0;

    function crearBurbuja() {
      const burbuja = document.createElement("div");
      burbuja.className = "bubble";
      burbuja.textContent = frases[indice];

      // Variación aleatoria en posición horizontal (-100px a +100px)
      const offset = Math.floor(Math.random() * 200) - 100;
      burbuja.style.left = `calc(50% + ${offset}px)`;

      document.querySelector(".container").appendChild(burbuja);

      // Eliminar la burbuja después de la animación
      setTimeout(() => {
        burbuja.remove();
      }, 3000);

      indice = (indice + 1) % frases.length;
    }
  </script>

</body>
</html>

