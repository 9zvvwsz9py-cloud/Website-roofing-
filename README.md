<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ongoing Roofing – Santa Clarita, CA</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,300&display=swap" rel="stylesheet" />
  <style>
    /* ─── Design Tokens ─── */
    :root {
      --rust:   #C8401A;
      --rust-lt:#E05530;
      --slate:  #1A1F2B;
      --slate-2:#252C3A;
      --fog:    #F4F1EC;
      --sand:   #DDD8CE;
      --white:  #FFFFFF;
      --gold:   #E8A832;
      --text:   #2A2A2A;
      --muted:  #6B6B6B;
      --ff-head: 'Bebas Neue', sans-serif;
      --ff-body: 'DM Sans', sans-serif;
      --radius:  6px;
      --shadow-card: 0 4px 24px rgba(0,0,0,.10);
    }

    /* ─── Reset ─── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body { font-family: var(--ff-body); color: var(--text); background: var(--fog); overflow-x: hidden; }
    img  { max-width: 100%; display: block; }
    a    { text-decoration: none; color: inherit; }

    /* ─── Utility ─── */
    .container { max-width: 1180px; margin: 0 auto; padding: 0 24px; }
    .btn-primary {
      display: inline-block;
      background: var(--rust);
      color: var(--white);
      font-family: var(--ff-body);
      font-weight: 600;
      font-size: .95rem;
      letter-spacing: .04em;
      padding: 14px 32px;
      border-radius: var(--radius);
      border: none;
      cursor: pointer;
      transition: background .2s, transform .15s;
    }
    .btn-primary:hover { background: var(--rust-lt); transform: translateY(-2px); }
    .btn-outline {
      display: inline-block;
      border: 2px solid var(--white);
      color: var(--white);
      font-family: var(--ff-body);
      font-weight: 600;
      font-size: .95rem;
      letter-spacing: .04em;
      padding: 12px 30px;
      border-radius: var(--radius);
      transition: background .2s, color .2s;
    }
    .btn-outline:hover { background: var(--white); color: var(--rust); }
    .section-label {
      display: inline-block;
      background: var(--rust);
      color: var(--white);
      font-size: .7rem;
      font-weight: 600;
      letter-spacing: .14em;
      text-transform: uppercase;
      padding: 5px 14px;
      border-radius: 2px;
      margin-bottom: 18px;
    }
    .section-title {
      font-family: var(--ff-head);
      font-size: clamp(2.2rem, 5vw, 3.6rem);
      line-height: 1;
      letter-spacing: .01em;
      color: var(--slate);
    }
    .section-subtitle {
      font-size: 1.05rem;
      color: var(--muted);
      line-height: 1.7;
      max-width: 520px;
    }

    /* ─── Topbar ─── */
    .topbar {
      background: var(--slate);
      color: var(--sand);
      font-size: .82rem;
      padding: 8px 0;
    }
    .topbar .container { display: flex; justify-content: space-between; align-items: center; gap: 12px; flex-wrap: wrap; }
    .topbar a { color: var(--gold); }

    /* ─── Nav ─── */
    .nav {
      position: sticky; top: 0; z-index: 100;
      background: var(--white);
      border-bottom: 3px solid var(--rust);
      box-shadow: 0 2px 12px rgba(0,0,0,.07);
    }
    .nav .container {
      display: flex; align-items: center; justify-content: space-between;
      padding-top: 14px; padding-bottom: 14px;
    }
    .nav-logo {
      display: flex; align-items: center; gap: 12px;
    }
    .nav-logo .icon {
      width: 42px; height: 42px;
      background: var(--rust);
      border-radius: 4px;
      display: flex; align-items: center; justify-content: center;
      flex-shrink: 0;
    }
    .nav-logo .icon svg { fill: var(--white); width: 24px; height: 24px; }
    .nav-logo .wordmark {
      font-family: var(--ff-head);
      font-size: 1.6rem;
      letter-spacing: .04em;
      color: var(--slate);
      line-height: 1;
    }
    .nav-logo .sub { font-size: .7rem; letter-spacing: .1em; color: var(--muted); text-transform: uppercase; font-family: var(--ff-body); }
    .nav-links { display: flex; gap: 32px; align-items: center; }
    .nav-links a { font-size: .9rem; font-weight: 500; color: var(--slate); transition: color .2s; }
    .nav-links a:hover { color: var(--rust); }
    .nav-cta { font-size: .9rem !important; }
    .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; background: none; border: none; padding: 4px; }
    .hamburger span { display: block; width: 26px; height: 2px; background: var(--slate); border-radius: 2px; transition: .3s; }
    #menu-toggle { display: none; }
    #menu-toggle:checked ~ .nav-links { display: flex; }

    /* ─── Hero ─── */
    .hero {
      position: relative;
      min-height: 88vh;
      background: var(--slate);
      display: flex; align-items: center;
      overflow: hidden;
    }
    .hero-bg {
      position: absolute; inset: 0;
      background:
        linear-gradient(135deg, rgba(26,31,43,.95) 0%, rgba(26,31,43,.7) 60%, rgba(200,64,26,.35) 100%),
        repeating-linear-gradient(
          45deg,
          rgba(255,255,255,.015) 0px,
          rgba(255,255,255,.015) 1px,
          transparent 1px,
          transparent 40px
        );
    }
    /* Decorative roof silhouette */
    .hero-bg::after {
      content: '';
      position: absolute;
      bottom: 0; left: 0; right: 0;
      height: 220px;
      background:
        linear-gradient(to bottom right, transparent 49.5%, rgba(200,64,26,.18) 50%) left/50% 100% no-repeat,
        linear-gradient(to bottom left,  transparent 49.5%, rgba(200,64,26,.18) 50%) right/50% 100% no-repeat;
    }
    .hero .container { position: relative; z-index: 2; padding-top: 60px; padding-bottom: 100px; }
    .hero-badge {
      display: inline-flex; align-items: center; gap: 8px;
      background: rgba(232,168,50,.15);
      border: 1px solid rgba(232,168,50,.4);
      color: var(--gold);
      font-size: .8rem; font-weight: 600; letter-spacing: .1em;
      text-transform: uppercase; padding: 6px 16px; border-radius: 100px;
      margin-bottom: 28px;
    }
    .hero-badge .dot { width: 7px; height: 7px; background: var(--gold); border-radius: 50%; animation: pulse 1.8s infinite; }
    @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.4} }
    .hero h1 {
      font-family: var(--ff-head);
      font-size: clamp(3.5rem, 9vw, 7rem);
      color: var(--white);
      line-height: .95;
      letter-spacing: .01em;
      margin-bottom: 28px;
    }
    .hero h1 em { color: var(--rust-lt); font-style: normal; }
    .hero p {
      font-size: 1.15rem; color: rgba(255,255,255,.75);
      line-height: 1.7; max-width: 520px; margin-bottom: 42px;
    }
    .hero-btns { display: flex; gap: 16px; flex-wrap: wrap; }
    .hero-stats {
      display: flex; gap: 40px; margin-top: 64px; flex-wrap: wrap;
    }
    .hero-stat .num {
      font-family: var(--ff-head);
      font-size: 2.8rem;
      color: var(--white);
      letter-spacing: .02em;
      line-height: 1;
    }
    .hero-stat .label { font-size: .82rem; color: rgba(255,255,255,.55); letter-spacing: .06em; text-transform: uppercase; margin-top: 4px; }

    /* ─── Trust Strip ─── */
    .trust {
      background: var(--rust);
      padding: 18px 0;
    }
    .trust .container {
      display: flex; align-items: center; justify-content: center;
      gap: 40px; flex-wrap: wrap;
    }
    .trust-item {
      display: flex; align-items: center; gap: 10px;
      color: var(--white); font-size: .9rem; font-weight: 500;
    }
    .trust-item svg { opacity: .9; flex-shrink: 0; }

    /* ─── Services ─── */
    .services { padding: 100px 0; background: var(--white); }
    .services-head { margin-bottom: 60px; }
    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 24px;
    }
    .service-card {
      background: var(--fog);
      border-radius: 10px;
      padding: 36px 30px;
      border: 1px solid var(--sand);
      position: relative;
      overflow: hidden;
      transition: transform .2s, box-shadow .2s;
    }
    .service-card:hover { transform: translateY(-6px); box-shadow: var(--shadow-card); }
    .service-card::before {
      content: '';
      position: absolute; top: 0; left: 0; right: 0; height: 3px;
      background: var(--rust);
      transform: scaleX(0); transform-origin: left;
      transition: transform .3s;
    }
    .service-card:hover::before { transform: scaleX(1); }
    .service-icon {
      width: 52px; height: 52px;
      background: var(--rust);
      border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
      margin-bottom: 20px;
    }
    .service-icon svg { fill: var(--white); width: 26px; height: 26px; }
    .service-card h3 { font-family: var(--ff-head); font-size: 1.55rem; color: var(--slate); margin-bottom: 10px; letter-spacing: .02em; }
    .service-card p  { font-size: .92rem; color: var(--muted); line-height: 1.65; }

    /* ─── Why Us ─── */
    .why { background: var(--slate); color: var(--white); padding: 100px 0; }
    .why .container { display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center; }
    .why .section-title { color: var(--white); }
    .why .section-subtitle { color: rgba(255,255,255,.6); }
    .why-list { margin-top: 40px; display: flex; flex-direction: column; gap: 24px; }
    .why-item { display: flex; gap: 18px; align-items: flex-start; }
    .why-num {
      font-family: var(--ff-head);
      font-size: 2.4rem; color: var(--rust);
      line-height: 1; flex-shrink: 0; width: 48px;
    }
    .why-item h4 { font-weight: 600; font-size: 1rem; margin-bottom: 4px; }
    .why-item p  { font-size: .9rem; color: rgba(255,255,255,.6); line-height: 1.6; }
    .why-visual {
      background: var(--slate-2);
      border-radius: 12px;
      padding: 40px;
      border: 1px solid rgba(255,255,255,.07);
      display: flex; flex-direction: column; gap: 24px;
    }
    .rating-block { text-align: center; }
    .rating-block .big { font-family: var(--ff-head); font-size: 5rem; color: var(--white); line-height: 1; }
    .rating-block .stars { font-size: 1.5rem; color: var(--gold); letter-spacing: 4px; margin: 6px 0; }
    .rating-block .sub { font-size: .82rem; color: rgba(255,255,255,.45); }
    .divider { height: 1px; background: rgba(255,255,255,.08); }
    .proof-row { display: flex; justify-content: space-around; }
    .proof-item { text-align: center; }
    .proof-item .n { font-family: var(--ff-head); font-size: 2.2rem; color: var(--rust-lt); }
    .proof-item .l { font-size: .78rem; color: rgba(255,255,255,.45); text-transform: uppercase; letter-spacing: .07em; margin-top: 4px; }

    /* ─── Reviews ─── */
    .reviews { padding: 100px 0; background: var(--fog); }
    .reviews-head { margin-bottom: 60px; }
    .reviews-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr)); gap: 24px; }
    .review-card {
      background: var(--white);
      border-radius: 10px;
      padding: 30px 28px;
      box-shadow: var(--shadow-card);
      border-left: 4px solid var(--rust);
      display: flex; flex-direction: column; gap: 14px;
    }
    .review-stars { color: var(--gold); font-size: 1.1rem; letter-spacing: 3px; }
    .review-text { font-size: .93rem; line-height: 1.7; color: var(--text); font-style: italic; }
    .review-author { display: flex; align-items: center; gap: 12px; margin-top: auto; padding-top: 14px; border-top: 1px solid var(--sand); }
    .review-avatar {
      width: 40px; height: 40px; border-radius: 50%;
      background: var(--rust);
      display: flex; align-items: center; justify-content: center;
      color: var(--white); font-weight: 700; font-size: .95rem; flex-shrink: 0;
    }
    .review-author .name { font-weight: 600; font-size: .9rem; }
    .review-author .date { font-size: .78rem; color: var(--muted); }
    .yelp-badge {
      display: inline-flex; align-items: center; gap: 6px;
      font-size: .75rem; color: var(--muted); margin-top: 4px;
    }
    .yelp-badge svg { width: 14px; height: 14px; }

    /* ─── Process ─── */
    .process { padding: 100px 0; background: var(--white); }
    .process-steps {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 0; margin-top: 60px; position: relative;
    }
    .process-steps::before {
      content: '';
      position: absolute; top: 32px; left: 10%; right: 10%; height: 2px;
      background: repeating-linear-gradient(90deg, var(--sand) 0px, var(--sand) 8px, transparent 8px, transparent 16px);
      z-index: 0;
    }
    .step { text-align: center; padding: 0 20px; position: relative; z-index: 1; }
    .step-num {
      width: 64px; height: 64px; border-radius: 50%;
      background: var(--rust); color: var(--white);
      font-family: var(--ff-head); font-size: 1.8rem;
      display: flex; align-items: center; justify-content: center;
      margin: 0 auto 20px;
      box-shadow: 0 0 0 6px var(--white), 0 0 0 7px var(--sand);
    }
    .step h4 { font-weight: 600; font-size: 1rem; margin-bottom: 8px; }
    .step p  { font-size: .87rem; color: var(--muted); line-height: 1.6; }

    /* ─── CTA Band ─── */
    .cta-band {
      background: var(--rust);
      padding: 80px 0;
      position: relative; overflow: hidden;
    }
    .cta-band::before {
      content: 'ONGOING';
      position: absolute; right: -40px; top: -30px;
      font-family: var(--ff-head);
      font-size: 14rem; color: rgba(255,255,255,.06); pointer-events: none; line-height: 1;
    }
    .cta-band .container { position: relative; z-index: 2; display: flex; align-items: center; justify-content: space-between; gap: 32px; flex-wrap: wrap; }
    .cta-band h2 { font-family: var(--ff-head); font-size: clamp(2rem, 5vw, 3.5rem); color: var(--white); line-height: 1; }
    .cta-band p  { color: rgba(255,255,255,.75); font-size: 1rem; margin-top: 10px; }
    .cta-band .btn-outline:hover { color: var(--rust); }

    /* ─── Contact ─── */
    .contact { padding: 100px 0; background: var(--fog); }
    .contact .container { display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: start; }
    .contact-form { background: var(--white); border-radius: 12px; padding: 48px 40px; box-shadow: var(--shadow-card); }
    .form-group { margin-bottom: 20px; }
    .form-group label { display: block; font-size: .83rem; font-weight: 600; letter-spacing: .05em; text-transform: uppercase; margin-bottom: 7px; color: var(--slate); }
    .form-group input,
    .form-group select,
    .form-group textarea {
      width: 100%;
      border: 1.5px solid var(--sand);
      border-radius: var(--radius);
      padding: 11px 14px;
      font-family: var(--ff-body);
      font-size: .92rem;
      color: var(--text);
      background: var(--fog);
      transition: border-color .2s;
      outline: none;
    }
    .form-group input:focus,
    .form-group select:focus,
    .form-group textarea:focus { border-color: var(--rust); background: var(--white); }
    .form-group textarea { resize: vertical; min-height: 110px; }
    .contact-form .btn-primary { width: 100%; text-align: center; font-size: 1rem; padding: 16px; }
    .contact-info { display: flex; flex-direction: column; gap: 32px; }
    .contact-info .section-title { margin-bottom: 8px; }
    .info-block { display: flex; gap: 16px; align-items: flex-start; }
    .info-icon {
      width: 44px; height: 44px; flex-shrink: 0;
      background: var(--rust);
      border-radius: 8px;
      display: flex; align-items: center; justify-content: center;
    }
    .info-icon svg { fill: var(--white); width: 20px; height: 20px; }
    .info-block h4 { font-weight: 600; font-size: .9rem; margin-bottom: 3px; }
    .info-block p,
    .info-block a { font-size: .95rem; color: var(--muted); }
    .info-block a:hover { color: var(--rust); }

    /* ─── Footer ─── */
    .footer { background: var(--slate); color: rgba(255,255,255,.55); padding: 60px 0 32px; }
    .footer-top { display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 48px; margin-bottom: 48px; }
    .footer-logo { font-family: var(--ff-head); font-size: 2rem; color: var(--white); letter-spacing: .04em; margin-bottom: 12px; }
    .footer-tagline { font-size: .88rem; line-height: 1.7; max-width: 280px; }
    .footer-col h5 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .12em; color: var(--white); margin-bottom: 18px; }
    .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: 10px; }
    .footer-col ul a { font-size: .88rem; transition: color .2s; }
    .footer-col ul a:hover { color: var(--rust-lt); }
    .footer-bottom { border-top: 1px solid rgba(255,255,255,.07); padding-top: 28px; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px; font-size: .8rem; }
    .footer-bottom a { color: var(--rust-lt); }

    /* ─── Responsive ─── */
    @media (max-width: 860px) {
      .why .container { grid-template-columns: 1fr; gap: 48px; }
      .contact .container { grid-template-columns: 1fr; gap: 48px; }
      .footer-top { grid-template-columns: 1fr 1fr; }
      .process-steps::before { display: none; }
      .nav-links {
        display: none;
        position: absolute; top: 100%; left: 0; right: 0;
        background: var(--white);
        flex-direction: column;
        padding: 20px 24px;
        border-top: 1px solid var(--sand);
        box-shadow: 0 8px 24px rgba(0,0,0,.1);
        gap: 16px;
      }
      .hamburger { display: flex; }
      #menu-toggle:checked ~ .nav-links { display: flex; }
    }
    @media (max-width: 560px) {
      .hero h1 { font-size: 3.2rem; }
      .hero-stats { gap: 24px; }
      .footer-top { grid-template-columns: 1fr; }
      .cta-band .container { flex-direction: column; }
      .topbar .container { justify-content: center; text-align: center; }
    }

    /* ─── Scroll animations ─── */
    .fade-up {
      opacity: 0; transform: translateY(30px);
      transition: opacity .6s ease, transform .6s ease;
    }
    .fade-up.visible { opacity: 1; transform: translateY(0); }
  </style>
</head>
<body>

  <!-- ════ TOPBAR ════ -->
  <div class="topbar">
    <div class="container">
      <span>📍 Proudly Serving Santa Clarita, CA &amp; Surrounding Areas</span>
      <span>Call Now: <a href="tel:+14242444404">(424) 244-4404</a></span>
    </div>
  </div>

  <!-- ════ NAV ════ -->
  <nav class="nav">
    <div class="container">
      <a href="#" class="nav-logo">
        <div class="icon">
          <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path d="M12 3L2 12h3v9h5v-6h4v6h5v-9h3L12 3z"/>
          </svg>
        </div>
        <div>
          <div class="wordmark">Ongoing Roofing</div>
          <div class="sub">Santa Clarita, CA</div>
        </div>
      </a>

      <input type="checkbox" id="menu-toggle" />
      <label class="hamburger" for="menu-toggle">
        <span></span><span></span><span></span>
      </label>

      <div class="nav-links">
        <a href="#services">Services</a>
        <a href="#why">Why Us</a>
        <a href="#process">Process</a>
        <a href="#contact" class="btn-primary nav-cta">Free Estimate</a>
      </div>
    </div>
  </nav>

  <!-- ════ HERO ════ -->
  <section class="hero">
    <div class="hero-bg"></div>
    <div class="container">
      <div class="hero-badge">
        <span class="dot"></span>
        5-Star Rated on Yelp · Santa Clarita's Trusted Roofers
      </div>
      <h1>Your Roof.<br>Our <em>Ongoing</em><br>Commitment.</h1>
      <p>Expert residential roofing for Santa Clarita homeowners — done right the first time. Repairs, replacements, tile, shingle, flat roofs &amp; more.</p>
      <div class="hero-btns">
        <a href="#contact" class="btn-primary">Get a Free Estimate</a>
        <a href="tel:+14242444404" class="btn-outline">(424) 244-4404 — Call Now</a>
      </div>
      <div class="hero-stats">
        <div class="hero-stat"><div class="num">5★</div><div class="label">Yelp Rating</div></div>
        <div class="hero-stat"><div class="num">100%</div><div class="label">Licensed &amp; Insured</div></div>
        <div class="hero-stat"><div class="num">SCV</div><div class="label">Local &amp; Family-Owned</div></div>
      </div>
    </div>
  </section>

  <!-- ════ TRUST STRIP ════ -->
  <div class="trust">
    <div class="container">
      <div class="trust-item">
        <svg width="20" height="20" fill="none" viewBox="0 0 24 24" stroke="white" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"/></svg>
        Licensed &amp; Insured
      </div>
      <div class="trust-item">
        <svg width="20" height="20" fill="none" viewBox="0 0 24 24" stroke="white" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/></svg>
        Free Estimates
      </div>
      <div class="trust-item">
        <svg width="20" height="20" fill="none" viewBox="0 0 24 24" stroke="white" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/></svg>
        Serving Santa Clarita Valley
      </div>
      <div class="trust-item">
        <svg width="20" height="20" fill="none" viewBox="0 0 24 24" stroke="white" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M11.049 2.927c.3-.921 1.603-.921 1.902 0l1.519 4.674a1 1 0 00.95.69h4.915c.969 0 1.371 1.24.588 1.81l-3.976 2.888a1 1 0 00-.363 1.118l1.518 4.674c.3.922-.755 1.688-1.538 1.118l-3.976-2.888a1 1 0 00-1.176 0l-3.976 2.888c-.783.57-1.838-.197-1.538-1.118l1.518-4.674a1 1 0 00-.363-1.118l-3.976-2.888c-.784-.57-.38-1.81.588-1.81h4.914a1 1 0 00.951-.69l1.519-4.674z"/></svg>
        5-Star Yelp Reviews
      </div>
      <div class="trust-item">
        <svg width="20" height="20" fill="none" viewBox="0 0 24 24" stroke="white" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 7V5z"/></svg>
        (424) 244-4404
      </div>
    </div>
  </div>

  <!-- ════ SERVICES ════ -->
  <section class="services" id="services">
    <div class="container">
      <div class="services-head">
        <span class="section-label">What We Do</span>
        <h2 class="section-title fade-up">Complete Roofing<br>Solutions</h2>
        <p class="section-subtitle fade-up" style="margin-top:14px;">From a single missing shingle to a full re-roof, Ongoing Roofing handles every job with the same care and craftsmanship Santa Clarita homeowners depend on.</p>
      </div>
      <div class="services-grid">
        <div class="service-card fade-up">
          <div class="service-icon">
            <svg viewBox="0 0 24 24"><path d="M12 3L2 12h3v9h5v-6h4v6h5v-9h3L12 3z"/></svg>
          </div>
          <h3>Roof Replacement</h3>
          <p>Full tear-off and re-roof for residential properties. We work with all major manufacturers and stand behind our installs with a workmanship warranty.</p>
        </div>
        <div class="service-card fade-up">
          <div class="service-icon">
            <svg viewBox="0 0 24 24"><path d="M19.428 15.428a2 2 0 00-1.022-.547l-2.387-.477a6 6 0 00-3.86.517l-.318.158a6 6 0 01-3.86.517L6.05 15.21a2 2 0 00-1.806.547M8 4h8l-1 1v5.172a2 2 0 00.586 1.414l5 5c1.26 1.26.367 3.414-1.415 3.414H4.828c-1.782 0-2.674-2.154-1.414-3.414l5-5A2 2 0 009 10.172V5L8 4z"/></svg>
          </div>
          <h3>Leak Repair</h3>
          <p>Accurate leak detection and lasting repairs — not just patches. We identify the source and fix it right so it doesn't come back.</p>
        </div>
        <div class="service-card fade-up">
          <div class="service-icon">
            <svg viewBox="0 0 24 24"><path d="M9 3H5a2 2 0 00-2 2v4m6-6h10a2 2 0 012 2v4M9 3v18m0 0h10a2 2 0 002-2V9M9 21H5a2 2 0 01-2-2V9m0 0h18"/></svg>
          </div>
          <h3>Tile Roofing</h3>
          <p>Clay and concrete tile installation, repair, and re-setting. We understand Santa Clarita's California Spanish architecture inside and out.</p>
        </div>
        <div class="service-card fade-up">
          <div class="service-icon">
            <svg viewBox="0 0 24 24"><path d="M20 7l-8-4-8 4m16 0l-8 4m8-4v10l-8 4m0-10L4 7m8 4v10M4 7v10l8 4"/></svg>
          </div>
          <h3>Shingle Roofing</h3>
          <p>Asphalt composition shingles installed with precision. Architectural, 3-tab, impact-resistant — we'll help you choose the right product for your home and budget.</p>
        </div>
        <div class="service-card fade-up">
          <div class="service-icon">
            <svg viewBox="0 0 24 24"><path d="M3 15a4 4 0 004 4h9a5 5 0 10-.1-9.999 5.002 5.002 0 10-9.78 2.096A4.001 4.001 0 003 15z"/></svg>
          </div>
          <h3>Flat &amp; Low-Slope</h3>
          <p>Torch-down, TPO, and foam flat roof systems for patios, additions, and commercial-style structures. Properly sloped and sealed to handle SoCal weather.</p>
        </div>
        <div class="service-card fade-up">
          <div class="service-icon">
            <svg viewBox="0 0 24 24"><path d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"/></svg>
          </div>
          <h3>Roof Inspection</h3>
          <p>Detailed visual and physical inspection with a written report. Great for pre-purchase due diligence or insurance documentation.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ════ WHY US ════ -->
  <section class="why" id="why">
    <div class="container">
      <div>
        <span class="section-label">Why Ongoing Roofing</span>
        <h2 class="section-title fade-up">We Actually Show<br>Up &amp; Deliver</h2>
        <p class="section-subtitle fade-up" style="margin-top:14px;">Santa Clarita homeowners have a lot of options. Here's why they keep calling us back — and referring their neighbors.</p>
        <div class="why-list">
          <div class="why-item fade-up">
            <div class="why-num">01</div>
            <div>
              <h4>Honest Estimates, No Games</h4>
              <p>We quote what the job actually requires. No inflated scopes, no surprise line items at the end.</p>
            </div>
          </div>
          <div class="why-item fade-up">
            <div class="why-num">02</div>
            <div>
              <h4>Responsive Communication</h4>
              <p>You'll always know the status of your project. Real answers from real people — not a call center.</p>
            </div>
          </div>
          <div class="why-item fade-up">
            <div class="why-num">03</div>
            <div>
              <h4>Clean, Respectful Jobsite</h4>
              <p>We protect your landscaping, clean up daily, and do a final magnetic sweep for nails. Your property is treated like ours.</p>
            </div>
          </div>
          <div class="why-item fade-up">
            <div class="why-num">04</div>
            <div>
              <h4>Local &amp; Accountable</h4>
              <p>We live and work in Santa Clarita. Our reputation matters here, and we stand behind every single job.</p>
            </div>
          </div>
        </div>
      </div>
      <div class="why-visual fade-up">
        <div class="rating-block">
          <div class="big">5.0</div>
          <div class="stars">★★★★★</div>
          <div class="sub">Average Yelp Rating</div>
        </div>
        <div class="divider"></div>
        <div class="proof-row">
          <div class="proof-item">
            <div class="n">5★</div>
            <div class="l">Yelp Reviews</div>
          </div>
          <div class="proof-item">
            <div class="n">SCV</div>
            <div class="l">Local Roots</div>
          </div>
          <div class="proof-item">
            <div class="n">C-39</div>
            <div class="l">Licensed</div>
          </div>
        </div>
        <div class="divider"></div>
        <div style="color:rgba(255,255,255,.55); font-size:.85rem; line-height:1.6; text-align:center;">
          "They were professional, thorough, and the price was fair. I wouldn't hesitate to recommend Ongoing Roofing to anyone in Santa Clarita."
          <div style="margin-top:10px; color:var(--gold); font-size:.78rem;">— Yelp Reviewer ★★★★★</div>
        </div>
      </div>
    </div>
  </section>



  <!-- ════ PROCESS ════ -->
  <section class="process" id="process">
    <div class="container">
      <div style="text-align:center; max-width:540px; margin:0 auto;">
        <span class="section-label">How It Works</span>
        <h2 class="section-title fade-up">Simple. Transparent.<br>No Surprises.</h2>
      </div>
      <div class="process-steps">
        <div class="step fade-up">
          <div class="step-num">1</div>
          <h4>Call or Request Online</h4>
          <p>Reach out by phone or fill out the form below. We'll respond same day.</p>
        </div>
        <div class="step fade-up">
          <div class="step-num">2</div>
          <h4>Free On-Site Estimate</h4>
          <p>We inspect your roof in person and give you a clear, itemized written quote.</p>
        </div>
        <div class="step fade-up">
          <div class="step-num">3</div>
          <h4>Scheduled &amp; Confirmed</h4>
          <p>Once you approve, we lock in your start date and order materials.</p>
        </div>
        <div class="step fade-up">
          <div class="step-num">4</div>
          <h4>Work Completed</h4>
          <p>Our crew completes the job on time, cleans up completely, and does a final walkthrough with you.</p>
        </div>
        <div class="step fade-up">
          <div class="step-num">5</div>
          <h4>Warranty &amp; Follow-Up</h4>
          <p>Your roof is backed by a workmanship warranty. We're a phone call away if you ever need us.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ════ CTA BAND ════ -->
  <section class="cta-band">
    <div class="container">
      <div>
        <h2>Ready for a Roof<br>You Can Count On?</h2>
        <p>Free estimates · No pressure · Licensed &amp; insured</p>
      </div>
      <div style="display:flex; gap:16px; flex-wrap:wrap;">
        <a href="#contact" class="btn-primary" style="background:var(--white); color:var(--rust);">Get a Free Estimate</a>
        <a href="tel:+14242444404" class="btn-outline">(424) 244-4404 — Call Now</a>
      </div>
    </div>
  </section>

  <!-- ════ CONTACT ════ -->
  <section class="contact" id="contact">
    <div class="container">
      <div class="contact-info">
        <div>
          <span class="section-label">Get In Touch</span>
          <h2 class="section-title fade-up">Let's Talk<br>About Your Roof</h2>
          <p class="section-subtitle fade-up" style="margin-top:14px;">No obligation, no hard sell. Just an honest conversation and a free look at your roof.</p>
        </div>
        <div class="info-block fade-up">
          <div class="info-icon"><svg viewBox="0 0 24 24"><path d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 7V5z"/></svg></div>
          <div>
            <h4>Phone</h4>
            <a href="tel:+14242444404">(424) 244-4404</a>
          </div>
        </div>
        <div class="info-block fade-up">
          <div class="info-icon"><svg viewBox="0 0 24 24"><path d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg></div>
          <div>
            <h4>Service Area</h4>
            <p>Santa Clarita, Valencia, Newhall, Canyon Country, Saugus, Stevenson Ranch &amp; surrounding areas</p>
          </div>
        </div>
        <div class="info-block fade-up">
          <div class="info-icon"><svg viewBox="0 0 24 24"><path d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"/></svg></div>
          <div>
            <h4>Office Address</h4>
            <p>23450 Newhall Ave, Ste 12<br>Newhall, CA 91321</p>
          </div>
        </div>
        <div class="info-block fade-up">
          <div class="info-icon"><svg viewBox="0 0 24 24"><path d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"/></svg></div>
          <div>
            <h4>Hours</h4>
            <!-- ★ INSERT REAL HOURS ★ -->
            <p>Mon – Thu: 7:00 AM – 6:00 PM<br>Friday: 9:00 AM – 6:00 PM<br>Saturday: 7:00 AM – 6:00 PM<br>Sunday: Closed</p>
          </div>
        </div>
        <div class="info-block fade-up">
          <div class="info-icon"><svg viewBox="0 0 24 24"><path d="M11.049 2.927c.3-.921 1.603-.921 1.902 0l1.519 4.674a1 1 0 00.95.69h4.915c.969 0 1.371 1.24.588 1.81l-3.976 2.888a1 1 0 00-.363 1.118l1.518 4.674c.3.922-.755 1.688-1.538 1.118l-3.976-2.888a1 1 0 00-1.176 0l-3.976 2.888c-.783.57-1.838-.197-1.538-1.118l1.518-4.674a1 1 0 00-.363-1.118l-3.976-2.888c-.784-.57-.38-1.81.588-1.81h4.914a1 1 0 00.951-.69l1.519-4.674z"/></svg></div>
          <div>
            <h4>Find Us on Yelp</h4>
            <a href="https://www.yelp.com/biz/ongoing-roofing-santa-clarita" target="_blank" rel="noopener">Read Our Reviews ↗</a>
          </div>
        </div>
      </div>

      <div class="contact-form fade-up">
        <h3 style="font-family:var(--ff-head); font-size:2rem; color:var(--slate); margin-bottom:28px; letter-spacing:.02em;">Free Estimate<br>Request</h3>
        <form action="#" method="POST">
          <div class="form-group">
            <label for="name">Your Name</label>
            <input type="text" id="name" name="name" placeholder="Jane Smith" required />
          </div>
          <div class="form-group">
            <label for="phone">Phone Number</label>
            <input type="tel" id="phone" name="phone" placeholder="(661) 555-0000" required />
          </div>
          <div class="form-group">
            <label for="email">Email Address</label>
            <input type="email" id="email" name="email" placeholder="jane@example.com" />
          </div>
          <div class="form-group">
            <label for="service">Service Needed</label>
            <select id="service" name="service">
              <option value="">Select a service…</option>
              <option>Roof Replacement</option>
              <option>Leak Repair</option>
              <option>Tile Roofing</option>
              <option>Shingle Roofing</option>
              <option>Flat / Low-Slope Roof</option>
              <option>Roof Inspection</option>
              <option>Other / Not Sure</option>
            </select>
          </div>
          <div class="form-group">
            <label for="message">Tell Us More (optional)</label>
            <textarea id="message" name="message" placeholder="Briefly describe your roof situation or what you're looking for…"></textarea>
          </div>
          <button type="submit" class="btn-primary">Send My Request</button>
          <p style="font-size:.78rem; color:var(--muted); margin-top:12px; text-align:center;">We'll respond within one business day. No spam, ever.</p>
        </form>
      </div>
    </div>
  </section>

  <!-- ════ FOOTER ════ -->
  <footer class="footer">
    <div class="container">
      <div class="footer-top">
        <div>
          <div class="footer-logo">Ongoing Roofing</div>
          <p class="footer-tagline">Honest, reliable roofing for Santa Clarita homeowners. Licensed, insured, and committed to doing it right.</p>
          <div style="margin-top:20px;">
            <a href="https://www.yelp.com/biz/ongoing-roofing-santa-clarita" target="_blank" rel="noopener" style="display:inline-flex; align-items:center; gap:6px; color:var(--gold); font-size:.85rem;">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="#E8A832"><path d="M20.16 12.73l-4.65-1.34c-.82-.24-1.57.54-1.27 1.34l1.75 4.52c.3.78 1.37.88 1.81.17l2.9-3.18c.44-.49.2-1.26-.54-1.51zm-8.5 5.6l-.23-4.82c-.04-.86-.97-1.34-1.68-.84l-3.97 2.78c-.7.49-.57 1.56.22 1.88l4.2 1.61c.79.3 1.5-.23 1.46-1.01l.01-.9-.01.3zm-5.4-8.14l3.97 2.78c.7.5 1.64.02 1.68-.84l.22-4.82c.05-.78-.67-1.31-1.46-1.01l-4.2 1.61c-.79.3-.92 1.38-.22 1.88l.01-.02v.42zm6.68-6.66L12.7 8c-.3.8.45 1.58 1.27 1.34l4.65-1.34c.74-.22.98-.99.54-1.51L16.26 3.3c-.44-.71-1.51-.61-1.81.17l-.01-.02.5.08z"/></svg>
              View us on Yelp ★★★★★
            </a>
          </div>
        </div>
        <div class="footer-col">
          <h5>Services</h5>
          <ul>
            <li><a href="#services">Roof Replacement</a></li>
            <li><a href="#services">Leak Repair</a></li>
            <li><a href="#services">Tile Roofing</a></li>
            <li><a href="#services">Shingle Roofing</a></li>
            <li><a href="#services">Flat Roofs</a></li>
            <li><a href="#services">Roof Inspection</a></li>
          </ul>
        </div>
        <div class="footer-col">
          <h5>Company</h5>
          <ul>
            <li><a href="#why">Why Us</a></li>
            <li><a href="#process">Our Process</a></li>
            <li><a href="#contact">Free Estimate</a></li>
            <li><a href="https://www.yelp.com/biz/ongoing-roofing-santa-clarita" target="_blank" rel="noopener">Yelp Profile ↗</a></li>
          </ul>
        </div>
      </div>
      <div class="footer-bottom">
        <span>© 2025 Ongoing Roofing · 23450 Newhall Ave Ste 12, Newhall CA 91321 · (424) 244-4404</span>
        <span>Built to protect what matters most</span>
      </div>
    </div>
  </footer>

  <script>
    // Scroll-triggered fade-up animations
    const observer = new IntersectionObserver(entries => {
      entries.forEach(e => {
        if (e.isIntersecting) {
          e.target.classList.add('visible');
          observer.unobserve(e.target);
        }
      });
    }, { threshold: 0.12 });

    document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

    // Close mobile menu when a link is clicked
    document.querySelectorAll('.nav-links a').forEach(link => {
      link.addEventListener('click', () => {
        document.getElementById('menu-toggle').checked = false;
      });
    });
  </script>
</body>
</html>
