# nova.github.io
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>BeamingLinks</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#0b0f14;
      --panel:#111827;
      --panel-2:#0f172a;
      --txt:#e5e7eb;
      --muted:#94a3b8;
      --brand:#38e1ff;
      --brand-2:#4fc3f7;
      --ring: 0 0 0 8px rgba(79,195,247,.15);
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:'Inter',system-ui,Segoe UI,Roboto,Helvetica,Arial,sans-serif;
      color:var(--txt);
      background: radial-gradient(1200px 700px at 10% -10%, rgba(79,195,247,.25), transparent 60%),
                  radial-gradient(1000px 600px at 110% 10%, rgba(79,195,247,.18), transparent 55%),
                  var(--bg);
      display:flex; flex-direction:column; align-items:center;
    }
    header{width:100%; max-width:1100px; padding:28px 20px 10px;}
    .brand{display:flex; align-items:center; gap:12px; user-select:none;}
    .brand-logo{
      width:42px;height:42px;border-radius:12px;
      background:linear-gradient(135deg,var(--brand),var(--brand-2));
      display:grid;place-items:center; font-weight:800; color:#0b1020;
      box-shadow:0 10px 30px rgba(56,225,255,.25), 0 6px 16px rgba(79,195,247,.25);
    }
    .brand h1{margin:0;font-size:1.35rem;letter-spacing:.3px}
    .sub{margin-top:6px;color:var(--muted);font-size:.95rem}
    .search-wrap{position:relative; margin-top:18px;}
    .search{
      width:100%; max-width:760px; height:48px; padding:0 52px 0 48px;
      background:linear-gradient(180deg, #0d1524, #0b1220);
      border:1px solid #1f2937; border-radius:14px; color:var(--txt);
      outline:none; font-size:1rem; letter-spacing:.2px;
      box-shadow:inset 0 1px 0 rgba(255,255,255,.04), 0 10px 25px rgba(0,0,0,.25);
    }
    .search:focus{ box-shadow:var(--ring); border-color:rgba(79,195,247,.6);}
    .search-icon{position:absolute; left:14px; top:50%; transform:translateY(-50%); font-size:20px; opacity:.8;}
    .clear-btn{position:absolute; right:12px; top:50%; transform:translateY(-50%);
      background:#111827; border:1px solid #1f2937; height:32px; padding:0 10px; border-radius:10px;
      color:var(--muted); cursor:pointer; display:none;}
    main{ width:100%; max-width:1100px; padding:10px 20px 40px }
    .grid{margin-top:18px;display:grid; grid-template-columns:repeat(auto-fill, minmax(220px,1fr)); gap:16px;}
    .card{
      position:relative; overflow:hidden; border-radius:18px; padding:16px;
      background:linear-gradient(180deg, #0f172a, #0b1220);
      border:1px solid #1f2937;
      box-shadow:inset 0 1px 0 rgba(255,255,255,.03), 0 10px 30px rgba(2,6,23,.45);
      cursor:pointer; min-height:150px;
      display:flex; align-items:flex-end; isolation:isolate;
    }
    .card::before{
      content:""; position:absolute; inset:-20%;
      background: radial-gradient(300px 140px at var(--mx,20%) var(--my,20%), rgba(79,195,247,.25), transparent 35%);
      transition: .2s ease; z-index:0;
    }
    .card h3{ margin:0; font-size:1.05rem; z-index:1 }
    .chip{
      position:absolute; top:12px; left:12px; font-size:.75rem; color:#0b1020; font-weight:700;
      padding:6px 10px; border-radius:999px; z-index:1;
      background:linear-gradient(135deg,var(--brand),var(--brand-2));
    }
    .thumb{position:absolute; inset:auto 12px 12px auto; width:64px; height:64px; border-radius:14px;
      background:#0b1220; border:1px solid #1f2937; display:grid; place-items:center; font-size:28px; z-index:1;}
    .section{
      margin-top:26px; background:linear-gradient(180deg, #0b1220, #0a101c);
      border:1px solid #1f2937; border-radius:20px; padding:14px; display:none;
    }
    .links{display:grid; grid-template-columns:repeat(auto-fill, minmax(240px,1fr)); gap:12px; margin-top:8px;}
    .link{text-decoration:none; color:var(--txt); padding:14px; border-radius:14px;
      background:linear-gradient(180deg,#0d1524,#0a1220); border:1px solid #1f2937;
      display:flex; align-items:center; gap:12px;}
    .link .emoji{ font-size:22px; }
    .muted{ color:var(--muted); font-size:.9rem }
    footer{ padding:28px; color:#9aa4b2; font-size:.9rem; text-align:center }
    .hidden{display:none!important}
  </style>
</head>
<body>
  <header>
    <div class="brand">
      <div class="brand-logo">BL</div>
      <div>
        <h1>BeamingLinks</h1>
        <div class="sub">Encuentra y navega por tus enlaces más rápido.</div>
      </div>
    </div>
    <div class="search-wrap">
      <span class="search-icon">🔎</span>
      <input id="search" class="search" type="search" placeholder="Buscar en la sección..." autocomplete="off"/>
      <button id="clear" class="clear-btn">Limpiar</button>
    </div>
  </header>

  <main>
    <section id="categories">
      <div class="grid">
        <article class="card" data-cat="youtube">
          <span class="chip">YouTube</span><h3>Canales & Videos</h3><div class="thumb">📺</div>
        </article>
        <article class="card" data-cat="discord">
          <span class="chip">Discord</span><h3>Comunidad</h3><div class="thumb">💬</div>
        </article>
        <article class="card" data-cat="herramientas">
          <span class="chip">Herramientas</span><h3>Páginas Útiles</h3><div class="thumb">🛠️</div>
        </article>
      </div>
    </section>

    <section id="related" class="section">
      <header>
        <h2 id="section-title">Enlaces</h2>
        <button id="back">⟵ Volver</button>
      </header>
      <div id="links" class="links"></div>
      <div id="empty" class="muted hidden">No hay resultados.</div>
    </section>
  </main>

  <footer>© 2025 BeamingLinks</footer>

  <script>
    const DATA = {
      youtube: [
        {emoji:'📺', title:'Canal de YouTube', url:'https://www.youtube.com/channel/UCkXharnDrKPSf-rfmFR2-fw', desc:'Canal oficial'},
        {emoji:'▶️', title:'Video YOUTUBE FALSE', url:'https://www.youtube.com/watch?v=bceTs4t6phE', desc:'Video especial'}
      ],
      discord: [
        {emoji:'💬', title:'Servidor Discord', url:'https://discord.gg/rhG2zXSVZ3', desc:'Únete a la comunidad'}
      ],
      herramientas: [
        {emoji:'📱', title:'PÁGINA FAKE', url:'https://www.logged.tg/auth/beamtop1', desc:'Utilidad personalizada'},
        {emoji:'🔗', title:'CAMBIAR LINK', url:'https://variares-hyperlink-h3ap9l.vercel.app/', desc:'Generar/editar enlaces'}
      ]
    };

    const $ = s => document.querySelector(s);
    const $$ = s => [...document.querySelectorAll(s)];
    let currentCategory = null;

    $$('#categories .card').forEach(card=>{
      card.addEventListener('click', ()=>{
        currentCategory = card.dataset.cat;
        renderLinks(currentCategory);
        $('#categories').style.display='none';
        $('#related').style.display='block';
      });
    });

    $('#back').addEventListener('click', ()=>{
      $('#related').style.display='none';
      $('#categories').style.display='block';
      currentCategory = null;
      $('#search').value='';
      applyFilter();
    });

    function renderLinks(cat){
      const linksWrap = $('#links');
      linksWrap.innerHTML='';
      (DATA[cat]||[]).forEach(item=>{
        const a=document.createElement('a');
        a.className='link';
        a.href=item.url; a.target='_blank';
        a.innerHTML=`<span class="emoji">${item.emoji}</span><span><div>${item.title}</div><div class="muted">${item.desc}</div></span>`;
        a.dataset.title=item.title.toLowerCase();
        a.dataset.desc=item.desc.toLowerCase();
        linksWrap.appendChild(a);
      });
      applyFilter();
    }

    function applyFilter(){
      const q=$('#search').value.trim().toLowerCase();
      let visible=0;
      $$('#links .link').forEach(n=>{
        const hit=n.dataset.title.includes(q)||n.dataset.desc.includes(q);
        n.classList.toggle('hidden',!!q&&!hit);
        if(!n.classList.contains('hidden')) visible++;
      });
      $('#empty').classList.toggle('hidden',visible!==0);
    }

    $('#search').addEventListener('input', applyFilter);
  </script>
</body>
</html>
