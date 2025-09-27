<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Carta para Evelyn</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;500;700;900&family=Great+Vibes&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#fff0f4;
      --card-bg: rgba(255,255,255,0.75);
      --accent:#ff6b8a;
      --muted:#6b6b6b;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      min-height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
      font-family: 'Montserrat', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
      background: radial-gradient(ellipse at 10% 10%, #ffeef6 0%, var(--bg) 20%), radial-gradient(ellipse at 90% 90%, #fff6f4 0%, var(--bg) 30%);
      overflow:hidden;
    }
    .hearts {
      position:fixed; inset:0; pointer-events:none; z-index:0; overflow:hidden;
    }
    .heart{
      position:absolute; width:48px; height:48px; transform:rotate(45deg);
      left:50%; top:50%;
      background:linear-gradient(45deg,#ff9db2,#ff6b8a);
      border-radius:8px 8px 0 0;
      opacity:0.85;
      animation:floatUp linear infinite;
      box-shadow:0 6px 18px rgba(255,107,138,0.25);
    }
    .heart:before, .heart:after{
      content:''; position:absolute; width:48px; height:48px; background:inherit; border-radius:50%;
      top:-24px; left:0;
    }
    .heart:after{ left:-24px; top:0 }
    @keyframes floatUp{
      0%{ transform: translate3d(var(--x,0),var(--y,0),0) scale(0.9) rotate(45deg); opacity:0 }
      10%{ opacity:0.9 }
      100%{ transform: translate3d(var(--x,0),-140vh,0) scale(1.05) rotate(45deg); opacity:0 }
    }
    .card{
      position:relative;
      z-index:2;
      width:min(920px,94vw);
      max-width:920px;
      padding: clamp(20px,4vw,48px);
      border-radius:20px;
      background:var(--card-bg);
      box-shadow: 0 12px 40px rgba(0,0,0,0.12);
      backdrop-filter: blur(6px) saturate(120%);
      display:grid;
      grid-template-columns: 1fr 360px;
      gap:24px;
      align-items:center;
    }
    .monogram{
      display:flex; align-items:center; justify-content:center;
      background: linear-gradient(135deg, rgba(255,107,138,0.08), rgba(255,221,229,0.08));
      border-radius:16px; padding:20px;
      min-height:240px;
      position:relative;
    }
    .initial{
      font-family: 'Great Vibes', cursive;
      font-size:9.5rem; line-height:1; color: rgba(255,107,138,0.18);
      -webkit-text-stroke: 1px rgba(255,107,138,0.06);
      text-shadow: 0 6px 30px rgba(255,107,138,0.05);
    }
    .heart-badge{
      position:absolute; top:18px; right:18px; width:64px; height:64px; border-radius:14px; display:flex; align-items:center; justify-content:center;
      background: linear-gradient(135deg,#ff6b8a,#ff9db2); color:white; font-weight:700; font-size:20px; box-shadow:0 8px 20px rgba(255,107,138,0.2);
    }
    .content{
      padding:12px 6px; color:#222; 
    }
    .content h1{ margin:0 0 8px 0; font-size:clamp(22px,3.2vw,32px); color:#b8003a }
    .content .meta{ color:var(--muted); margin-bottom:14px }
    .letter{
      background:rgba(255,255,255,0.6); padding:18px; border-radius:12px; min-height:200px; font-size:1.05rem; line-height:1.6; color:#2b2b2b;
    }
    .controls{ display:flex; gap:8px; margin-top:12px }
    .btn{ padding:10px 14px; border-radius:10px; border:0; cursor:pointer; font-weight:600 }
    .btn--accent{ background:linear-gradient(90deg,#ff6b8a,#ff9db2); color:white }
    .btn--muted{ background:transparent; border:1px solid rgba(0,0,0,0.06) }
    @media (max-width:880px){
      .card{ grid-template-columns: 1fr; }
      .monogram{ order: -1 }
      .initial{ font-size:6.5rem }
    }
    .note{ margin-top:12px; color:var(--muted); font-size:0.9rem }
  </style>
</head>
<body>
  <div class="hearts" aria-hidden="true"></div>
  <main class="card" role="main">
    <section class="content">
      <h1>Para Evelyn</h1>
      <div class="meta">Una carta virtual hecha con cariño por Aarón.</div>
      <div class="letter">
        Jaajsjjs<br>
        Hola mi amorsh<br>
        Muak<br>
        Mira<br>
        No soy tan bueno con las cartas<br>
        No como tu mi niña bella<br>
        Pero si puedo hacer algo similar jsjs<br>
        Gracias por todo lo que hemos vivido juntos<br>
        Y aunque no siempre estamos de acuerdo en algunas cosas te agradezco por darme todo tu apoyo, a veces lo que nos decimos enojados o alterados podrían lastimar al otro mi cielo<br>
        Pero todo eso es parte de nuestra relación mi cielo<br>
        Te amoooooo con todo mi corazóncito<br>
        Mi mujer, mi amorsh,  mi novia, mi Evelyn<br>
        Muak<br>
        Le pido a Dios un futuro a tu lado mi cielo<br>
        Y con todo mi amor<br>
        Esta carta o esta página web jajajaajjsjs<br>
        Es para ti❤️
      </div>
    </section>
    <aside class="monogram" aria-hidden="true">
      <div class="initial">E</div>
      <div class="heart-badge">E</div>
    </aside>
  </main>
  <script>
    const heartsContainer = document.querySelector('.hearts');
    const HEARTS = 18;
    for(let i=0;i<HEARTS;i++){
      const h = document.createElement('div');
      h.className='heart';
      const size = Math.floor(Math.random()*36)+28;
      h.style.width = size+'px'; h.style.height = size+'px';
      h.style.setProperty('--x', (Math.random()*120 - 60)+'vw');
      h.style.setProperty('--y', (Math.random()*60 + 20)+'vh');
      const left = Math.random()*100; h.style.left = left+'%';
      const delay = -(Math.random()*18).toFixed(2)+'s';
      const dur = (10 + Math.random()*22).toFixed(2) + 's';
      h.style.animationDuration = dur; h.style.animationDelay = delay;
      heartsContainer.appendChild(h);
    }
  </script>
</body>
</html>

# Carta-html-
