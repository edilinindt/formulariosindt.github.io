<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Formulários de Manutenção</title>

  <style>
    :root{
      --bg:#0b1220;
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
      padding: 22px 18px 10px;
      max-width: 1060px;
      margin: 0 auto;
    }

    .brand{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:14px;
      flex-wrap:wrap;
      margin-bottom: 10px;
    }

    .logo{
      height: 56px;
      width: auto;
      max-width: 100%;
      display:block;
      filter: drop-shadow(0 10px 24px rgba(0,0,0,.45));
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
      max-width: 1060px;
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
      grid-template-columns: repeat( auto-fit, minmax(280px, 1fr) );
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
      min-height: 138px;
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
      max-width: 1060px;
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
      .logo{filter:none}
    }
  </style>
</head>

<body>
  <header>
    <div class="brand">
      <!-- ✅ Logo anexado: deixe o arquivo na mesma pasta do HTML -->
      <img class="logo" src="LOGO%20COL%20BRANCO.png" alt="Logo INDT" />
      <div class="title">
        <h1>Formulários de Manutenção Predial</h1>
        <span class="badge">Acesso rápido (celular / tablet)</span>
      </div>
    </div>

    <p class="subtitle">
      Toque em <b>Abrir</b> para acessar o formulário. Use <b>Copiar link</b> para compartilhar no WhatsApp.
    </p>
  </header>

  <main>
    <div class="toolbar">
      <div class="search" role="search">
        <small>🔎</small>
        <input id="q" type="search" placeholder="Buscar (ex.: iluminação, água, SPDA, incêndio, dreno...)" />
      </div>
      <button class="btn" id="btnLimpar" type="button">Limpar busca</button>
      <button class="btn green" id="btnImprimir" type="button">Imprimir / PDF</button>
    </div>

    <section class="grid" id="lista">

      <!-- 1 -->
      <article class="card" data-tags="iluminação geral lampadas luminarias circuito eletrica">
        <span class="code">RE-FA-00-00-005</span>
        <h2>ILUMINAÇÃO GERAL</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/af85422b29f94e0b292b39ebe992b8df?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/af85422b29f94e0b292b39ebe992b8df?r=use1">Copiar link</button>
        </div>
      </article>

      <!-- 2 -->
      <article class="card" data-tags="iluminação emergencia luz autonomia bateria bloco emergencia">
        <span class="code">RE-FA-00-00-005</span>
        <h2>ILUMINAÇÃO DE EMERGÊNCIA</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/9d92da93b664738365dcddf13464b670?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/9d92da93b664738365dcddf13464b670?r=use1">Copiar link</button>
        </div>
      </article>

      <!-- 3 -->
      <article class="card" data-tags="wc banheiro masculino feminino pne acessibilidade loucas metais">
        <span class="code">RE-FA-00-00-005</span>
        <h2>WCs MASCULINOS E FEMININO / PNEs</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/a827d3dfed034c0cf1b8ce725a65b249?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/a827d3dfed034c0cf1b8ce725a65b249?r=use1">Copiar link</button>
        </div>
      </article>

      <!-- 4 -->
      <article class="card" data-tags="termografia ponto termografado aquecimento eletrica conexao">
        <span class="code">RE-FA-00-00-005</span>
        <h2>ANÁLISE PONTO TERMOGRAFADO</h2>
        <p class="meta">Inspeção / análise</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/f85c257d30f6c7afb1e8321b8c369e99?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/f85c257d30f6c7afb1e8321b8c369e99?r=use1">Copiar link</button>
        </div>
      </article>

      <!-- 5 -->
      <article class="card" data-tags="agua abastecimento bombas reservatorio cisterna caixa dagua">
        <span class="code">RE-FA-00-00-004</span>
        <h2>SISTEMA DE ABASTECIMENTO DE ÁGUA</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/16bedb844769edc0f540b5fa6a43ef34?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/16bedb844769edc0f540b5fa6a43ef34?r=use1">Copiar link</button>
        </div>
      </article>

      <!-- 6 -->
      <article class="card" data-tags="canaletas drenagem pluvial chuva ralo calha">
        <span class="code">RE-FA-00-00-004</span>
        <h2>INSPEÇÃO CANALETAS DE DRENAGEM PLUVIAL</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/a8331b3269f0095aeb41c9f98c8bd154?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/a8331b3269f0095aeb41c9f98c8bd154?r=use1">Copiar link</button>
        </div>
      </article>

      <!-- 7 -->
      <article class="card" data-tags="incendio combate incendio hidrante extintor sprinklers alarme">
        <span class="code">RE-FA-00-00-007</span>
        <h2>INSPEÇÃO SISTEMA DE COMBATE À INCÊNDIO</h2>
        <p class="meta">Inspeção / segurança</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/45eb590e956d8b2c1909f95db04b01c0?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/45eb590e956d8b2c1909f95db04b01c0?r=use1">Copiar link</button>
        </div>
      </article>

      <!-- 8 -->
      <article class="card" data-tags="infraestrutura chamber motorola telecom rack energia">
        <span class="code">RE-FA-00-00-008</span>
        <h2>INSPEÇÃO INFRAESTRUTURA CHAMBER MOTOROLA</h2>
        <p class="meta">Inspeção / infraestrutura</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/e3e9a3a5f3f445bb341e429accdb8463?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/e3e9a3a5f3f445bb341e429accdb8463?r=use1">Copiar link</button>
        </div>
      </article>

      <!-- 9 -->
      <article class="card" data-tags="portao automatico cancela motor controle acesso">
        <span class="code">RE-FA-00-00-005</span>
        <h2>PORTÃO AUTOMÁTICO E CANCELA</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/1d175efa1d2aa969598eaebeed5fae2d?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/1d175efa1d2aa969598eaebeed5fae2d?r=use1">Copiar link</button>
        </div>
      </article>

      <!-- 10 -->
      <article class="card" data-tags="ventiladores cubico transformador 750kva ventilacao subestacao">
        <span class="code">RE-FA-00-00-005</span>
        <h2>VENTILADORES CUBÍCO TRANSFORMADOR 750KVA</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/1b870b07681d458325d74d16bb9899b8?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/1b870b07681d458325d74d16bb9899b8?r=use1">Copiar link</button>
        </div>
      </article>

      <!-- 11 -->
      <article class="card" data-tags="spda eletrica aterramento para-raios malha equipotencial">
        <span class="code">RE-FA-00-00-005</span>
        <h2>ELÉTRICA SPDA</h2>
        <p class="meta">Inspeção / elétrica</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/95cb9ac6ce41ead34c7d9dd0f570592d?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/95cb9ac6ce41ead34c7d9dd0f570592d?r=use1">Copiar link</button>
        </div>
      </article>

      <!-- 12 -->
      <article class="card" data-tags="bombas bomba recalque pressurizacao agua sistema">
        <span class="code">RE-FA-00-00-006</span>
        <h2>BOMBAS</h2>
        <p class="meta">Inspeção / manutenção</p>
        <div class="actions">
          <a class="open" target="_blank" rel="noopener" href="https://forms.monday.com/forms/a88023441b56774c5028b6d943daea39?r=use1">Abrir</a>
          <button class="copy" type="button" data-link="https://forms.monday.com/forms/a88023441b56774c5028b6d943daea39?r=use1">Copiar link</button>
        </div>
      </article>

    </section>
  </main>

  <footer>
    Dica: no celular, use “Adicionar à Tela de Início” para virar um atalho tipo app.
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
