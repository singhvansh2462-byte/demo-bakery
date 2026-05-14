<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Petal & Crumb Bakery — Premium Bakes</title>
  <meta name="description" content="A premium pastel bakery experience: cakes, biscuits, pastries, and breads — crafted with love." />

  <style>
    :root{
      --cream:#FFF6E8;
      --pink:#FFD6E6;
      --sky:#CFEFFF;
      --ink:#1f2a37;
      --muted:#4b5a6a;

      --card:#ffffffcc;
      --stroke:rgba(31,42,55,.12);
      --shadow: 0 18px 50px rgba(25, 40, 60, .10);
      --shadow-soft: 0 10px 25px rgba(25, 40, 60, .10);

      --glow-cyan: rgba(120, 225, 255, .55);
      --glow-pink: rgba(255, 142, 199, .55);

      --radius-xl: 28px;
      --radius-lg: 20px;
      --radius-md: 14px;
      --radius-sm: 12px;

      --max: 1120px;

      --font: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
    }

    *{ box-sizing:border-box; }
    html, body{ height:100%; }
    body{
      margin:0;
      font-family:var(--font);
      color:var(--ink);
      background:
        radial-gradient(1000px 600px at 10% -10%, rgba(207,239,255,.75), transparent 55%),
        radial-gradient(900px 520px at 80% 0%, rgba(255,214,230,.65), transparent 52%),
        linear-gradient(180deg, var(--cream), #ffffff 65%);
      overflow-x:hidden;
    }

    a{ color:inherit; text-decoration:none; }

    .container{
      width: min(var(--max), calc(100% - 40px));
      margin: 0 auto;
    }

    .top-sheen{
      position:fixed;
      inset:-40% -20% auto -20%;
      height: 60vh;
      background:
        radial-gradient(closest-side, rgba(255,214,230,.18), transparent 65%),
        radial-gradient(closest-side, rgba(207,239,255,.18), transparent 62%);
      pointer-events:none;
      z-index:0;
      filter: blur(10px);
      opacity:.9;
    }

    header{
      position:sticky;
      top:0;
      z-index:50;
      backdrop-filter: blur(10px);
      background: linear-gradient(180deg, rgba(255,246,232,.78), rgba(255,246,232,.40));
      border-bottom: 1px solid rgba(31,42,55,.08);
    }

    .nav{
      display:flex;
      align-items:center;
      justify-content:space-between;
      padding: 14px 0;
      gap:14px;
    }

    .brand{
      display:flex;
      align-items:center;
      gap:12px;
      min-width: 220px;
    }

    .logo{
      width: 40px;
      height: 40px;
      border-radius: 14px;
      background:
        radial-gradient(circle at 30% 25%, #fff, transparent 45%),
        linear-gradient(135deg, rgba(120,225,255,.65), rgba(255,142,199,.62));
      box-shadow:
        0 10px 30px rgba(120,225,255,.18),
        0 12px 35px rgba(255,142,199,.16);
      border: 1px solid rgba(255,255,255,.65);
      position:relative;
    }
    .logo:after{
      content:"";
      position:absolute;
      inset:10px;
      border-radius: 10px;
      border: 1px dashed rgba(31,42,55,.18);
      transform: rotate(8deg);
      opacity:.55;
    }

    .brand h1{
      margin:0;
      font-size: 14px;
      font-weight: 780;
      letter-spacing:.2px;
      line-height:1.2;
    }
    .brand p{
      margin:0;
      font-size: 12px;
      color: var(--muted);
    }

    nav ul{
      margin:0;
      padding:0;
      list-style:none;
      display:flex;
      gap: 18px;
      align-items:center;
      flex-wrap:wrap;
      justify-content:flex-end;
    }

    nav a{
      font-size: 13px;
      color: rgba(31,42,55,.86);
      padding: 8px 10px;
      border-radius: 999px;
      transition: background .25s ease, transform .25s ease;
      border: 1px solid transparent;
    }

    nav a:hover{
      background: rgba(255,255,255,.58);
      border-color: rgba(31,42,55,.10);
      transform: translateY(-1px);
    }

    .cta{
      display:flex;
      align-items:center;
      gap:10px;
    }

    .btn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap:10px;
      padding: 12px 16px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,.55);
      background:
        radial-gradient(120% 140% at 0% 0%, rgba(255,255,255,.85), rgba(255,255,255,.35) 45%, rgba(255,255,255,.15) 75%),
        linear-gradient(135deg, rgba(120,225,255,.62), rgba(255,142,199,.58));
      color: #08212c;
      font-weight: 750;
      letter-spacing:.2px;
      box-shadow:
        0 12px 35px rgba(120,225,255,.18),
        0 16px 44px rgba(255,142,199,.14);
      transition: transform .2s ease, box-shadow .2s ease, filter .2s ease;
      user-select:none;
      cursor:pointer;
    }

    .btn:hover{
      transform: translateY(-2px);
      filter:saturate(1.05);
      box-shadow:
        0 16px 45px rgba(120,225,255,.24),
        0 22px 55px rgba(255,142,199,.18);
    }

    .btn:active{ transform: translateY(-1px); }

    .btn-secondary{
      background: rgba(255,255,255,.55);
      border: 1px solid rgba(31,42,55,.10);
      box-shadow: 0 10px 25px rgba(25,40,60,.08);
      color: rgba(31,42,55,.92);
    }

    .pill{
      display:inline-flex;
      align-items:center;
      gap:10px;
      padding: 8px 12px;
      border-radius:999px;
      background: rgba(255,255,255,.55);
      border: 1px solid rgba(31,42,55,.10);
      box-shadow: 0 10px 24px rgba(25,40,60,.06);
      font-size: 13px;
      color: rgba(31,42,55,.86);
      width: fit-content;
      transform: translateZ(0);
    }

    .dot{
      width:10px;
      height:10px;
      border-radius:50%;
      background: linear-gradient(135deg, rgba(120,225,255,.9), rgba(255,142,199,.9));
      box-shadow: 0 0 0 6px rgba(120,225,255,.14);
    }

    section{
      position:relative;
      z-index:1;
      padding: 86px 0;
    }

    .hero{
      padding-top: 58px;
    }

    .hero-grid{
      display:grid;
      grid-template-columns: 1.1fr .9fr;
      gap: 26px;
      align-items:center;
    }

    @media (max-width: 900px){
      .hero-grid{ grid-template-columns: 1fr; }
      .brand{ min-width:auto; }
    }

    .h-hero{
      margin: 16px 0 10px;
      font-size: clamp(34px, 4.2vw, 56px);
      letter-spacing: -0.8px;
      line-height:1.02;
    }

    .grad-text{
      background: linear-gradient(90deg, rgba(120,225,255,.95), rgba(255,142,199,.95), rgba(120,225,255,.85));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      text-shadow: 0 10px 35px rgba(120,225,255,.10);
    }

    .subhead{
      margin: 0;
      font-size: 16px;
      color: rgba(31,42,55,.80);
      line-height:1.65;
      max-width: 56ch;
    }

    .hero-actions{
      display:flex;
      gap: 12px;
      align-items:center;
      flex-wrap:wrap;
      margin-top: 22px;
    }

    .hero-stats{
      display:grid;
      grid-template-columns: repeat(3, minmax(0,1fr));
      gap: 12px;
      margin-top: 22px;
    }

    @media (max-width: 520px){
      .hero-stats{ grid-template-columns: 1fr; }
    }

    .stat{
      padding: 14px 14px;
      border-radius: 18px;
      background: rgba(255,255,255,.52);
      border: 1px solid rgba(31,42,55,.10);
      box-shadow: 0 14px 35px rgba(25,40,60,.08);
      transform: translateZ(0);
    }
    .stat b{ display:block; font-size: 16px; letter-spacing:.2px; }
    .stat span{ display:block; margin-top: 6px; font-size: 12.5px; color: rgba(31,42,55,.72); line-height:1.3; }

    /* Hero cake 3D */
    .cake-wrap{
      position:relative;
      height: 420px;
      border-radius: var(--radius-xl);
      background:
        radial-gradient(120% 90% at 30% 18%, rgba(255,214,230,.55), transparent 55%),
        radial-gradient(120% 90% at 80% 0%, rgba(207,239,255,.60), transparent 48%),
        linear-gradient(180deg, rgba(255,255,255,.55), rgba(255,255,255,.20));
      border: 1px solid rgba(31,42,55,.10);
      box-shadow: var(--shadow-soft);
      overflow:hidden;
      display:flex;
      align-items:center;
      justify-content:center;
      transform: translateZ(0);
    }

    .cake-ornaments{
      position:absolute;
      inset:-30px;
      pointer-events:none;
    }
    .cake-ornaments:before,
    .cake-ornaments:after{
      content:"";
      position:absolute;
      width: 210px;
      height: 210px;
      border-radius: 50%;
      filter: blur(1px);
      opacity:.7;
      transform: translateZ(0);
    }
    .cake-ornaments:before{
      left:-50px;
      top:-60px;
      background: radial-gradient(circle at 30% 30%, rgba(255,214,230,.75), transparent 60%);
      animation: drift1 9s ease-in-out infinite;
    }
    .cake-ornaments:after{
      right:-60px;
      bottom:-60px;
      background: radial-gradient(circle at 40% 40%, rgba(207,239,255,.75), transparent 58%);
      animation: drift2 11s ease-in-out infinite;
    }

    @keyframes drift1{ 0%,100%{ transform: translate(0,0); } 50%{ transform: translate(22px, 18px);} }
    @keyframes drift2{ 0%,100%{ transform: translate(0,0); } 50%{ transform: translate(-18px, -22px);} }

    .cake-scene{
      position:relative;
      width: 280px;
      height: 330px;
      perspective: 900px;
      transform-style: preserve-3d;
    }

    .cake{
      position:absolute;
      left:50%;
      top: 52%;
      transform: translate(-50%, -50%) rotateX(var(--rx, -10deg)) rotateY(var(--ry, 12deg));
      transform-style: preserve-3d;
      animation: cakeFloat 6s ease-in-out infinite;
    }

    @keyframes cakeFloat{
      0%,100%{ transform: translate(-50%, -50%) rotateX(-10deg) rotateY(12deg) translateY(0px); }
      50%{ transform: translate(-50%, -50%) rotateX(-8deg) rotateY(7deg) translateY(-10px); }
    }

    .tier{
      position:absolute;
      left:50%;
      transform: translateX(-50%);
      border-radius: 999px;
      transform-style: preserve-3d;
      box-shadow:
        0 30px 60px rgba(18, 33, 50, .12);
      border: 1px solid rgba(255,255,255,.65);
      overflow:hidden;
    }

    .tier.top{
      width: 120px;
      height: 64px;
      top: 56px;
      background:
        linear-gradient(180deg, rgba(255,255,255,.80), rgba(255,214,230,.75) 55%, rgba(255,142,199,.35));
    }
    .tier.mid{
      width: 168px;
      height: 82px;
      top: 122px;
      background:
        linear-gradient(180deg, rgba(255,255,255,.86), rgba(207,239,255,.86) 55%, rgba(120,225,255,.30));
    }
    .tier.base{
      width: 218px;
      height: 100px;
      top: 206px;
      background:
        linear-gradient(180deg, rgba(255,255,255,.86), rgba(255,246,232,.96) 50%, rgba(255,214,230,.40));
    }

    .tier:before{
      content:"";
      position:absolute;
      inset:-18px;
      background:
        radial-gradient(circle at 22% 18%, rgba(255,255,255,.85), transparent 36%),
        radial-gradient(circle at 78% 30%, rgba(255,255,255,.55), transparent 45%),
        radial-gradient(circle at 50% 90%, rgba(0,0,0,.07), transparent 55%);
      opacity:.9;
      transform: translateZ(25px);
    }

    .icing{
      position:absolute;
      left:50%;
      top: 46px;
      width: 132px;
      height: 44px;
      transform: translateX(-50%) translateZ(35px);
      border-radius: 999px;
      background:
        radial-gradient(circle at 30% 25%, rgba(255,255,255,.95), rgba(255,214,230,.85) 45%, rgba(255,142,199,.25) 78%);
      box-shadow:
        0 20px 40px rgba(255,142,199,.18),
        0 10px 25px rgba(120,225,255,.12);
      border: 1px solid rgba(255,255,255,.75);
    }

    .icing:after{
      content:"";
      position:absolute;
      left:50%;
      top: 26px;
      width: 160px;
      height: 30px;
      transform: translateX(-50%);
      background:
        repeating-linear-gradient(90deg, rgba(255,142,199,.0) 0 10px, rgba(255,142,199,.18) 10px 12px);
      border-radius: 999px;
      opacity:.7;
      filter: blur(.2px);
    }

    .sparkle-canvas{
      position:absolute;
      inset: 0;
      pointer-events:none;
      opacity:.95;
    }

    .cake-shadow{
      position:absolute;
      left:50%;
      top: 78%;
      width: 240px;
      height: 60px;
      transform: translateX(-50%) translateZ(-40px);
      background: radial-gradient(circle, rgba(31,42,55,.18), transparent 65%);
      filter: blur(2px);
      opacity:.28;
    }

    /* Sections */
    .section-head{
      display:flex;
      align-items:flex-end;
      justify-content:space-between;
      gap: 14px;
      margin-bottom: 22px;
    }

    .kicker{
      font-size: 13px;
      color: rgba(31,42,55,.72);
      letter-spacing: .28px;
      text-transform: uppercase;
      margin: 0 0 8px;
    }

    .h2{
      margin:0;
      font-size: clamp(24px, 2.6vw, 36px);
      letter-spacing: -0.4px;
    }

    .section-sub{
      margin: 8px 0 0;
      color: rgba(31,42,55,.78);
      line-height: 1.7;
      max-width: 70ch;
      font-size: 15px;
    }

    .grid{
      display:grid;
      gap: 14px;
    }

    .grid.menu{
      grid-template-columns: repeat(4, minmax(0,1fr));
    }

    @media (max-width: 1050px){
      .grid.menu{ grid-template-columns: repeat(2, minmax(0,1fr)); }
    }
    @media (max-width: 560px){
      .grid.menu{ grid-template-columns: 1fr; }
    }

    .card{
      border-radius: var(--radius-lg);
      background: rgba(255,255,255,.55);
      border: 1px solid rgba(31,42,55,.10);
      box-shadow: 0 16px 40px rgba(25,40,60,.08);
      overflow:hidden;
      position:relative;
      transform: translateZ(0);
    }

    .menu-cat{
      padding: 16px;
      display:flex;
      flex-direction:column;
      gap: 10px;
    }

    .menu-cat h3{
      margin: 0;
      font-size: 16px;
      letter-spacing:.1px;
    }

    .menu-cat .cat-grad{
      background: linear-gradient(90deg, rgba(120,225,255,.85), rgba(255,142,199,.85));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      font-weight: 820;
    }

    .price-list{
      display:flex;
      flex-direction:column;
      gap: 10px;
      margin-top: 2px;
    }

    .price-item{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
      padding: 12px 12px;
      border-radius: 16px;
      border: 1px solid rgba(31,42,55,.08);
      background: rgba(255,255,255,.62);
      transition: transform .2s ease, box-shadow .2s ease, border-color .2s ease;
      position:relative;
      overflow:hidden;
    }

    .price-item:before{
      content:"";
      position:absolute;
      inset:-2px;
      background:
        radial-gradient(240px 120px at 30% 0%, rgba(120,225,255,.25), transparent 58%),
        radial-gradient(240px 120px at 70% 0%, rgba(255,142,199,.22), transparent 58%);
      opacity:0;
      transition: opacity .2s ease;
    }

    .price-item:hover{
      transform: translateY(-3px);
      border-color: rgba(31,42,55,.14);
      box-shadow: 0 18px 45px rgba(120,225,255,.13), 0 18px 45px rgba(255,142,199,.10);
    }
    .price-item:hover:before{ opacity:1; }

    .price-item b,
    .price-item span{ position:relative; z-index:1; }

    .price-item b{
      font-size: 13.5px;
      letter-spacing: .15px;
    }

    .price-item span{
      font-weight: 900;
      font-size: 13.5px;
      color: rgba(31,42,55,.85);
    }

    /* About */
    .about-grid{
      display:grid;
      grid-template-columns: 1.1fr .9fr;
      gap: 18px;
      align-items:center;
    }
    @media (max-width: 900px){ .about-grid{ grid-template-columns: 1fr; } }

    .about-card{
      padding: 18px;
    }

    .about-text{
      font-size: 15px;
      color: rgba(31,42,55,.80);
      line-height: 1.8;
      margin: 10px 0 0;
    }

    .photo-frame{
      padding: 10px;
      background:
        linear-gradient(180deg, rgba(255,255,255,.65), rgba(255,255,255,.25));
      border-radius: var(--radius-xl);
      border: 1px solid rgba(31,42,55,.10);
      box-shadow: var(--shadow-soft);
      overflow:hidden;
      transform: translateZ(0);
    }

    .photo-frame img{
      width:100%;
      height: 360px;
      object-fit: cover;
      border-radius: 22px;
      border: 1px solid rgba(255,255,255,.5);
      filter: saturate(1.02);
      transform: scale(1.01);
      transition: transform .35s ease;
    }

    .photo-frame:hover img{ transform: scale(1.06); }

    /* Gallery */
    .gallery-grid{
      grid-template-columns: repeat(12, minmax(0, 1fr));
    }

    .g-item{ grid-column: span 4; }
    @media (max-width: 950px){ .g-item{ grid-column: span 6; } }
    @media (max-width: 580px){ .g-item{ grid-column: span 12; } }

    .g-tile{
      padding: 10px;
    }

    .img-frame{
      border-radius: 22px;
      overflow:hidden;
      border: 1px solid rgba(31,42,55,.10);
      background: rgba(255,255,255,.55);
      position:relative;
      transition: transform .25s ease, box-shadow .25s ease, border-color .25s ease;
      transform-style: preserve-3d;
    }

    .img-frame img{
      width:100%;
      height: 220px;
      object-fit: cover;
      display:block;
      transform: translateZ(0);
      filter: saturate(1.02);
      transition: transform .5s ease;
    }

    .img-frame .cap{
      position:absolute;
      left: 14px;
      right: 14px;
      bottom: 14px;
      padding: 10px 12px;
      border-radius: 16px;
      background: rgba(255,255,255,.65);
      border: 1px solid rgba(31,42,55,.10);
      box-shadow: 0 14px 35px rgba(25,40,60,.08);
      opacity:0;
      transform: translateY(8px);
      transition: opacity .25s ease, transform .25s ease;
    }

    .img-frame:hover{
      border-color: rgba(31,42,55,.16);
      box-shadow: 0 20px 55px rgba(120,225,255,.14), 0 20px 55px rgba(255,142,199,.10);
      transform: translateY(-4px);
    }
    .img-frame:hover img{ transform: scale(1.06); }
    .img-frame:hover .cap{ opacity:1; transform: translateY(0); }

    .cap b{
      display:block;
      font-size: 13.5px;
    }
    .cap span{
      display:block;
      margin-top: 4px;
      font-size: 12.5px;
      color: rgba(31,42,55,.72);
    }

    /* Contact */
    .contact-grid{
      grid-template-columns: 1fr 1fr;
      align-items: stretch;
    }
    @media (max-width: 900px){ .contact-grid{ grid-template-columns: 1fr; } }

    .contact-card{ padding: 18px; }

    .contact-row{
      display:flex;
      gap:12px;
      align-items:flex-start;
      padding: 12px;
      border-radius: 18px;
      border: 1px solid rgba(31,42,55,.10);
      background: rgba(255,255,255,.58);
      margin-top: 12px;
      transition: transform .2s ease, box-shadow .2s ease;
    }

    .contact-row:hover{
      transform: translateY(-3px);
      box-shadow: 0 18px 45px rgba(120,225,255,.12), 0 18px 45px rgba(255,142,199,.09);
    }

    .ico{
      width: 42px;
      height: 42px;
      border-radius: 16px;
      background:
        radial-gradient(circle at 30% 25%, rgba(255,255,255,.85), transparent 50%),
        linear-gradient(135deg, rgba(120,225,255,.60), rgba(255,142,199,.56));
      border: 1px solid rgba(255,255,255,.55);
      display:flex;
      align-items:center;
      justify-content:center;
      box-shadow: 0 12px 30px rgba(120,225,255,.14);
      flex:0 0 auto;
    }

    .contact-row b{ display:block; font-size: 13.5px; margin-bottom: 5px; }
    .contact-row p{ margin:0; font-size: 14px; color: rgba(31,42,55,.78); line-height:1.5; }

    .copy-btn{
      margin-left:auto;
      padding: 10px 12px;
      border-radius: 14px;
      border: 1px solid rgba(31,42,55,.10);
      background: rgba(255,255,255,.6);
      cursor:pointer;
      font-weight: 750;
      font-size: 13px;
      transition: transform .2s ease, box-shadow .2s ease;
    }

    .copy-btn:hover{ transform: translateY(-2px); box-shadow: 0 16px 40px rgba(25,40,60,.10); }

    .map-frame{
      padding: 10px;
    }

    iframe{
      width:100%;
      height: 370px;
      border:0;
      border-radius: 22px;
      overflow:hidden;
      filter: saturate(1.02);
    }

    /* Footer */
    footer{
      padding: 34px 0 46px;
      border-top: 1px solid rgba(31,42,55,.08);
      background: linear-gradient(180deg, rgba(255,255,255,.0), rgba(255,255,255,.45));
    }

    .footer-row{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap: 14px;
      flex-wrap:wrap;
    }

    .footer-row small{
      color: rgba(31,42,55,.70);
      font-size: 13px;
    }

    .social{
      display:flex;
      gap: 10px;
      align-items:center;
    }

    .social a{
      width: 42px;
      height: 42px;
      border-radius: 16px;
      display:inline-flex;
      align-items:center;
      justify-content:center;
      border: 1px solid rgba(31,42,55,.10);
      background: rgba(255,255,255,.55);
      box-shadow: 0 14px 35px rgba(25,40,60,.07);
      transition: transform .2s ease, box-shadow .2s ease;
    }

    .social a:hover{
      transform: translateY(-3px);
      box-shadow: 0 18px 50px rgba(120,225,255,.14), 0 18px 50px rgba(255,142,199,.10);
    }

    /* Utilities */
    .muted{ color: rgba(31,42,55,.72); }

    /* Parallax */
    [data-parallax]{ will-change: transform; }

    /* Reduce motion */
    @media (prefers-reduced-motion: reduce){
      *{ scroll-behavior: auto !important; }
      .cake{ animation: none !important; }
      .price-item, .img-frame, nav a, .photo-frame img { transition: none !important; }
    }

    html{ scroll-behavior:smooth; }
  </style>
</head>
<body>
  <div class="top-sheen" aria-hidden="true"></div>

  <header>
    <div class="container nav">
      <a class="brand" href="#top" aria-label="Petal & Crumb Bakery Home">
        <div class="logo" aria-hidden="true"></div>
        <div>
          <h1>Petal &amp; Crumb</h1>
          <p>Premium bakery • Light &amp; airy</p>
        </div>
      </a>

      <nav aria-label="Primary">
        <ul>
          <li><a href="#menu">Menu</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#gallery">Gallery</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>

      <div class="cta">
        <a class="btn" href="#contact" role="button">Order a Box <span aria-hidden="true">→</span></a>
      </div>
    </div>
  </header>

  <main id="top">
    <!-- HERO -->
    <section class="hero" aria-label="Hero">
      <div class="container hero-grid">
        <div>
          <div class="pill" data-parallax="0.12">
            <span class="dot" aria-hidden="true"></span>
            <span>Small-batch • pastel perfection • baked fresh daily</span>
          </div>

          <h2 class="h-hero">
            <span class="grad-text">Premium</span> cakes &amp; pastries, crafted for moments you’ll remember.
          </h2>

          <p class="subhead">
            Soft creams, delicate textures, and elegant flavors—curated in a light theme designed to feel as airy as our bakes.
          </p>

          <div class="hero-actions">
            <a class="btn" href="#menu">Explore Menu</a>
            <a class="btn btn-secondary" href="#gallery">View Gallery</a>
          </div>

          <div class="hero-stats" aria-label="Highlights">
            <div class="stat" data-parallax="0.08">
              <b>Seasonal Specials</b>
              <span>Pastel flavors that change with the week.</span>
            </div>
            <div class="stat" data-parallax="0.10">
              <b>Hand-Finished</b>
              <span>Each cake is topped with love and precision.</span>
            </div>
            <div class="stat" data-parallax="0.06">
              <b>Gift-Ready</b>
              <span>Clean packaging with a soft glow feel.</span>
            </div>
          </div>
        </div>

        <div class="cake-wrap" data-parallax="0.18">
          <div class="cake-ornaments" aria-hidden="true"></div>

          <div class="cake-scene" aria-hidden="true">
            <canvas class="sparkle-canvas" id="sparkles" width="560" height="560"></canvas>
            <div class="cake-shadow"></div>
            <div class="cake" id="cake">
              <div class="tier base"></div>
              <div class="tier mid"></div>
              <div class="tier top"></div>
              <div class="icing"></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- MENU -->
    <section id="menu" aria-label="Menu">
      <div class="container">
        <div class="section-head">
          <div>
            <p class="kicker">Menu</p>
            <h3 class="h2"><span class="grad-text">Bakes</span> made for sweet cravings</h3>
            <p class="section-sub">Clean price cards with a pastel glow—hover to feel the highlight.</p>
          </div>
        </div>

        <div class="grid menu">
          <article class="card menu-cat" data-parallax="0.06">
            <h3><span class="cat-grad">Cakes</span></h3>
            <div class="price-list" role="list">
              <div class="price-item" role="listitem"><b>Vanilla Cloud Cake</b><span>$34</span></div>
              <div class="price-item" role="listitem"><b>Strawberry Petal Cake</b><span>$38</span></div>
              <div class="price-item" role="listitem"><b>Sky Cream Cheesecake</b><span>$42</span></div>
            </div>
          </article>

          <article class="card menu-cat" data-parallax="0.06">
            <h3><span class="cat-grad">Biscuits</span></h3>
            <div class="price-list" role="list">
              <div class="price-item" role="listitem"><b>Butter Blossom Biscuits</b><span>$14</span></div>
              <div class="price-item" role="listitem"><b>Pink Sugar Shortbread</b><span>$16</span></div>
              <div class="price-item" role="listitem"><b>Blueberry Breeze Rounds</b><span>$18</span></div>
            </div>
          </article>

          <article class="card menu-cat" data-parallax="0.06">
            <h3><span class="cat-grad">Pastries</span></h3>
            <div class="price-list" role="list">
              <div class="price-item" role="listitem"><b>Cream Puff Royale</b><span>$22</span></div>
              <div class="price-item" role="listitem"><b>Peach Satin Danish</b><span>$26</span></div>
              <div class="price-item" role="listitem"><b>Chocolate Halo Croissant</b><span>$28</span></div>
            </div>
          </article>

          <article class="card menu-cat" data-parallax="0.06">
            <h3><span class="cat-grad">Breads</span></h3>
            <div class="price-list" role="list">
              <div class="price-item" role="listitem"><b>Honey Oat Loaf</b><span>$20</span></div>
              <div class="price-item" role="listitem"><b>Butter Brioche Braid</b><span>$24</span></div>
              <div class="price-item" role="listitem"><b>Garden Seed Ciabatta</b><span>$21</span></div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <!-- ABOUT -->
    <section id="about" aria-label="About Us">
      <div class="container">
        <div class="section-head">
          <div>
            <p class="kicker">About Us</p>
            <h3 class="h2"><span class="grad-text">Warm</span> and welcoming from the first bite</h3>
            <p class="section-sub">We believe premium bakes should feel gentle—soft pastels, calm textures, and joyful flavors.</p>
          </div>
        </div>

        <div class="about-grid">
          <div class="card about-card" data-parallax="0.08">
            <h3 style="margin:0; font-size:18px;">A bakery with a light touch</h3>
            <p class="about-text">
              Petal &amp; Crumb was born from a love of careful finishing—satin glazes, airy crumb, and pastel-inspired artistry.
              Our bakers craft each item in small batches, so every slice feels fresh, elegant, and beautifully balanced.
            </p>
            <p class="about-text">
              From celebration cakes to everyday breads, we keep the experience minimalist and premium—so you can enjoy the moment,
              not just the calories.
            </p>
            <div class="hero-actions" style="margin-top:18px;">
              <a class="btn" href="#contact">Ask About Custom Orders</a>
              <a class="btn btn-secondary" href="#menu">See What’s Baking</a>
            </div>
          </div>

          <div class="photo-frame" data-parallax="0.14">
            <img
              alt="Bakery interior with pastel desserts"
              src="https://images.unsplash.com/photo-1527515637462-cff94eecc1ac?auto=format&fit=crop&w=1200&q=70"
              loading="lazy"
            />
          </div>
        </div>
      </div>
    </section>

    <!-- GALLERY -->
    <section id="gallery" aria-label="Gallery">
      <div class="container">
        <div class="section-head">
          <div>
            <p class="kicker">Gallery</p>
            <h3 class="h2"><span class="grad-text">Light-framed</span> product moments</h3>
            <p class="section-sub">Hover tiles for a subtle lift and caption glow.</p>
          </div>
        </div>

        <div class="grid gallery-grid">
          <article class="card g-item g-tile" data-parallax="0.05">
            <div class="img-frame" data-tilt>
              <img alt="Vanilla cloud cake" src="https://images.unsplash.com/photo-1542826438-bd32f99c8f4f?auto=format&fit=crop&w=1200&q=70" loading="lazy" />
              <div class="cap"><b>Vanilla Cloud</b><span>Soft cream &amp; airy crumb</span></div>
            </div>
          </article>

          <article class="card g-item g-tile" data-parallax="0.05">
            <div class="img-frame" data-tilt>
              <img alt="Strawberry pastries" src="https://images.unsplash.com/photo-1464349095431-ebb6c4f8d5d7?auto=format&fit=crop&w=1200&q=70" loading="lazy" />
              <div class="cap"><b>Strawberry Petals</b><span>Light, bright, elegant</span></div>
            </div>
          </article>

          <article class="card g-item g-tile" data-parallax="0.05">
            <div class="img-frame" data-tilt>
              <img alt="Cheesecake slice" src="https://images.unsplash.com/photo-1541877084-18d54be2f9d4?auto=format&fit=crop&w=1200&q=70" loading="lazy" />
              <div class="cap"><b>Sky Cream</b><span>Velvety cheesecake layers</span></div>
            </div>
          </article>

          <article class="card g-item g-tile" data-parallax="0.05">
            <div class="img-frame" data-tilt>
              <img alt="Crispy croissants" src="https://images.unsplash.com/photo-1513104890138-7c749659a591?auto=format&fit=crop&w=1200&q=70" loading="lazy" />
              <div class="cap"><b>Halo Croissants</b><span>Buttery, flaky, golden</span></div>
            </div>
          </article>

          <article class="card g-item g-tile" data-parallax="0.05">
            <div class="img-frame" data-tilt>
              <img alt="Biscuit assortment" src="https://images.unsplash.com/photo-1541592106381-b31e9677c0e5?auto=format&fit=crop&w=1200&q=70" loading="lazy" />
              <div class="cap"><b>Butter Blossom</b><span>Perfect with tea</span></div>
            </div>
          </article>

          <article class="card g-item g-tile" data-parallax="0.05">
            <div class="img-frame" data-tilt>
              <img alt="Breads in a basket" src="https://images.unsplash.com/photo-1549931319-a545dcf6dd88?auto=format&fit=crop&w=1200&q=70" loading="lazy" />
              <div class="cap"><b>Garden Seed Bread</b><span>Warm &amp; nourishing</span></div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" aria-label="Contact">
      <div class="container">
        <div class="section-head">
          <div>
            <p class="kicker">Contact</p>
            <h3 class="h2"><span class="grad-text">Let’s</span> bake something special</h3>
            <p class="section-sub">Phone, email, and location—copy details with one tap.</p>
          </div>
        </div>

        <div class="grid contact-grid">
          <div class="card contact-card" data-parallax="0.06">
            <h3 style="margin:0; font-size:18px;">Reach Petal &amp; Crumb</h3>

            <div class="contact-row" aria-label="Phone">
              <div class="ico" aria-hidden="true">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.8 19.8 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6A19.8 19.8 0 0 1 2.11 4.18 2 2 0 0 1 4.1 2h3a2 2 0 0 1 2 1.72c.12.86.32 1.7.59 2.5a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.58-1.15a2 2 0 0 1 2.11-.45c.8.27 1.64.47 2.5.59A2 2 0 0 1 22 16.92z" stroke="rgba(8,33,44,.92)" stroke-width="1.8"/>
                </svg>
              </div>
              <div>
                <b>Phone</b>
                <p id="phoneText">+1 (555) 012-3456</p>
              </div>
              <button class="copy-btn" data-copy="#phoneText" data-kind="Phone">Copy</button>
            </div>

            <div class="contact-row" aria-label="Email">
              <div class="ico" aria-hidden="true">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M4 4h16a2 2 0 0 1 2 2v12a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2z" stroke="rgba(8,33,44,.92)" stroke-width="1.8"/>
                  <path d="m22 6-10 7L2 6" stroke="rgba(8,33,44,.92)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </div>
              <div>
                <b>Email</b>
                <p id="emailText">hello@petalcrum.bakery</p>
              </div>
              <button class="copy-btn" data-copy="#emailText" data-kind="Email">Copy</button>
            </div>

            <div class="contact-row" aria-label="Location">
              <div class="ico" aria-hidden="true">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M21 10c0 6-9 12-9 12s-9-6-9-12a9 9 0 0 1 18 0z" stroke="rgba(8,33,44,.92)" stroke-width="1.8"/>
                  <path d="M12 10a3 3 0 1 0 0-6 3 3 0 0 0 0 6z" stroke="rgba(8,33,44,.92)" stroke-width="1.8"/>
                </svg>
              </div>
              <div>
                <b>Location</b>
                <p>Rose Lane, Cozy District, 10012</p>
              </div>
            </div>

            <p class="muted" style="margin: 14px 0 0; line-height:1.6; font-size: 13.5px;">
              Custom orders welcome. Tell us your date, vibe, and flavor preferences.
            </p>
          </div>

          <div class="card map-frame" data-parallax="0.10">
            <iframe
              title="Bakery location map"
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
              src="https://www.google.com/maps?q=New%20York%20City&output=embed"
            ></iframe>
          </div>
        </div>
      </div>
    </section>

    <!-- FOOTER -->
    <footer aria-label="Footer">
      <div class="container">
        <div class="footer-row">
          <small>© <span id="year"></span> Petal &amp; Crumb Bakery. Light-theme premium bakes.</small>
          <div class="social" aria-label="Social media">
            <a href="#" aria-label="Instagram" title="Instagram">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M7 2h10a5 5 0 0 1 5 5v10a5 5 0 0 1-5 5H7a5 5 0 0 1-5-5V7a5 5 0 0 1 5-5z" stroke="rgba(31,42,55,.88)" stroke-width="1.8"/>
                <path d="M12 17a5 5 0 1 0 0-10 5 5 0 0 0 0 10z" stroke="rgba(31,42,55,.88)" stroke-width="1.8"/>
                <path d="M17.5 6.5h.01" stroke="rgba(31,42,55,.88)" stroke-width="2.6" stroke-linecap="round"/>
              </svg>
            </a>
            <a href="#" aria-label="Facebook" title="Facebook">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3V2z" stroke="rgba(31,42,55,.88)" stroke-width="1.8" stroke-linejoin="round"/>
              </svg>
            </a>
            <a href="#" aria-label="Twitter" title="Twitter">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M22 4s-1.8.9-3.1 1.1A4.2 4.2 0 0 0 12 8.1a12 12 0 0 1-8-4s-3 8 5 12c-2 1-4 1-4 1s2 4 9 3c7-1 9-6 9-10 0-.4 0-.8-.1-1.2A7 7 0 0 0 22 4z" stroke="rgba(31,42,55,.88)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </a>
          </div>
        </div>
      </div>
    </footer>
  </main>

  <script>
    (function(){
      const year = document.getElementById('year');
      if(year) year.textContent = new Date().getFullYear();

      // Parallax (smooth)
      const parallaxEls = Array.from(document.querySelectorAll('[data-parallax]'));
      const reduceMotion = window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches;
      let raf = 0;
      let lastY = window.scrollY || 0;

      function updateParallax(){
        raf = 0;
        if(reduceMotion) return;
        const y = window.scrollY || 0;
        const delta = y - lastY;
        lastY = y;
        const viewH = window.innerHeight || 800;

        for(const el of parallaxEls){
          const factor = parseFloat(el.getAttribute('data-parallax')) || 0;
          const rect = el.getBoundingClientRect();
          const mid = rect.top + rect.height/2;
          const t = (mid - viewH/2) / viewH; // roughly -1..1
          const amount = -t * factor * 120;
          el.style.transform = `translateY(${amount}px)`;

          // subtle additional tilt for hero cake
          if(el.id === 'cake' && Math.abs(delta) > 0){
            // no-op; handled below
          }
        }
      }

      window.addEventListener('scroll', () => {
        if(reduceMotion) return;
        if(!raf) raf = requestAnimationFrame(updateParallax);
      }, { passive:true });

      // Cake 3D tilt based on pointer
      const cake = document.getElementById('cake');
      const cakeWrap = document.querySelector('.cake-wrap');
      if(cake && cakeWrap && !reduceMotion){
        const maxTilt = 10;
        cakeWrap.addEventListener('pointermove', (e) => {
          const r = cakeWrap.getBoundingClientRect();
          const px = (e.clientX - r.left) / r.width; // 0..1
          const py = (e.clientY - r.top) / r.height;
          const ry = (px - 0.5) * maxTilt * 1.2;
          const rx = -(py - 0.5) * maxTilt;
          cake.style.setProperty('--rx', rx.toFixed(2) + 'deg');
          cake.style.setProperty('--ry', ry.toFixed(2) + 'deg');
        });
      }

      // Particle sparkles canvas
      const canvas = document.getElementById('sparkles');
      const ctx = canvas && canvas.getContext ? canvas.getContext('2d') : null;
      let particles = [];

      function resizeCanvas(){
        if(!canvas) return;
        const rect = canvas.getBoundingClientRect();
        const dpr = Math.min(2, window.devicePixelRatio || 1);
        canvas.width = Math.floor(rect.width * dpr);
        canvas.height = Math.floor(rect.height * dpr);
      }

      if(canvas && ctx && !reduceMotion){
        resizeCanvas();
        window.addEventListener('resize', resizeCanvas);

        const spawn = 70;
        const w = canvas.width, h = canvas.height;
        particles = Array.from({length: spawn}).map(() => ({
          x: Math.random()*w,
          y: Math.random()*h,
          vx: (Math.random() - 0.5) * 0.25,
          vy: -0.4 - Math.random()*0.6,
          r: 0.8 + Math.random()*1.6,
          life: 0.2 + Math.random()*0.8,
          hue: Math.random() < 0.5 ? 190 : 330
        }));

        let last = performance.now();
        function loop(now){
          const dt = Math.min(0.033, (now-last)/1000);
          last = now;

          const cw = canvas.width, ch = canvas.height;
          ctx.clearRect(0,0,cw,ch);

          for(const p of particles){
            p.life -= dt * 0.65;
            p.x += p.vx * (dt*60);
            p.y += p.vy * (dt*60);

            if(p.life <= 0 || p.y < -10){
              p.x = Math.random()*cw;
              p.y = ch + 10;
              p.vx = (Math.random() - 0.5) * 0.25;
              p.vy = -0.4 - Math.random()*0.6;
              p.r = 0.8 + Math.random()*1.6;
              p.life = 0.35 + Math.random()*0.8;
              p.hue = Math.random() < 0.5 ? 190 : 330;
            }

            const alpha = Math.max(0, Math.min(1, p.life));
            ctx.beginPath();
            ctx.fillStyle = `hsla(${p.hue}, 95%, 75%, ${alpha*0.55})`;
            ctx.arc(p.x, p.y, p.r, 0, Math.PI*2);
            ctx.fill();

            // glow
            ctx.beginPath();
            ctx.fillStyle = `hsla(${p.hue}, 95%, 80%, ${alpha*0.18})`;
            ctx.arc(p.x, p.y, p.r*3.2, 0, Math.PI*2);
            ctx.fill();
          }

          requestAnimationFrame(loop);
        }

        requestAnimationFrame(loop);
      }

      // Copy helpers
      const copyBtns = Array.from(document.querySelectorAll('[data-copy]'));
      async function copyText(text){
        try{
          await navigator.clipboard.writeText(text);
          return true;
        }catch{
          // fallback
          const ta = document.createElement('textarea');
          ta.value = text;
          ta.style.position = 'fixed';
          ta.style.top = '-9999px';
          document.body.appendChild(ta);
          ta.select();
          const ok = document.execCommand('copy');
          document.body.removeChild(ta);
          return ok;
        }
      }

      for(const btn of copyBtns){
        btn.addEventListener('click', async () => {
          const sel = btn.getAttribute('data-copy');
          const el = sel ? document.querySelector(sel) : null;
          const text = el ? el.textContent.trim() : btn.textContent.trim();
          const ok = await copyText(text);
          const old = btn.textContent;
          btn.textContent = ok ? 'Copied!' : 'Copy failed';
          setTimeout(()=> btn.textContent = old, 1200);
        });
      }

      // Gallery tilt on mouse
      const tilts = Array.from(document.querySelectorAll('[data-tilt]'));
      if(!reduceMotion){
        for(const tile of tilts){
          tile.addEventListener('pointermove', (e) => {
            const r = tile.getBoundingClientRect();
            const px = (e.clientX - r.left) / r.width;
            const py = (e.clientY - r.top) / r.height;
            const ry = (px - 0.5) * 10;
            const rx = -(py - 0.5) * 8;
            tile.style.transform = `rotateX(${rx.toFixed(2)}deg) rotateY(${ry.toFixed(2)}deg) translateY(-2px)`;
          });
          tile.addEventListener('pointerleave', () => {
            tile.style.transform = '';
          });
        }
      }

      // initial parallax
      if(!reduceMotion) updateParallax();
    })();
  </script>
</body>
</html>

