
<!DOCTYPE html>

<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CartaQR Pro — Tu Menú Digital</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@700;800&family=Outfit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
* { margin: 0; padding: 0; box-sizing: border-box; }

:root {
–gold: #C9A84C;
–dark: #0D0D0D;
–dark2: #141414;
–white: #FFFFFF;
}

body {
background: #f0ece4;
font-family: ‘Outfit’, sans-serif;
min-height: 100vh;
}

/* ─── HERO SECTION ─── */
.hero {
background: var(–dark);
position: relative;
overflow: hidden;
padding: 0;
}

.hero-inner {
max-width: 680px;
margin: 0 auto;
padding: 0 24px;
}

.top-strip {
background: var(–gold);
text-align: center;
padding: 9px;
font-size: 11px;
font-weight: 600;
letter-spacing: 0.2em;
text-transform: uppercase;
color: #000;
}

.hero-content {
padding: 44px 0 36px;
position: relative;
z-index: 1;
}

/* glow */
.hero::after {
content: ‘’;
position: absolute;
width: 400px; height: 400px;
background: radial-gradient(circle, rgba(201,168,76,0.1) 0%, transparent 70%);
top: -100px; right: -100px;
border-radius: 50%;
pointer-events: none;
}

.eyebrow {
display: inline-flex;
align-items: center;
gap: 10px;
margin-bottom: 18px;
}
.eyebrow-line { width: 28px; height: 1px; background: var(–gold); }
.eyebrow-text { font-size: 11px; font-weight: 500; letter-spacing: 0.18em; text-transform: uppercase; color: var(–gold); }

h1 {
font-family: ‘Cormorant Garamond’, serif;
font-weight: 800;
font-size: clamp(48px, 10vw, 68px);
line-height: 0.95;
color: var(–white);
margin-bottom: 16px;
}
h1 .gold  { color: var(–gold); display: block; }
h1 .muted { color: rgba(255,255,255,0.18); display: block; font-size: clamp(22px,5vw,32px); margin-top: 6px; letter-spacing: 0.04em; }

.hero-sub {
font-size: 14px;
font-weight: 300;
color: rgba(255,255,255,0.45);
line-height: 1.7;
margin-bottom: 32px;
max-width: 420px;
}

/* transform row */
.transform-row {
background: #141414;
border: 1px solid #252525;
border-radius: 14px;
display: flex;
align-items: stretch;
overflow: hidden;
margin-bottom: 32px;
}
.c-side { flex:1; padding: 22px 18px; display:flex; flex-direction:column; align-items:center; gap:8px; }
.c-side.old { border-right: 1px solid #252525; opacity: 0.6; }
.c-side.new { background: linear-gradient(135deg,rgba(201,168,76,0.07),transparent); }
.c-icon { font-size: 28px; }
.c-lbl  { font-size: 10px; font-weight:600; letter-spacing:0.16em; text-transform:uppercase; color: rgba(255,255,255,0.3); }
.c-desc { font-size: 12px; font-weight:300; color:rgba(255,255,255,0.5); text-align:center; line-height:1.5; }
.arrow-col { width:42px; display:flex; align-items:center; justify-content:center; flex-shrink:0; }
.arrow-sym { font-size:18px; color:var(–gold); animation: ap 1.8s ease-in-out infinite; }
@keyframes ap { 0%,100%{transform:translateX(0);opacity:1} 50%{transform:translateX(5px);opacity:0.5} }

/* benefits */
.benefits {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 10px;
margin-bottom: 0;
padding-bottom: 44px;
}
.ben {
background: #161616;
border: 1px solid #222;
border-radius: 12px;
padding: 14px 10px;
display:flex; flex-direction:column; gap:6px;
}
.ben-icon  { font-size: 18px; }
.ben-title { font-size: 11px; font-weight: 600; color: var(–white); }
.ben-text  { font-size: 10.5px; font-weight: 300; color: rgba(255,255,255,0.38); line-height: 1.5; }

/* ─── FORM SECTION ─── */
.form-section {
background: #fff;
max-width: 680px;
margin: 0 auto;
border-radius: 0 0 20px 20px;
padding: 36px 32px 40px;
box-shadow: 0 20px 60px rgba(0,0,0,0.12);
}

.form-title {
font-family: ‘Cormorant Garamond’, serif;
font-weight: 700;
font-size: 28px;
color: #111;
margin-bottom: 6px;
}

.form-title span { color: var(–gold); }

.form-sub {
font-size: 13px;
font-weight: 300;
color: #888;
margin-bottom: 26px;
line-height: 1.6;
}

.form-grid {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 14px;
}

.field {
display: flex;
flex-direction: column;
gap: 6px;
}

.field.full { grid-column: 1 / -1; }

label {
font-size: 11.5px;
font-weight: 500;
color: #444;
letter-spacing: 0.04em;
}

input, select, textarea {
width: 100%;
padding: 13px 16px;
border: 1.5px solid #e8e8e8;
border-radius: 10px;
font-family: ‘Outfit’, sans-serif;
font-size: 14px;
font-weight: 400;
color: #111;
background: #fafafa;
outline: none;
transition: border-color 0.2s, background 0.2s;
-webkit-appearance: none;
}

input:focus, select:focus, textarea:focus {
border-color: var(–gold);
background: #fff;
}

input::placeholder, textarea::placeholder { color: #bbb; }

textarea { resize: none; height: 80px; }

.submit-btn {
width: 100%;
margin-top: 20px;
background: #25D366;
color: #000;
border: none;
border-radius: 50px;
padding: 16px;
font-family: ‘Outfit’, sans-serif;
font-size: 15px;
font-weight: 700;
letter-spacing: 0.03em;
cursor: pointer;
display: flex;
align-items: center;
justify-content: center;
gap: 10px;
box-shadow: 0 8px 24px rgba(37,211,102,0.3);
transition: transform 0.2s, box-shadow 0.2s;
}

.submit-btn:hover {
transform: translateY(-2px);
box-shadow: 0 12px 32px rgba(37,211,102,0.45);
}

.submit-btn svg { width: 20px; height: 20px; }

.privacy-note {
text-align: center;
font-size: 11px;
color: #bbb;
margin-top: 12px;
line-height: 1.6;
}

/* ─── FOOTER ─── */
footer {
max-width: 680px;
margin: 0 auto;
padding: 20px 24px;
display: flex;
justify-content: space-between;
align-items: center;
}

.brand {
font-family: ‘Cormorant Garamond’, serif;
font-size: 18px;
font-weight: 700;
color: #555;
}
.brand span { color: var(–gold); }

.footer-info { font-size: 11px; color: #aaa; }

/* success overlay */
.success-overlay {
display: none;
position: fixed;
inset: 0;
background: rgba(0,0,0,0.7);
z-index: 999;
align-items: center;
justify-content: center;
padding: 24px;
}
.success-overlay.show { display: flex; }
.success-box {
background: #fff;
border-radius: 20px;
padding: 40px 32px;
max-width: 340px;
text-align: center;
}
.success-icon { font-size: 48px; margin-bottom: 16px; }
.success-title { font-family:‘Cormorant Garamond’,serif; font-size:26px; font-weight:700; color:#111; margin-bottom:8px; }
.success-sub { font-size:13px; color:#888; line-height:1.6; margin-bottom:24px; }
.success-close {
background: var(–gold);
color: #000;
border: none;
border-radius: 50px;
padding: 12px 28px;
font-family:‘Outfit’,sans-serif;
font-size:14px;
font-weight:600;
cursor:pointer;
}

@media (max-width: 480px) {
.form-grid { grid-template-columns: 1fr; }
.benefits  { grid-template-columns: 1fr 1fr; }
.form-section { padding: 28px 20px 32px; border-radius: 0; }
}
</style>

</head>
<body>

<!-- HERO -->

<div class="hero">
  <div class="top-strip">✦ Servicio Profesional de Digitalización de Cartas ✦</div>
  <div class="hero-inner">
    <div class="hero-content">
      <div class="eyebrow">
        <div class="eyebrow-line"></div>
        <span class="eyebrow-text">Moderniza tu negocio hoy</span>
      </div>
      <h1>
        Tu carta
        <span class="gold">en un QR</span>
        <span class="muted">— Sin complicaciones —</span>
      </h1>
      <p class="hero-sub">
        Convierto tu menú físico en una carta digital que tus clientes leen al instante desde su celular — sin apps, sin esperas, sin costos mensuales.
      </p>

```
  <div class="transform-row">
    <div class="c-side old">
      <div class="c-icon">📋</div>
      <div class="c-lbl">Antes</div>
      <div class="c-desc">Carta física que se pierde, ensucia y obliga a esperar al mozo</div>
    </div>
    <div class="arrow-col"><span class="arrow-sym">→</span></div>
    <div class="c-side new">
      <div class="c-icon">📱</div>
      <div class="c-lbl">Ahora</div>
      <div class="c-desc">Carta digital siempre disponible al instante desde el celular</div>
    </div>
  </div>

  <div class="benefits">
    <div class="ben">
      <div class="ben-icon">⚡</div>
      <div class="ben-title">Entrega rápida</div>
      <div class="ben-text">Tu carta lista en tiempo récord</div>
    </div>
    <div class="ben">
      <div class="ben-icon">🔄</div>
      <div class="ben-title">Actualizable</div>
      <div class="ben-text">Cambia precios cuando quieras</div>
    </div>
    <div class="ben">
      <div class="ben-icon">📲</div>
      <div class="ben-title">Sin apps</div>
      <div class="ben-text">Solo la cámara del celular</div>
    </div>
  </div>
</div>
```

  </div>
</div>

<!-- FORM -->

<div class="form-section">
  <div class="form-title">Queremos <span>conocerte</span></div>
  <p class="form-sub">Déjanos tus datos y te contactamos por WhatsApp en minutos.</p>

  <div class="form-grid">
    <div class="field">
      <label>Nombre *</label>
      <input type="text" id="nombre" placeholder="Tu nombre" required>
    </div>
    <div class="field">
      <label>Apellidos *</label>
      <input type="text" id="apellido" placeholder="Tus apellidos" required>
    </div>
    <div class="field">
      <label>WhatsApp *</label>
      <input type="tel" id="telefono" placeholder="9XX XXX XXX" required>
    </div>
    <div class="field">
      <label>Tipo de negocio *</label>
      <select id="negocio">
        <option value="" disabled selected>Selecciona...</option>
        <option>Restaurante</option>
        <option>Cafetería</option>
        <option>Bar / Pub</option>
        <option>Pollería</option>
        <option>Cevichería</option>
        <option>Otro</option>
      </select>
    </div>
    <div class="field full">
      <label>Nombre de tu negocio *</label>
      <input type="text" id="nombre-negocio" placeholder="Ej: Restaurante El Sabor">
    </div>
    <div class="field full">
      <label>¿Alguna consulta? (opcional)</label>
      <textarea id="consulta" placeholder="Cuéntanos más sobre lo que necesitas..."></textarea>
    </div>
  </div>

  <button class="submit-btn" onclick="enviarWhatsApp()">
    <svg viewBox="0 0 24 24" fill="black">
      <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/>
    </svg>
    Enviar por WhatsApp
  </button>

  <p class="privacy-note">🔒 Tus datos son privados y solo serán usados para contactarte.</p>
</div>

<footer>
  <div class="brand">Carta<span>QR</span> Pro</div>
  <div class="footer-info">📍 Perú · WhatsApp: 977 927 759</div>
</footer>

<!-- SUCCESS OVERLAY -->

<div class="success-overlay" id="successOverlay">
  <div class="success-box">
    <div class="success-icon">🎉</div>
    <div class="success-title">¡Listo!</div>
    <p class="success-sub">Te estamos redirigiendo a WhatsApp con tu información. ¡Te respondemos en minutos!</p>
    <button class="success-close" onclick="document.getElementById('successOverlay').classList.remove('show')">Cerrar</button>
  </div>
</div>

<script>
function enviarWhatsApp() {
  const nombre   = document.getElementById('nombre').value.trim();
  const apellido = document.getElementById('apellido').value.trim();
  const telefono = document.getElementById('telefono').value.trim();
  const negocio  = document.getElementById('negocio').value;
  const nomNeg   = document.getElementById('nombre-negocio').value.trim();
  const consulta = document.getElementById('consulta').value.trim();

  if (!nombre || !apellido || !telefono || !negocio) {
    alert('Por favor completa los campos obligatorios (*)');
    return;
  }

  const msg = `¡Hola! Me interesa el servicio de Carta QR 📱\n\n` +
    `👤 *Nombre:* ${nombre} ${apellido}\n` +
    `📞 *Mi WhatsApp:* ${telefono}\n` +
    `🍽️ *Tipo de negocio:* ${negocio}\n` +
    `🏪 *Nombre del negocio:* ${nomNeg || 'No indicado'}\n` +
    (consulta ? `💬 *Consulta:* ${consulta}\n` : '') +
    `\nQuisiera recibir más información. ¡Gracias!`;

  document.getElementById('successOverlay').classList.add('show');

  setTimeout(() => {
    window.open('https://wa.me/51977927759?text=' + encodeURIComponent(msg), '_blank');
  }, 800);
}
</script>

</body>
</html>