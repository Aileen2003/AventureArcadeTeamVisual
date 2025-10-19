<!--
Temple Run Arcade: Reliquias Malditas — INDEX VISUAL (.md)
Rama: prototipo | Autora: Aileen (Líder)
Nota: Este .md usa HTML incrustado. En algunos visores web pueden filtrarse estilos.
En VS Code / GitKraken preview / GitHub Pages funciona correctamente.
-->

<style>
/* ======== RESET ======== */
* { box-sizing: border-box; }
html, body { margin:0; padding:0; }

/* ======== PALETA ======== */
:root{
  --gold:#f6d068;
  --gold-deep:#c7a343;
  --teal:#3fe0cf;          /* turquesa tipo HUD */
  --teal-deep:#1aa89a;
  --bg-dark:#0a0c10;
  --bg-stone:#111418;
  --white:#f2f2f2;
}

/* ======== FONDO TEXTURIZADO (ruina / piedra) ======== */
body{
  font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
  color:var(--white);
  background:
    radial-gradient(1200px 700px at 50% -10%, #1a1f27 0%, transparent 60%),
    linear-gradient(180deg, #0b0e12 0%, #080a0e 50%, #06080c 100%),
    var(--bg-dark);
  min-height:100vh;
  line-height:1.5;
  overflow-x:hidden;
}

/* Capa de ruido / textura (SVG embebido en data-uri) */
body::before{
  content:"";
  position:fixed; inset:0;
  pointer-events:none; opacity:.12; mix-blend-mode:overlay;
  background-image: url("data:image/svg+xml;utf8,\
  <svg xmlns='http://www.w3.org/2000/svg' width='160' height='160' viewBox='0 0 160 160'>\
    <filter id='n'>\
      <feTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2' stitchTiles='stitch'/>\
      <feColorMatrix type='saturate' values='0'/>\
      <feComponentTransfer><feFuncA type='table' tableValues='0 0.8'/></feComponentTransfer>\
    </filter>\
    <rect width='100%' height='100%' filter='url(%23n)'/>\
  </svg>");
  background-size:160px 160px;
}

/* ======== CONTENEDOR CENTRAL ======== */
.screen{
  min-height: 100svh;
  display:grid;
  place-items:center;
  padding:40px 24px 80px;
}

/* ======== LOGO ======== */
.logo{
  text-align:center;
  text-transform:uppercase;
  letter-spacing:1px;
  margin: 0 0 16px 0;
  line-height:1.05;
  font-weight: 900;
  filter: drop-shadow(0 8px 20px rgba(246,208,104,.16));
}
.logo .main{
  display:block; font-size: clamp(28px, 6.2vw, 56px);
  background: linear-gradient(180deg, var(--gold) 0%, #ffe9a1 35%, var(--gold-deep) 100%);
  -webkit-background-clip:text; background-clip:text; color: transparent;
  text-shadow: 0 1px 0 rgba(0,0,0,.5);
}
.logo .sub{
  display:block; font-size: clamp(16px, 3.4vw, 28px);
  color: var(--teal);
  text-shadow: 0 0 8px rgba(63,224,207,.35), 0 0 24px rgba(26,168,154,.25);
}

/* ======== TARJETA (marco templo) ======== */
.frame{
  width: min(960px, 92%);
  border: 2px solid rgba(255,255,255,.06);
  border-radius: 14px;
  padding: 20px;
  background:
    linear-gradient(180deg, rgba(255,255,255,.03), rgba(255,255,255,.01)),
    radial-gradient(900px 200px at 50% -160px, rgba(246,208,104,.10), transparent 60%),
    linear-gradient(180deg, rgba(0,0,0,.35), rgba(0,0,0,.55));
  box-shadow: 0 8px 36px rgba(0,0,0,.45), inset 0 0 0 1px rgba(255,255,255,.04);
}

/* ======== MENÚ ======== */
.menu{
  display:grid; gap:12px;
  grid-template-columns: repeat(3, minmax(120px, 1fr));
  align-items:center;
}
.btn{
  padding: 14px 16px;
  border: 2px solid var(--teal);
  color: var(--teal);
  background: linear-gradient(180deg, rgba(63,224,207,.08), rgba(26,168,154,.05));
  text-align:center; text-decoration:none; font-weight: 800; text-transform:uppercase;
  letter-spacing:.5px; border-radius:10px; position:relative;
  transition: transform .08s ease, box-shadow .2s ease, background .2s ease;
  box-shadow: 0 0 0 0 rgba(63,224,207,.0);
}
.btn:hover{
  transform: translateY(-1px);
  box-shadow: 0 10px 20px rgba(0,0,0,.35), 0 0 16px rgba(63,224,207,.25);
  background: linear-gradient(180deg, rgba(63,224,207,.15), rgba(26,168,154,.08));
}
.badge{
  display:inline-block; margin-left:8px; padding:.5px 6px; border-radius:8px;
  font-size:.8rem; color:#111; background: var(--gold);
  box-shadow: 0 0 10px rgba(246,208,104,.35);
}

/* ======== INSERT COIN ======== */
.hint{
  margin-top:14px; text-align:center; opacity:.85; font-size:.95rem;
  color: var(--gold);
  text-shadow: 0 0 10px rgba(246,208,104,.25);
  animation: pulse 2s infinite;
}
@keyframes pulse { 0%,100%{opacity:.45;} 50%{opacity:1;} }

/* ======== SECCIONES ======== */
.section{
  scroll-margin-top: 80px;
  width:min(960px, 92%);
  margin: 56px auto 0 auto;
  border-left: 4px solid var(--gold-deep);
  padding: 14px 18px 4px 18px;
  background: linear-gradient(180deg, rgba(255,255,255,.03), rgba(255,255,255,.01));
  border-radius: 10px;
}
.section h2{
  margin:0 0 6px 0; padding:0;
  color: var(--gold);
  text-transform: uppercase; letter-spacing:.5px;
}
.section p{ margin-top: 8px; opacity:.95; }

/* ======== MINI HUD DECOS ======== */
.hud{
  margin: 16px 0 8px 0; display:flex; gap:16px; align-items:center; flex-wrap:wrap;
}
.hud .heart{
  width:18px; height:18px; border-radius:4px;
  background: radial-gradient(circle at 35% 35%, #b6fff6 0%, var(--teal) 50%, var(--teal-deep) 100%);
  box-shadow: 0 0 10px rgba(63,224,207,.45), inset 0 0 6px rgba(0,0,0,.35);
  transform: rotate(45deg);
}
.hud .bar{
  flex: 1 1 180px; height:10px; border-radius:999px;
  background: linear-gradient(90deg, var(--teal) 0% , rgba(63,224,207,.15) 60%);
  box-shadow: inset 0 0 6px rgba(0,0,0,.55), 0 0 10px rgba(63,224,207,.25);
}
.hud .score{
  padding:4px 10px; border-radius:10px; font-weight:800; color:#111;
  background: linear-gradient(180deg, var(--gold) 0%, #ffd96f 60%, var(--gold-deep) 100%);
  box-shadow: 0 0 12px rgba(246,208,104,.35);
}

/* ======== FOOTER ======== */
.footer{
  width:min(960px, 92%); margin:40px auto 24px auto;
  opacity:.7; font-size:.9rem; text-align:center;
}

/* ======== SCROLL SUAVE ======== */
html { scroll-behavior: smooth; }

/* ======== RESPONSIVE ======== */
@media (max-width:680px){
  .menu{ grid-template-columns: 1fr; }
}
</style>

<div class="screen">
  <header class="logo">
    <span class="main">Temple Run Arcade</span>
    <span class="sub">Reliquias Malditas</span>
  </header>

  <section class="frame">
    <nav class="menu">
      <a class="btn" href="#jugar">Jugar <span class="badge">Start</span></a>
      <a class="btn" href="#controles">Controles</a>
      <a class="btn" href="#creditos">Créditos</a>
    </nav>
    <div class="hint">INSERT COIN — PULSE START</div>
  </section>

  <!-- Mini HUD decorativo (coincide con tu referencia visual) -->
  <div class="hud" aria-hidden="true" style="width:min(960px,92%);">
    <div class="heart"></div><div class="heart"></div><div class="heart"></div>
    <div class="bar"></div>
    <div class="score">ARTIFACTS: 3/7</div>
  </div>
</div>

<!-- ================= SECCIONES ================= -->

<div id="jugar" class="section">
  <h2>Jugar</h2>
  <p><em>Las ruinas despiertan... ¿Estás lista para entrar? Recoge las reliquias... antes de que el templo te devore.</em></p>
  <ul>
    <li>Objetivo del nivel: reunir <strong>3 fragmentos</strong> y abrir el <strong>portal de salida</strong>.</li>
    <li>Vigila las <strong>trampas</strong>: losas que caen, lanzas alternas, paredes móviles.</li>
    <li>Usa los <strong>Orbes de Tiempo</strong> para frenar trampas por 3 segundos.</li>
  </ul>
  <div class="hud" aria-hidden="true">
    <div class="heart"></div><div class="heart"></div><div class="heart"></div>
    <div class="bar"></div>
    <div class="score">SCORE x1.5</div>
  </div>
</div>

<div id="controles" class="section">
  <h2>Controles</h2>
  <ul>
    <li><strong>W / ↑</strong> — Saltar</li>
    <li><strong>S / ↓</strong> — Deslizar</li>
    <li><strong>A-D / ← →</strong> — Esquivar</li>
    <li><strong>Espacio</strong> — Usar Orbe</li>
  </ul>
  <p style="opacity:.85">Consejo: encadena acciones sin recibir daño para aumentar el <strong>multiplicador</strong>.</p>
</div>

<div id="creditos" class="section">
  <h2>Créditos</h2>
  <p><strong>AventuraArcadeTeam</strong></p>
  <ul>
    <li><strong>Aileen</strong> — Líder de repositorio / Prototipo</li>
    <li><strong>Elizabeth</strong> — Diseños / Recursos visuales</li>
    <li><strong>Javier</strong> — Narrativa / Documentación</li>
  </ul>
  <p style="opacity:.8">Proyecto académico estilo arcade — prototipo visual en Markdown.</p>
</div>

<div class="footer">
  © Temple Run Arcade: Reliquias Malditas — Prototipo visual (.md). 
  <br/>Tip: en GitKraken/VSCode puedes abrir “Preview” para ver los estilos.
</div>
