
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rota Atlântica — Trabalho de Geografia</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --navy-deep:#0D2436;
    --navy-mid:#123449;
    --navy-line:#22475e;
    --sand:#E9DEC4;
    --paper:#F6F1E4;
    --coral:#E2622E;
    --coral-dim:#b94f24;
    --teal:#4FA79A;
    --ink:#12242E;
    --serif: 'Fraunces', Georgia, 'Times New Roman', serif;
    --sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  }

  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    font-family:var(--sans);
    background:var(--paper);
    color:var(--ink);
    line-height:1.5;
  }
  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.001ms !important; animation-iteration-count:1 !important; scroll-behavior:auto !important;}
  }

  a{color:inherit;}
  h1,h2,h3{font-family:var(--serif); margin:0; font-weight:600;}
  p{margin:0;}

  .wrap{max-width:1080px; margin:0 auto; padding:0 28px;}

  /* ---------- NAV ---------- */
  nav{
    position:sticky; top:0; z-index:50;
    background:rgba(13,36,54,0.92);
    backdrop-filter:blur(6px);
    border-bottom:1px solid var(--navy-line);
  }
  nav .wrap{
    display:flex; align-items:center; justify-content:space-between;
    height:64px;
  }
  .brand{
    color:var(--sand);
    font-family:var(--serif);
    font-size:1.05rem;
    letter-spacing:0.01em;
    display:flex; align-items:center; gap:10px;
  }
  .brand svg{flex:none;}
  .navlinks{display:flex; gap:26px; list-style:none; margin:0; padding:0;}
  .navlinks a{
    color:var(--sand); text-decoration:none; font-size:0.92rem; opacity:0.85;
    border-bottom:1px solid transparent; padding-bottom:3px; transition:opacity .2s, border-color .2s;
  }
  .navlinks a:hover, .navlinks a:focus-visible{opacity:1; border-color:var(--coral);}

  /* ---------- HERO ---------- */
  header.hero{
    background:
      radial-gradient(ellipse at 20% 0%, #14405a 0%, transparent 55%),
      linear-gradient(180deg, var(--navy-deep) 0%, #0a1c2b 100%);
    color:var(--sand);
    padding:64px 0 40px;
  }
  .hero-inner{max-width:760px;}
  .kicker{
    color:var(--teal); font-size:0.95rem; margin-bottom:14px; font-weight:500;
  }
  h1.title{
    font-size:clamp(2.1rem, 5vw, 3.4rem);
    line-height:1.08;
    color:var(--paper);
    max-width:15ch;
  }
  h1.title em{
    font-style:italic; color:var(--coral);
  }
  .lede{
    margin-top:20px; font-size:1.08rem; color:#c7d6df; max-width:56ch;
  }
  .hero-ctas{margin-top:30px; display:flex; gap:14px; flex-wrap:wrap;}
  .btn{
    display:inline-block; padding:13px 24px; border-radius:2px; font-size:0.95rem;
    text-decoration:none; cursor:pointer; border:1px solid transparent; font-family:var(--sans); font-weight:500;
  }
  .btn-primary{background:var(--coral); color:#fff;}
  .btn-primary:hover{background:var(--coral-dim);}
  .btn-ghost{background:transparent; color:var(--sand); border-color:#3d5b6f;}
  .btn-ghost:hover{border-color:var(--sand);}

  /* ---------- MAP ---------- */
  .map-panel{
    margin-top:52px;
    border:1px solid var(--navy-line);
    background:linear-gradient(180deg, #0f2c40, #0a2032);
    border-radius:3px;
    padding:22px 22px 14px;
  }
  .map-panel svg{width:100%; height:auto; display:block;}
  .boat{
    offset-path: path("M55,150 C 220,60 460,205 700,90");
    offset-rotate: 0deg;
    animation: sail 9s ease-in-out infinite alternate;
  }
  @keyframes sail{
    0%{offset-distance:0%;}
    100%{offset-distance:100%;}
  }
  .route-line{
    stroke-dasharray:6 8;
    animation:dash 2.4s linear infinite;
  }
  @keyframes dash{ to { stroke-dashoffset:-140; } }

  .facts{
    display:grid; grid-template-columns:repeat(4,1fr); gap:1px;
    background:var(--navy-line); margin-top:0; border-top:1px solid var(--navy-line);
  }
  .fact{background:#0e2a3d; padding:18px 20px;}
  .fact .num{color:var(--sand); font-family:var(--serif); font-size:1.35rem;}
  .fact .lbl{color:#8fa8b6; font-size:0.82rem; margin-top:4px;}
  @media (max-width:720px){ .facts{grid-template-columns:1fr 1fr;} }

  /* ---------- SECTIONS GENERIC ---------- */
  section{padding:74px 0;}
  .section-head{max-width:620px; margin-bottom:40px;}
  .section-head h2{font-size:clamp(1.6rem,3.2vw,2.2rem);}
  .section-head p{margin-top:12px; color:#4b5b63; font-size:1rem;}

  /* ---------- DESTINATIONS ---------- */
  .islands{
    display:grid; grid-template-columns:repeat(4, 1fr); gap:16px;
  }
  @media (max-width:900px){ .islands{grid-template-columns:1fr 1fr;} }
  @media (max-width:520px){ .islands{grid-template-columns:1fr;} }

  .island-card{
    background:var(--navy-deep); color:var(--sand);
    border-radius:2px; overflow:hidden; cursor:pointer;
    border:1px solid var(--navy-deep);
    transition:border-color .2s;
  }
  .island-card:hover, .island-card:focus-visible{border-color:var(--coral);}
  .island-card .img{
    height:120px; display:flex; align-items:center; justify-content:center;
  }
  .island-card .body{padding:16px 18px 20px;}
  .island-card h3{font-size:1.1rem; color:var(--paper);}
  .island-card .tag{color:var(--teal); font-size:0.8rem; margin-top:4px; display:block;}
  .island-card .more{
    max-height:0; overflow:hidden; transition:max-height .35s ease;
    font-size:0.9rem; color:#c7d6df; margin-top:0;
  }
  .island-card.open .more{max-height:200px; margin-top:12px;}
  .island-card .plus{
    float:right; color:var(--coral); font-family:var(--serif); font-size:1.3rem; transition:transform .25s;
  }
  .island-card.open .plus{transform:rotate(45deg);}

  /* ---------- CALCULATOR ---------- */
  .calc{
    display:grid; grid-template-columns:1.15fr 0.85fr; gap:0;
    border:1px solid #ddd3ba; background:#fff;
  }
  @media (max-width:800px){ .calc{grid-template-columns:1fr;} }
  .calc-options{padding:32px;}
  .calc-summary{background:var(--navy-deep); color:var(--sand); padding:32px;}

  .pkg{
    border:1px solid #ddd3ba; padding:16px 18px; margin-bottom:12px; cursor:pointer;
    display:flex; justify-content:space-between; align-items:flex-start; gap:12px;
  }
  .pkg:hover{border-color:var(--coral);}
  .pkg.selected{border-color:var(--coral); background:#fdf5ef;}
  .pkg .pname{font-family:var(--serif); font-size:1.05rem;}
  .pkg .pdesc{font-size:0.85rem; color:#6b6355; margin-top:4px;}
  .pkg .pprice{font-family:var(--serif); font-size:1.15rem; white-space:nowrap;}
  .pkg input{margin-top:4px;}

  .field-row{margin-top:22px;}
  .field-row label{display:block; font-size:0.88rem; color:#4b5b63; margin-bottom:8px;}
  .stepper{display:flex; align-items:center; gap:14px;}
  .stepper button{
    width:34px; height:34px; border:1px solid #ccc0a2; background:#fff; cursor:pointer; font-size:1.1rem; border-radius:2px;
  }
  .stepper button:hover{border-color:var(--coral);}
  .stepper span{min-width:2ch; text-align:center; font-family:var(--serif); font-size:1.15rem;}
  input[type=range]{width:100%; accent-color:var(--coral);}

  .calc-summary h3{color:var(--paper); font-size:1.05rem; font-weight:500; font-family:var(--sans);}
  .summary-line{
    display:flex; justify-content:space-between; padding:10px 0; border-bottom:1px solid var(--navy-line); font-size:0.92rem; color:#c7d6df;
  }
  .summary-total{
    display:flex; justify-content:space-between; padding-top:18px; margin-top:6px; align-items:baseline;
  }
  .summary-total .amt{font-family:var(--serif); font-size:2.1rem; color:var(--paper);}
  .summary-total .per{font-size:0.78rem; color:#8fa8b6;}

  /* ---------- ITINERARY ---------- */
  .tabs{display:flex; flex-wrap:wrap; gap:8px; margin-bottom:24px;}
  .tab-btn{
    padding:9px 16px; border:1px solid #ccc0a2; background:#fff; cursor:pointer; font-size:0.88rem; font-family:var(--sans);
    border-radius:2px; color:var(--ink);
  }
  .tab-btn.active{background:var(--navy-deep); color:var(--sand); border-color:var(--navy-deep);}
  .tab-panel{display:none; border:1px solid #ddd3ba; background:#fff; padding:26px 28px;}
  .tab-panel.active{display:block;}
  .tab-panel h3{font-size:1.2rem;}
  .tab-panel .day-label{color:var(--teal); font-size:0.85rem; margin-bottom:6px; display:block;}
  .tab-panel p{margin-top:12px; color:#4b5b63;}

  /* ---------- BOOKING FORM ---------- */
  .booking{
    background:var(--navy-deep); color:var(--sand); padding:60px 0;
  }
  .booking .section-head p{color:#a9bdc9;}
  .booking .section-head h2{color:var(--paper);}
  form.reserve{
    display:grid; grid-template-columns:1fr 1fr; gap:18px; max-width:680px;
  }
  form.reserve .full{grid-column:1 / -1;}
  @media (max-width:600px){ form.reserve{grid-template-columns:1fr;} }
  form.reserve label{display:block; font-size:0.85rem; margin-bottom:7px; color:#c7d6df;}
  form.reserve input, form.reserve select{
    width:100%; padding:11px 12px; background:#0f2c40; border:1px solid var(--navy-line); color:var(--paper);
    font-family:var(--sans); font-size:0.95rem; border-radius:2px;
  }
  form.reserve input:focus, form.reserve select:focus{outline:2px solid var(--coral); outline-offset:1px;}
  form.reserve button{margin-top:6px;}
  .confirm-box{
    display:none; margin-top:24px; border:1px solid var(--teal); background:#0f2c40; padding:20px 22px; max-width:680px;
  }
  .confirm-box.show{display:block;}
  .confirm-box h4{color:var(--teal); font-family:var(--sans); font-size:0.95rem; margin-bottom:8px;}
  .confirm-box p{color:#c7d6df; font-size:0.9rem;}

  :focus-visible{outline:2px solid var(--coral); outline-offset:2px;}

  footer{
    padding:30px 0; text-align:center; color:#8b8271; font-size:0.82rem; background:var(--paper);
    border-top:1px solid #ddd3ba;
  }
</style>
</head>
<body>

<nav>
  <div class="wrap">
    <div class="brand">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none"><path d="M3 17c1.5 1.5 3 1.5 4.5 0s3-1.5 4.5 0 3 1.5 4.5 0 3-1.5 4.5 0" stroke="#4FA79A" stroke-width="1.6" stroke-linecap="round"/><path d="M6 17V6l10 4-5 2.2" stroke="#E9DEC4" stroke-width="1.6" stroke-linejoin="round" stroke-linecap="round"/></svg>
      Rota Atlântica <span style="opacity:0.6; font-weight:400; font-size:0.8rem;">(trabalho de Geografia)</span>
    </div>
    <ul class="navlinks">
      <li><a href="#destinos">Destinos</a></li>
      <li><a href="#pacotes">Pacotes</a></li>
      <li><a href="#roteiro">Roteiro</a></li>
      <li><a href="#reserva">Reserva</a></li>
    </ul>
  </div>
</nav>

<header class="hero">
  <div class="wrap">
    <div class="hero-inner">
      <div class="kicker">Trabalho de Geografia · Rio Grande, RS → Cabo Verde</div>
      <h1 class="title">Uma travessia pelo Atlântico até <em>Cabo Verde</em></h1>
      <p class="lede">Do porto de Rio Grande, no extremo sul do Brasil, até as dez ilhas vulcânicas cabo-verdianas: um roteiro que atravessa o mesmo oceano que ligou historicamente as duas margens de língua portuguesa.</p>
      <div class="hero-ctas">
        <a href="#pacotes" class="btn btn-primary">Bora? Clarinho que sim!</a>
        <a href="#roteiro" class="btn btn-ghost">Ver roteiro</a>
      </div>
    </div>

    <div class="map-panel">
      <svg viewBox="0 0 760 220" xmlns="http://www.w3.org/2000/svg" aria-label="Mapa esquemático da rota entre Rio Grande e Cabo Verde">
        <!-- ocean texture lines -->
        <g stroke="#1c4258" stroke-width="1" opacity="0.5">
          <line x1="0" y1="40" x2="760" y2="40"/>
          <line x1="0" y1="180" x2="760" y2="180"/>
        </g>
        <!-- Brazil coast blob -->
        <path d="M0,220 L0,150 C 20,130 40,160 60,140 C 80,120 70,90 95,95 L 110,220 Z" fill="#173a52"/>
        <text x="18" y="205" fill="#E9DEC4" font-family="Inter, sans-serif" font-size="12">Rio Grande, RS</text>
        <circle cx="55" cy="150" r="4.5" fill="#E2622E"/>

        <!-- Cabo Verde archipelago -->
        <g fill="#173a52">
          <circle cx="700" cy="88" r="9"/>
          <circle cx="722" cy="70" r="6"/>
          <circle cx="688" cy="65" r="5"/>
          <circle cx="712" cy="105" r="6"/>
          <circle cx="735" cy="95" r="4.5"/>
        </g>
        <circle cx="700" cy="90" r="4.5" fill="#E2622E"/>
        <text x="640" y="130" fill="#E9DEC4" font-family="Inter, sans-serif" font-size="12">Cabo Verde</text>

        <!-- route -->
        <path class="route-line" d="M55,150 C 220,60 460,205 700,90" fill="none" stroke="#4FA79A" stroke-width="1.6"/>

        <!-- boat -->
        <g class="boat">
          <path d="M-7,4 L7,4 L4,9 L-4,9 Z M0,-9 L0,4 M0,-6 L5,-2 L0,0 Z" fill="none" stroke="#E9DEC4" stroke-width="1.4" stroke-linejoin="round" stroke-linecap="round"/>
        </g>
      </svg>
    </div>

    <div class="facts">
      <div class="fact"><div class="num">≈ 6.500 km</div><div class="lbl">distância em linha reta pelo Atlântico</div></div>
      <div class="fact"><div class="num">+2h</div><div class="lbl">fuso horário à frente de Rio Grande</div></div>
      <div class="fact"><div class="num">Português<br>e Crioulo</div><div class="lbl">idiomas falados no arquipélago</div></div>
      <div class="fact"><div class="num">Nov–Jun</div><div class="lbl">temporada seca, melhor época</div></div>
    </div>
  </div>
</header>

<section id="destinos">
  <div class="wrap">
    <div class="section-head">
      <h2>Quatro ilhas, quatro paisagens</h2>
      <p>Cabo Verde tem dez ilhas vulcânicas divididas em dois grupos, Barlavento e Sotavento. Estas quatro entram no roteiro.</p>
    </div>
    <div class="islands">

      <div class="island-card" tabindex="0" role="button" aria-expanded="false">
        <div class="img">
          <svg width="60" height="60" viewBox="0 0 60 60"><circle cx="30" cy="30" r="26" fill="none" stroke="#4FA79A" stroke-width="1.5"/><path d="M12 34 Q30 20 48 34" stroke="#E9DEC4" stroke-width="1.5" fill="none"/></svg>
        </div>
        <div class="body">
          <span class="plus">+</span>
          <h3>Ilha do Sal</h3>
          <span class="tag">Praias e dunas</span>
          <div class="more">Portão de entrada aérea do arquipélago. Praia de Santa Maria, águas claras e ventos constantes que atraem praticantes de windsurf e kitesurf.</div>
        </div>
      </div>

      <div class="island-card" tabindex="0" role="button" aria-expanded="false">
        <div class="img">
          <svg width="60" height="60" viewBox="0 0 60 60"><path d="M30 8 L44 46 L16 46 Z" fill="none" stroke="#E2622E" stroke-width="1.5"/><path d="M25 25 L34 25" stroke="#E9DEC4" stroke-width="1.5"/></svg>
        </div>
        <div class="body">
          <span class="plus">+</span>
          <h3>Fogo</h3>
          <span class="tag">Vulcão ativo</span>
          <div class="more">Abriga o Pico do Fogo, o ponto mais alto do país. Um vilarejo agrícola vive dentro da própria caldeira, produzindo café e vinho vulcânico.</div>
        </div>
      </div>

      <div class="island-card" tabindex="0" role="button" aria-expanded="false">
        <div class="img">
          <svg width="60" height="60" viewBox="0 0 60 60"><path d="M8 40 L20 18 L32 34 L44 12 L52 40" fill="none" stroke="#4FA79A" stroke-width="1.5" stroke-linejoin="round"/></svg>
        </div>
        <div class="body">
          <span class="plus">+</span>
          <h3>Santo Antão</h3>
          <span class="tag">Trilhas de montanha</span>
          <div class="more">Vales profundos e verdes cortados por trilhas coloniais em pedra. Destino preferido de quem busca caminhadas e paisagens dramáticas.</div>
        </div>
      </div>

      <div class="island-card" tabindex="0" role="button" aria-expanded="false">
        <div class="img">
          <svg width="60" height="60" viewBox="0 0 60 60"><circle cx="22" cy="30" r="3" fill="#E9DEC4"/><circle cx="32" cy="24" r="3" fill="#E9DEC4"/><circle cx="40" cy="34" r="3" fill="#E9DEC4"/><path d="M15 42 Q30 30 45 42" stroke="#4FA79A" stroke-width="1.5" fill="none"/></svg>
        </div>
        <div class="body">
          <span class="plus">+</span>
          <h3>São Vicente (Mindelo)</h3>
          <span class="tag">Música e cultura</span>
          <div class="more">Cidade natal de Cesária Évora e berço da morna, gênero musical reconhecido pela Unesco. Casario colorido e um dos maiores carnavais do país.</div>
        </div>
      </div>

    </div>
  </div>
</section>

<section id="pacotes" style="background:#fff; border-top:1px solid #ddd3ba; border-bottom:1px solid #ddd3ba;">
  <div class="wrap">
    <div class="section-head">
      <h2>Monte seu pacote</h2>
      <p>Escolha a categoria, o número de viajantes e ajuste as noites extras. O valor total é recalculado na hora.</p>
    </div>

    <div class="calc">
      <div class="calc-options">

        <div class="pkg selected" data-pkg="padrao" role="radio" aria-checked="true" tabindex="0">
          <div>
            <div class="pname">Padrão</div>
            <div class="pdesc">7 noites · hotel 3 estrelas · café da manhã incluso</div>
          </div>
          <div class="pprice">R$ 8.900</div>
        </div>

        <div class="pkg" data-pkg="conforto" role="radio" aria-checked="false" tabindex="0">
          <div>
            <div class="pname">Conforto</div>
            <div class="pdesc">7 noites · hotel 4 estrelas · meia pensão · passeio ao vulcão do Fogo</div>
          </div>
          <div class="pprice">R$ 12.500</div>
        </div>

        <div class="pkg" data-pkg="premium" role="radio" aria-checked="false" tabindex="0">
          <div>
            <div class="pname">Premium</div>
            <div class="pdesc">10 noites · hotel 5 estrelas · all inclusive · passeios em 3 ilhas</div>
          </div>
          <div class="pprice">R$ 17.900</div>
        </div>

        <div class="field-row">
          <label for="travelers">Número de viajantes</label>
          <div class="stepper">
            <button type="button" id="minus-t" aria-label="Diminuir viajantes">−</button>
            <span id="travelers-val">2</span>
            <button type="button" id="plus-t" aria-label="Aumentar viajantes">+</button>
          </div>
        </div>

        <div class="field-row">
          <label for="extranights">Noites extras: <span id="nights-val">0</span></label>
          <input type="range" id="extranights" min="0" max="6" value="0">
        </div>
      </div>

      <div class="calc-summary">
        <h3 id="summary-pkgname">Pacote Padrão</h3>
        <div class="summary-line"><span>Valor base por pessoa</span><span id="sum-base">R$ 8.900</span></div>
        <div class="summary-line"><span>Noites extras</span><span id="sum-extra">R$ 0</span></div>
        <div class="summary-line"><span>Viajantes</span><span id="sum-travelers">2</span></div>
        <div class="summary-total">
          <div>
            <div class="per">total estimado</div>
            <div class="amt" id="sum-total">R$ 17.800</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="roteiro">
  <div class="wrap">
    <div class="section-head">
      <h2>Roteiro sugerido — 7 dias</h2>
      <p>Base do pacote Padrão. Nos pacotes Conforto e Premium, o roteiro se estende para mais ilhas.</p>
    </div>

    <div class="tabs" role="tablist">
      <button class="tab-btn active" data-tab="1">Dia 1</button>
      <button class="tab-btn" data-tab="2">Dia 2</button>
      <button class="tab-btn" data-tab="3">Dia 3</button>
      <button class="tab-btn" data-tab="4">Dia 4</button>
      <button class="tab-btn" data-tab="5">Dia 5</button>
      <button class="tab-btn" data-tab="6">Dia 6</button>
      <button class="tab-btn" data-tab="7">Dia 7</button>
    </div>

    <div class="tab-panel active" data-panel="1">
      <span class="day-label">Chegada</span>
      <h3>Rio Grande → Ilha do Sal</h3>
      <p
