<!-- Temple Run Arcade: Reliquias Malditas — Versión Pages sin Jekyll -->
<!-- CSS integrado directamente para visual arcade -->
<style>
* { box-sizing: border-box; margin: 0; padding: 0; }
:root{
  --gold:#f6d068;
  --gold-deep:#c7a343;
  --teal:#3fe0cf;
  --teal-deep:#1aa89a;
  --bg-dark:#0a0c10;
  --white:#f2f2f2;
}
body{
  font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
  background:
    radial-gradient(1000px 600px at 50% -10%, #1a1f27 0%, transparent 60%),
    linear-gradient(180deg, #0b0e12 0%, #080a0e 50%, #06080c 100%),
    var(--bg-dark);
  color: var(--white);
  min-height: 100vh;
  overflow-x: hidden;
}
body::before{
  content:"";
  position: fixed; inset:0;
  pointer-events:none; opacity:.15;
  background-image:url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='200' height='200'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='1' numOctaves='2'/><feColorMatrix type='saturate' values='0'/><feComponentTransfer><feFuncA type='table' tableValues='0 0.5'/></feComponentTransfer></filter><rect width='100%' height='100%' filter='url(%23n)' /></svg>");
  background-size: 220px;
}
.screen{
  min-height: 90vh;
  display: grid;
  place-items: center;
  padding: 40px 20px;
  text-align: center;
}
.logo {
  text-transform: uppercase;
  font-weight: 900;
}
.logo .main{
  font-size: clamp(28px, 6vw, 60px);
  background: linear-gradient(180deg, var(--gold), #ffe9a1, var(--gold-deep));
  -webkit-background-clip:text;
  color: transparent;
}
.logo .sub{
  font-size: clamp(16px, 3.2vw, 30px);
  color: var(--teal);
  text-shadow: 0 0 8px rgba(63,224,207,.4);
}
.frame{
  width: min(900px, 92%);
  margin-top: 16px;
  padding: 20px;
  border-radius: 12px;
  background: rgba(255,255,255,0.03);
  border: 2px solid rgba(255,255,255,0.05);
}
.menu{
  display: grid; gap: 12px;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  margin-top: 10px;
}
.btn{
  display: inline-block;
  padding: 14px;
  border-radius: 10px;
  text-decoration: none;
  font-weight: bold;
  text-transform: uppercase;
  color: var(--teal);
  border: 2px solid var(--teal);
  background: rgba(63,224,207,.08);
  transition: 0.2s;
}
.btn:hover{
  box-shadow: 0 0 15px rgba(63,224,207,.4);
  transform: translateY(-2px);
}
.hint{
  margin-top: 12px;
  color: var(--gold);
  animation: blink 2s infinite;
}
@keyframes blink { 0%,100%{opacity:.4;} 50%{opacity:1;} }
.section{
  width: min(900px, 92%);
  margin: 60px auto;
  border-left: 4px solid var(--gold);
  padding: 16px 20px;
  background: rgba(255,255,255,0.03);
  border-radius: 8px;
}
.section h2{
  color: var(--gold);
  text-transform: uppercase;
  margin-bottom: 8px;
}
.footer{
  text-align: center;
  font-size: .9rem;
  opacity:.7;
  margin: 50px 0;
}
</style>

<div class="screen">
  <div class="logo">
    <span class="main">Temple Run Arcade</span>
    <span class="sub">Reliquias Malditas</span>
  </div>

  <div class="frame">
    <div class="menu">
      <a href="#jugar" class="btn">Jugar</a>
      <a href="#controles" class="btn">Controles</a>
      <a href="#creditos" class="btn">Créditos</a>
    </div>
    <div class="hint">INSERT COIN — PULSE START</div>
  </div>
</div>

<div id="jugar" class="section">
  <h2>Jugar</h2>
  <p><em>Las ruinas despiertan... ¿Estás lista para entrar? Recoge las reliquias... antes de que el templo te devore.</em></p>
  <ul>
    <li>Objetivo: reunir <strong>3 fragmentos</strong> y abrir el portal.</li>
    <li>Evita trampas: losas que caen, lanzas, paredes móviles.</li>
    <li>Orbes de Tiempo ralentizan trampas por 3 segundos.</li>
  </ul>
</div>

<div id="controles" class="section">
  <h2>Controles</h2>
  <ul>
    <li><strong>W / ↑</strong> — Saltar</li>
    <li><strong>S / ↓</strong> — Deslizar</li>
    <li><strong>A-D / ← →</strong> — Esquivar</li>
    <li><strong>Espacio</strong> — Usar Orbe</li>
  </ul>
</div>

<div id="creditos" class="section">
  <h2>Créditos</h2>
  <ul>
    <li><strong>Aileen</strong> — Líder / Prototipo</li>
    <li><strong>Elizabeth</strong> — Diseño Visual</li>
    <li><strong>Javier</strong> — Narrativa / Documentación</li>
  </ul>
  <p>Proyecto estilo Arcade — GitHub Pages.</p>
</div>

<div class="footer">
  © Temple Run Arcade: Reliquias Malditas | GitHub Pages Mode
</div>
