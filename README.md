<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Formulários de Manutenção</title>

  <style>
    :root{
      --bg:#0b1220;
      --card:#111a2e;
      --text:#e5e7eb;
      --muted:#9ca3af;
      --border:rgba(255,255,255,.10);
      --shadow: 0 10px 30px rgba(0,0,0,.35);
      --radius:18px;
      --blue: rgba(56,189,248,.12);
      --blueBorder: rgba(56,189,248,.35);
      --green: rgba(34,197,94,.10);
      --greenBorder: rgba(34,197,94,.35);
    }

    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Arial, sans-serif;
      background: radial-gradient(1200px 700px at 20% 10%, rgba(56,189,248,.18), transparent 60%),
                  radial-gradient(900px 500px at 90% 20%, rgba(34,197,94,.16), transparent 55%),
                  var(--bg);
      color:var(--text);
      min-height:100vh;
    }

    header{
      padding: 28px 18px 16px;
      max-width: 980px;
      margin: 0 auto;
    }
    .title{
      display:flex;
      gap:12px;
      align-items:center;
      flex-wrap:wrap;
    }
    h1{ margin:0; font-size: 20px; letter-spacing:.2px; }
    .badge{
      padding:6px 10px;
      border:1px solid var(--border);
      border-radius:999px;
      color:var(--muted);
      font-size:12px;
      background: rgba(255,255,255,.04);
    }
    .subtitle{
      margin:10px 0 0;
      color:var(--muted);
      font-size: 14px;
      line-height: 1.4;
    }

    main{
      max-width: 980px;
      margin: 0 auto;
      padding: 0 18px 28px;
    }

    .toolbar{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      margin: 16px 0 14px;
    }
    .search{
      flex: 1 1 260px;
      display:flex;
      align-items:center;
      gap:10px;
      padding: 12px 14px;
      border-radius: 14px;
      background: rgba(255,255,255,.04);
      border:1px solid var(--border);
      box-shadow: var(--shadow);
    }
    .search input{
      width:100%;
      border:0;
      outline:0;
      background:transparent;
      color:var(--text);
      font-size: 14px;
    }
    .search small{color:var(--muted)}
    .btn{
      flex: 0 0 auto;
      padding: 12px 14px;
      border-radius: 14px;
      border:1px solid var(--border);
      background: rgba(255,255,255,.04);
      color: var(--text);
      cursor:pointer;
      box-shadow: var(--shadow);
      font-size: 14px;
    }
    .btn:hover{border-color: rgba(255,255,255,.22)}
    .btn.green{
      border-color: rgba(34,197,94,.35);
      background: rgba(34,197,94,.10);
    }

    .grid{
      display:grid;
      grid-template-columns: repeat( auto-fit, minmax(260px, 1fr) );
      gap: 12px;
      margin-top: 10px;
    }

    .card{
      background: linear-gradient(180deg, rgba(255,255,255,.06), rgba(255,255,255,.03));
      border:1px solid var(--border);
      border-radius: var(--radius);
      padding: 14px;
      box-shadow: var(--shadow);
      display:flex;
      flex-direction:column;
      gap:10px;
      min-height: 130px;
    }
    .code{
      display:inline-block;
      font-size: 12px;
      color: var(--muted);
      border: 1px solid var(--border);
      border-radius: 999px;
      padding: 6px 10px;
      width: fit-content;
      background: rgba(255,255,255,.03);
    }
    .card h2{
      margin:0;
      font-size: 16px;
      line-height:1.25;
    }
    .meta{
      margin:0;
      color:var(--muted);
      font-size: 12px;
    }

    .actions{
      display:flex;
      gap:10px;
      margin-top:auto;
      flex-wrap:wrap;
    }
    a.open{
      flex: 1 1 140px;
      text-decoration:none;
      text-align:center;
      padding: 11px 12px;
      border-radius: 14px;
      background: var(--blue);
      border:1px solid var(--blueBorder);
      color: var(--text);
      font-weight:600;
    }
    a.open:hover{border-color: rgba(56,189,248,.55)}

    button.copy{
      flex: 1 1 140px;
      padding: 11px 12px;
      border-radius: 14px;
      background: var(--green);
      border:1px solid var(--greenBorder);
      color: var(--text);
      font-weight:600;
      cursor:pointer;
    }
    button.copy:hover{border-color: rgba(34,197,94,.55)}

    footer{
      max-width: 980px;
      margin: 0 auto;
      padding: 0 18px 22px;
      color: var(--muted);
      font-size: 12px;
      line-height: 1.4;
    }

    .hidden{display:none !important;}

    @media print{
      body{background:#fff;color:#000}
      .toolbar, .actions, .badge {display:none !important;}
      .card{box-shadow:none}
      .code{border-color:#ccc}
    }
  </style>
</head>

<body>
  <header>
    <div class="title">
      <h1>Formulários de Manutenção Predial</h1>
     
    </div>
    <p class="subtitle">
      Toque em <b>Abrir</b> para acessar o formulário. Use <b>Copiar link</b> para compartilhar no WhatsApp.
    </p>
  </header>

  <main>
    <div class="toolbar">
      <div class="search" role="search">
        <small>🔎</small>
        <input id="q" type="search" placeholder="Buscar (ex.: nobreak, gerador, subestação, água...)" />
      </div>
      <button class="btn" id="btnLimpar" type="button">Limpar busca</button>
      <button class="btn green" id="btnImprimir" type="button">Imprimir / PDF</button>
    </div>

    <section class="grid" id="lista">

      <article class="card" data-tags="compressor ar comprimido utilidades pneumático">
        <span class="code">RE-FA-00-00-006-2020-03</span>
        <h2>COMPRESSOR DE AR</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener"
             href="https://forms.monday.com/forms/5a88fb8a34aeaf178d018e12e62ad569?r=use1">Abrir</a>
          <button class="copy" type="button"
             data-link="https://forms.monday.com/forms/5a88fb8a34aeaf178d018e12e62ad569?r=use1">Copiar link</button>
        </div>
      </article>

      <article class="card" data-tags="nobreak ups energia bateria autonomia">
        <span class="code">RE-FA-00-00-005-2020-03</span>
        <h2>NOBREAK</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener"
             href="https://forms.monday.com/forms/5be57ed88eb06075e69915fb4f09e8c5?r=use1">Abrir</a>
          <button class="copy" type="button"
             data-link="https://forms.monday.com/forms/5be57ed88eb06075e69915fb4f09e8c5?r=use1">Copiar link</button>
        </div>
      </article>

      <article class="card" data-tags="subestação eletrica transformador disjuntor media tensão">
        <span class="code">RE-FA-00-00-005-2020-03</span>
        <h2>SUBESTAÇÃO</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener"
             href="https://forms.monday.com/forms/d2ced4450526fb04bee7cad6b77d36d4?r=use1">Abrir</a>
          <button class="copy" type="button"
             data-link="https://forms.monday.com/forms/d2ced4450526fb04bee7cad6b77d36d4?r=use1">Copiar link</button>
        </div>
      </article>

      <article class="card" data-tags="grupo gerador gerador diesel energia emergencia">
        <span class="code">RE-FA-00-00-005-2020-03</span>
        <h2>GRUPO GERADOR</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener"
             href="https://forms.monday.com/forms/44b86f0dbacca72933e44f4c520c4682?r=use1">Abrir</a>
          <button class="copy" type="button"
             data-link="https://forms.monday.com/forms/44b86f0dbacca72933e44f4c520c4682?r=use1">Copiar link</button>
        </div>
      </article>

      <article class="card" data-tags="bombas recalque água reservatório cisterna caixa dagua">
        <span class="code">RE-FA-00-00-004-2020-03</span>
        <h2>BOMBAS DE RECALQUE E RESERVATÓRIO DE ÁGUA</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener"
             href="https://forms.monday.com/forms/d00dd9a0e429f96efd24d89c300c0699?r=use1">Abrir</a>
          <button class="copy" type="button"
             data-link="https://forms.monday.com/forms/d00dd9a0e429f96efd24d89c300c0699?r=use1">Copiar link</button>
        </div>
      </article>

    </section>
  </main>

  <footer>
    Se quiser hospedar: pode colocar esse arquivo em um servidor interno, GitHub Pages, ou até compartilhar por nuvem.
    <br/>Dica: no iPhone/iPad/Android, dá pra “Adicionar à Tela de Início” e virar um atalho tipo app.
  </footer>

  <script>
    const q = document.getElementById('q');
    const lista = document.getElementById('lista');
    const cards = Array.from(lista.querySelectorAll('.card'));
    const btnLimpar = document.getElementById('btnLimpar');
    const btnImprimir = document.getElementById('btnImprimir');

    function normalizar(s){
      return (s || '')
        .toLowerCase()
        .normalize('NFD').replace(/[\u0300-\u036f]/g, '');
    }

    function filtrar(){
      const termo = normalizar(q.value.trim());
      cards.forEach(card => {
        const texto = normalizar(card.innerText);
        const tags = normalizar(card.getAttribute('data-tags'));
        const ok = !termo || texto.includes(termo) || tags.includes(termo);
        card.classList.toggle('hidden', !ok);
      });
    }

    q.addEventListener('input', filtrar);
    btnLimpar.addEventListener('click', () => { q.value=''; filtrar(); q.focus(); });
    btnImprimir.addEventListener('click', () => window.print());

    document.addEventListener('click', async (e) => {
      const btn = e.target.closest('button.copy');
      if(!btn) return;

      const link = btn.getAttribute('data-link');
      try{
        await navigator.clipboard.writeText(link);
        const antigo = btn.textContent;
        btn.textContent = 'Copiado ✅';
        setTimeout(()=> btn.textContent = antigo, 1200);
      }catch(err){
        prompt('Copie o link:', link);
      }
    });
  </script>
</body>
</html>

