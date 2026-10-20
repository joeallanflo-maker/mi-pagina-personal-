
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mi página personal | Joe Allan</title>

<style>
:root {
  --fondo: #10152e;
  --panel: #20294b;
  --tarjeta: #2b3861;
  --acento: #50dcff;
  --texto: #ffffff;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  font-family: Arial, sans-serif;
  color: var(--texto);
  background: linear-gradient(135deg, var(--fondo), var(--panel));
  font-size: 19px;
}

/* VIDEO 1: FONDO DE TODA LA PÁGINA */
#videoFondo {
  position: fixed;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -2;
  pointer-events: none;
}

.capaVideo {
  position: fixed;
  inset: 0;
  background: rgba(10, 15, 35, 0.78);
  z-index: -1;
  pointer-events: none;
}

header, nav, main, footer {
  position: relative;
}

header {
  text-align: center;
  padding: 20px 12px;
}

header h1 {
  color: var(--acento);
  font-size: clamp(28px, 5vw, 42px);
  margin-bottom: 10px;
}

nav {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
  padding: 15px;
  background: rgba(0, 0, 0, 0.35);
}

nav button {
  padding: 12px 16px;
  border: 2px solid var(--acento);
  border-radius: 12px;
  background: transparent;
  color: white;
  font-size: 17px;
  font-weight: bold;
  cursor: pointer;
}

nav button.activo,
nav button:hover {
  background: var(--acento);
  color: #10152e;
}

main {
  max-width: 1100px;
  margin: auto;
  padding: 20px;
}

.pagina {
  display: none;
}

.pagina.activa {
  display: block;
  animation: aparecer 0.35s ease;
}

@keyframes aparecer {
  from {
    opacity: 0;
    transform: translateY(8px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.panel {
  background: var(--panel);
  padding: 24px;
  border-radius: 20px;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
}

h2 {
  color: var(--acento);
  font-size: 30px;
}

h3 {
  color: var(--acento);
  font-size: 23px;
}

p {
  line-height: 1.6;
}

.etiqueta {
  display: inline-block;
  margin: 5px 4px 5px 0;
  padding: 7px 12px;
  background: var(--tarjeta);
  border: 1px solid var(--acento);
  border-radius: 20px;
}

.inicio-grid {
  display: grid;
  grid-template-columns: minmax(180px, 300px) 1fr;
  gap: 25px;
  align-items: center;
}

.perfil {
  width: 100%;
  max-width: 280px;
  aspect-ratio: 1 / 1;
  object-fit: cover;
  border-radius: 50%;
  border: 4px solid var(--acento);
  display: block;
  margin: auto;
}

.tarjetas {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 18px;
}

.tarjeta {
  background: var(--tarjeta);
  border-radius: 16px;
  padding: 17px;
  overflow: hidden;
}

.foto-tarjeta {
  width: 100%;
  height: 210px;
  object-fit: cover;
  border-radius: 12px;
  border: 2px solid var(--acento);
  display: block;
}

.foto-musica {
  display: block;
  width: 100%;
  max-width: 550px;
  max-height: 380px;
  object-fit: contain;
  margin: 20px auto;
  border: 3px solid var(--acento);
  border-radius: 16px;
}

.galeria {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 18px;
}

.foto-galeria {
  width: 100%;
  height: 270px;
  object-fit: cover;
  border: 3px solid var(--acento);
  border-radius: 14px;
  display: block;
}

/* VIDEO 2: REPRODUCTOR DE MÚSICA Y GALERÍA */
.video-especial {
  width: 100%;
  max-height: 520px;
  display: block;
  object-fit: contain;
  background: #000;
  border: 3px solid var(--acento);
  border-radius: 14px;
}

.video-contenedor {
  width: 100%;
  max-width: 800px;
  margin: 20px auto;
}

.pie-foto {
  text-align: center;
  font-weight: bold;
}

.tabla-contenedor {
  overflow-x: auto;
  margin: 20px 0;
}

table {
  width: 100%;
  border-collapse: collapse;
  background: var(--tarjeta);
  font-size: 17px;
}

th, td {
  border: 1px solid rgba(255, 255, 255, 0.3);
  padding: 13px;
  text-align: left;
}

th {
  color: #10152e;
  background: var(--acento);
}

footer {
  text-align: center;
  padding: 20px;
}

@media (max-width: 650px) {
  .inicio-grid {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .perfil {
    max-width: 210px;
  }

  .galeria {
    grid-template-columns: 1fr;
  }

  .foto-galeria {
    height: 240px;
  }

  nav button {
    font-size: 15px;
    padding: 10px;
  }

  main {
    padding: 12px;
  }

  .panel {
    padding: 17px;
  }
}

@media (prefers-reduced-motion: reduce) {
  .pagina.activa {
    animation: none;
  }
}
</style>
</head>

<body>

<!-- VIDEO 1: FONDO DE LA PÁGINA -->
<video id="videoFondo" autoplay muted loop playsinline>
  <source src="fondo.mp4" type="video/mp4">
</video>

<div class="capaVideo"></div>

<header>
  <h1>¡Bienvenido a mi página personal!</h1>
  <p>Mis gustos, pasatiempos y estudios</p>
</header>

<nav>
  <button class="activo" onclick="mostrarPagina('inicio', this)">
    🏠 Inicio
  </button>

  <button onclick="mostrarPagina('informacion', this)">
    👤 Mi información
  </button>

  <button onclick="mostrarPagina('musica', this)">
    🥁 Música
  </button>

  <button onclick="mostrarPagina('galeria', this)">
    📸 Galería
  </button>

  <button onclick="mostrarPagina('estudios', this)">
    🎓 Mis estudios
  </button>
</nav>

<main>

<!-- INICIO -->
<section id="inicio" class="pagina activa">
  <div class="panel inicio-grid">

    <div>
      <img class="perfil"
           src="perfil.jpg"
           alt="Mi foto de perfil">
    </div>

    <div>
      <h2>Hola, soy Joe Allan</h2>

      <p>
        Soy estudiante y esta es mi página personal.
        Aquí comparto mis gustos, pasatiempos y lo que aprendo.
      </p>

      <span class="etiqueta">🎮 Videojuegos</span>
      <span class="etiqueta">🥁 Música</span>
      <span class="etiqueta">🌴 Viajes</span>
      <span class="etiqueta">💻 Programación</span>
    </div>

  </div>
</section>

<!-- MI INFORMACIÓN -->
<section id="informacion" class="pagina">
  <div class="panel">

    <h2>👤 Mi información</h2>

    <p>
      Me gusta aprender cosas nuevas, conocer lugares,
      jugar videojuegos y utilizar la tecnología.
    </p>

    <div class="tarjetas">

      <div class="tarjeta">
        <h3>🎮 Mis gustos</h3>
        <img class="foto-tarjeta"
             src="freefire.jpg"
             alt="Free Fire">
        <p>Me gusta jugar Free Fire en mi tiempo libre.</p>
      </div>

      <div class="tarjeta">
        <h3>🌴 Viajes</h3>
        <img class="foto-tarjeta"
             src="playa.jpg"
             alt="Foto de la playa">
        <p>
          Me gusta visitar lugares y disfrutar de nuevas experiencias.
        </p>
      </div>

      <div class="tarjeta">
        <h3>💻 Tecnología</h3>
        <p>
          Me interesa la informática y aprender programación.
        </p>
      </div>

    </div>
  </div>
</section>

<!-- MÚSICA -->
<section id="musica" class="pagina">
  <div class="panel">

    <h2>🥁 Mi música</h2>

    <p>
      La música es uno de mis pasatiempos.
      Disfruto tocar instrumentos y aprender canciones.
    </p>

    <img class="foto-musica"
         src="tambores.jpeg"
         alt="Mis tambores">

    <div class="tarjetas">

      <div class="tarjeta">
        <h3>🥁 Tambor</h3>
        <p>Me gusta tocar ritmos con el tambor.</p>
      </div>

      <div class="tarjeta">
        <h3>🎶 Flauta</h3>
        <p>Me gusta aprender melodías con la flauta.</p>
      </div>

      <div class="tarjeta">
        <h3>🎸 Guitarra</h3>
        <p>Me gusta practicar canciones con la guitarra.</p>
      </div>

    </div>

    <!-- VIDEO 2 EN MÚSICA -->
    <h2>🎬 Mi video</h2>

    <p>
      Aquí puedes reproducir el video que forma parte de mi página.
    </p>

    <div class="video-contenedor">
      <video class="video-especial"
             controls
             playsinline
             preload="metadata">
        <source src="video_especial.mp4" type="video/mp4">
        Tu navegador no puede reproducir este video.
      </video>
    </div>

  </div>
</section>

<!-- GALERÍA -->
<section id="galeria" class="pagina">
  <div class="panel">

    <h2>📸 Mi galería</h2>

    <p>Algunas fotos de lugares y momentos especiales.</p>

    <div class="galeria">

      <div class="tarjeta">
        <img class="foto-galeria"
             src="galeria_alberca1.jpeg"
             alt="Alberca 1">
        <p class="pie-foto">🏊 Alberca</p>
      </div>

      <div class="tarjeta">
        <img class="foto-galeria"
             src="alberca_galeria2.jpeg"
             alt="Alberca 2">
        <p class="pie-foto">☀️ Un día de descanso</p>
      </div>

      <div class="tarjeta">
        <img class="foto-galeria"
             src="galeria_playa1.jpeg"
             alt="Playa 1">
        <p class="pie-foto">🌴 Playa</p>
      </div>

      <div class="tarjeta">
        <img class="foto-galeria"
             src="galeria_playa2.jpeg"
             alt="Playa 2">
        <p class="pie-foto">🌊 Junto al mar</p>
      </div>

    </div>

    <!-- EL MISMO VIDEO 2 EN GALERÍA -->
    <h2>🎬 Video especial</h2>

    <div class="tarjeta">
      <div class="video-contenedor">
        <video class="video-especial"
               controls
               playsinline
               preload="metadata">
          <source src="video_especial.mp4" type="video/mp4">
          Tu navegador no puede reproducir este video.
        </video>
      </div>

      <p class="pie-foto">🎥 Un video especial</p>
    </div>

  </div>
</section>

<!-- MIS ESTUDIOS -->
<section id="estudios" class="pagina">
  <div class="panel">

    <h2>🎓 Mis estudios</h2>

    <p>
      Estudio en el CBTis 157, ubicado en Villa de Álvarez,
      Colima. Me interesa aprender sobre informática y programación.
    </p>

    <h3>📚 Información escolar</h3>

    <div class="tabla-contenedor">
      <table>
        <tr>
          <th>Dato</th>
          <th>Información</th>
        </tr>

        <tr>
          <td>Nombre</td>
          <td>Joe Allan Santiago Flores</td>
        </tr>

        <tr>
          <td>Escuela</td>
          <td>CBTis 157</td>
        </tr>

        <tr>
          <td>Ubicación</td>
          <td>Villa de Álvarez, Colima</td>
        </tr>

        <tr>
          <td>Área de interés</td>
          <td>Informática y programación</td>
        </tr>
      </table>
    </div>

    <h3>💻 Temas de programación</h3>

    <div class="tabla-contenedor">
      <table>
        <tr>
          <th>Tema</th>
          <th>Función</th>
        </tr>

        <tr>
          <td>HTML</td>
          <td>Organiza el contenido de una página web.</td>
        </tr>

        <tr>
          <td>CSS</td>
          <td>Permite diseñar la página y cambiar sus colores.</td>
        </tr>

        <tr>
          <td>JavaScript</td>
          <td>Agrega acciones e interactividad.</td>
        </tr>
      </table>
    </div>

  </div>
</section>

</main>

<footer>
  <p>© 2026 | Página personal de Joe Allan 💻</p>
</footer>

<script>
function mostrarPagina(id, boton) {
  document.querySelectorAll(".pagina").forEach(function(pagina) {
    pagina.classList.remove("activa");
  });

  document.getElementById(id).classList.add("activa");

  document.querySelectorAll("nav button").forEach(function(b) {
    b.classList.remove("activo");
  });

  boton.classList.add("activo");

  const colores = {
    inicio: [
      "#10152e",
      "#20294b",
      "#2b3861",
      "#50dcff"
    ],

    informacion: [
      "#10251f",
      "#183e32",
      "#245542",
      "#70f0a6"
    ],

    musica: [
      "#28152e",
      "#45234e",
      "#60316b",
      "#f2a6ff"
    ],

    galeria: [
      "#10283a",
      "#19445d",
      "#225c78",
      "#6fe0ff"
    ],

    estudios: [
      "#2d1c0d",
      "#4b3018",
      "#684523",
      "#ffd166"
    ]
  };

  const c = colores[id];

  ["--fondo", "--panel", "--tarjeta", "--acento"]
    .forEach(function(variable, i) {
      document.documentElement.style.setProperty(variable, c[i]);
    });

  // Pausar los reproductores que quedan en secciones ocultas.
  document.querySelectorAll(".pagina video").forEach(function(video) {
    video.pause();
  });
}
</script>

</body>
</html>


