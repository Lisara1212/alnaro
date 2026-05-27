<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Alnaro Resort</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet" />
  <style>
    /* ── RESET & TOKENS ── */
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
    :root {
      --primary:   #0b3d91;
      --gold:      #c9973a;
      --gold-dark: #a87c2e;
      --bg:        #f9f7f4;
      --white:     #ffffff;
      --text:      #1a1a1a;
      --muted:     #6b6b6b;
      --border:    #e4ddd4;
    }
    html { scroll-behavior: smooth; }
    body { font-family: 'Inter', sans-serif; background: var(--bg); color: var(--text); }
    img  { display: block; max-width: 100%; }
    a    { text-decoration: none; color: inherit; }

    /* ── UTILITY ── */
    .serif   { font-family: 'Cormorant Garamond', serif; }
    .section { padding: 90px 24px; }
    .container { max-width: 1100px; margin: 0 auto; }
    .section-label {
      font-size: 10px; letter-spacing: .35em; text-transform: uppercase;
      color: var(--gold); margin-bottom: 10px;
    }
    .section-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 4vw, 3rem); font-weight: 300;
      color: var(--text); margin-bottom: 12px;
    }
    .divider {
      width: 48px; height: 1px; background: var(--gold); margin-bottom: 48px;
    }
    .section-header { text-align: center; }
    .section-header .divider { margin: 12px auto 48px; }

    /* ── NAVBAR ── */
    #navbar {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      padding: 20px 48px; display: flex; align-items: center;
      justify-content: space-between;
      transition: background .4s, padding .4s, box-shadow .4s;
    }
    #navbar.scrolled {
      background: rgba(255,255,255,.97); backdrop-filter: blur(8px);
      padding: 12px 48px; box-shadow: 0 1px 20px rgba(0,0,0,.08);
    }
    .logo-mark  { font-family: 'Cormorant Garamond', serif; font-size: 22px; letter-spacing: .18em; color: #fff; transition: color .4s; }
    .logo-sub   { font-size: 9px; letter-spacing: .38em; text-transform: uppercase; color: #f5c96e; transition: color .4s; }
    #navbar.scrolled .logo-mark { color: var(--primary); }
    #navbar.scrolled .logo-sub  { color: var(--gold); }

    .nav-links { display: flex; align-items: center; gap: 32px; }
    .nav-links a {
      font-size: 10px; letter-spacing: .22em; text-transform: uppercase;
      color: #fff; transition: opacity .3s;
    }
    .nav-links a:hover { opacity: .65; }
    #navbar.scrolled .nav-links a { color: var(--text); }
    .nav-book {
      font-size: 10px; letter-spacing: .18em; text-transform: uppercase;
      padding: 10px 22px; border: 1px solid #f5c96e; color: #f5c96e;
      transition: background .3s, color .3s;
    }
    .nav-book:hover { background: #f5c96e; color: #fff; }
    #navbar.scrolled .nav-book { border-color: var(--gold); color: var(--gold); }
    #navbar.scrolled .nav-book:hover { background: var(--gold); color: #fff; }

    /* mobile */
    .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; background: none; border: none; }
    .hamburger span { width: 22px; height: 2px; background: #fff; transition: background .4s; }
    #navbar.scrolled .hamburger span { background: var(--text); }
    .mobile-menu {
      display: none; flex-direction: column; gap: 16px;
      background: #fff; padding: 20px 24px; border-top: 1px solid var(--border);
    }
    .mobile-menu.open { display: flex; }
    .mobile-menu a { font-size: 12px; letter-spacing: .18em; text-transform: uppercase; color: var(--text); }

    /* ── HERO ── */
    #hero {
      position: relative; height: 100vh; min-height: 600px;
      display: flex; align-items: center; justify-content: center; overflow: hidden;
    }
    #hero img.hero-bg {
      position: absolute; inset: 0; width: 100%; height: 100%; object-fit: cover;
    }
    .hero-overlay {
      position: absolute; inset: 0;
      background: linear-gradient(to bottom, rgba(0,0,0,.5), rgba(0,0,0,.28), rgba(0,0,0,.62));
    }
    .hero-content {
      position: relative; z-index: 2; text-align: center; padding: 0 24px; max-width: 700px;
      animation: fadeUp .9s ease both;
    }
    .hero-eyebrow {
      font-size: 10px; letter-spacing: .4em; text-transform: uppercase;
      color: #f5c96e; margin-bottom: 16px;
    }
    .hero-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(3rem, 8vw, 6rem); font-weight: 300;
      color: #fff; line-height: 1; margin-bottom: 10px;
    }
    .hero-rule { width: 80px; height: 1px; background: #f5c96e; margin: 16px auto 18px; }
    .hero-tagline {
      font-family: 'Cormorant Garamond', serif; font-style: italic;
      font-size: 1.2rem; color: rgba(255,255,255,.8); margin-bottom: 36px;
    }
    .btn-gold {
      display: inline-block; font-size: 10px; letter-spacing: .25em;
      text-transform: uppercase; padding: 14px 32px;
      background: #f5c96e; color: #fff; transition: background .3s;
    }
    .btn-gold:hover { background: var(--gold-dark); }
    .scroll-down {
      position: absolute; bottom: 28px; left: 50%; transform: translateX(-50%);
      color: rgba(255,255,255,.55); font-size: 26px; animation: bounce 1.5s infinite;
    }

    /* ── SERVICES ── */
    #services { background: var(--white); }
    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 24px;
    }
    .service-card {
      padding: 32px; border: 1px solid var(--border);
      transition: border-color .3s, box-shadow .3s;
    }
    .service-card:hover { border-color: rgba(201,151,58,.4); box-shadow: 0 8px 28px rgba(0,0,0,.07); }
    .service-icon { font-size: 22px; margin-bottom: 18px; color: var(--gold); }
    .service-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.4rem; font-weight: 400; margin-bottom: 8px;
    }
    .service-rule { width: 28px; height: 1px; background: var(--gold); margin-bottom: 10px; transition: width .3s; }
    .service-card:hover .service-rule { width: 56px; }
    .service-desc { font-size: 13px; color: var(--muted); line-height: 1.7; }

    /* ── ROOMS ── */
    #rooms { background: var(--bg); }
    .rooms-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 24px; }
    .room-card { background: var(--white); overflow: hidden; box-shadow: 0 2px 12px rgba(0,0,0,.06); transition: box-shadow .4s; }
    .room-card:hover { box-shadow: 0 12px 40px rgba(0,0,0,.12); }
    .room-img { overflow: hidden; height: 240px; }
    .room-img img { width: 100%; height: 100%; object-fit: cover; transition: transform .7s; }
    .room-card:hover .room-img img { transform: scale(1.06); }
    .room-body { padding: 24px; }
    .room-subtitle { font-size: 10px; letter-spacing: .3em; text-transform: uppercase; color: var(--gold); margin-bottom: 6px; }
    .room-title { font-family: 'Cormorant Garamond', serif; font-size: 1.5rem; font-weight: 400; margin-bottom: 8px; }
    .room-rule { width: 28px; height: 1px; background: var(--gold); margin-bottom: 10px; }
    .room-desc { font-size: 13px; color: var(--muted); line-height: 1.7; margin-bottom: 18px; }
    .room-link {
      font-size: 10px; letter-spacing: .2em; text-transform: uppercase;
      color: var(--primary); border-bottom: 1px solid var(--primary);
      padding-bottom: 2px; transition: color .3s, border-color .3s;
    }
    .room-link:hover { color: var(--gold); border-color: var(--gold); }

    /* ── GALLERY ── */
    #gallery { background: var(--white); }
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-auto-rows: 220px;
      gap: 10px;
    }
    .gallery-item {
      position: relative; overflow: hidden; cursor: pointer;
    }
    .gallery-item:first-child { grid-column: span 2; grid-row: span 2; }
    .gallery-item img { width: 100%; height: 100%; object-fit: cover; transition: transform .7s; }
    .gallery-item:hover img { transform: scale(1.07); }
    .gallery-label {
      position: absolute; bottom: 0; left: 0; right: 0; padding: 12px 14px;
      background: linear-gradient(transparent, rgba(0,0,0,.55));
      font-size: 10px; letter-spacing: .2em; text-transform: uppercase;
      color: #fff; opacity: 0; transition: opacity .3s;
    }
    .gallery-item:hover .gallery-label { opacity: 1; }

    /* lightbox */
    #lightbox {
      display: none; position: fixed; inset: 0; z-index: 200;
      background: rgba(0,0,0,.92); align-items: center; justify-content: center;
    }
    #lightbox.open { display: flex; }
    #lightbox img { max-width: 92vw; max-height: 88vh; object-fit: contain; }
    #lb-close {
      position: absolute; top: 18px; right: 22px; font-size: 28px;
      color: #fff; cursor: pointer; background: none; border: none; transition: color .3s;
    }
    #lb-close:hover { color: #f5c96e; }

    /* ── TESTIMONIALS ── */
    #testimonials { background: var(--primary); }
    #testimonials .section-label { color: #f5c96e; }
    #testimonials .section-title { color: #fff; }
    #testimonials .divider { background: #f5c96e; }
    .reviews-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; }
    .review-card {
      background: rgba(255,255,255,.06); border: 1px solid rgba(255,255,255,.1);
      padding: 32px;
    }
    .stars { color: #f5c96e; font-size: 14px; margin-bottom: 14px; letter-spacing: 3px; }
    .review-text {
      font-family: 'Cormorant Garamond', serif; font-style: italic;
      font-size: 1.05rem; color: rgba(255,255,255,.8); line-height: 1.7; margin-bottom: 20px;
    }
    .reviewer { display: flex; align-items: center; gap: 12px; }
    .reviewer-avatar {
      width: 38px; height: 38px; border-radius: 50%;
      background: rgba(201,151,58,.25);
      display: flex; align-items: center; justify-content: center;
      font-family: 'Cormorant Garamond', serif; font-size: 1.2rem; color: #f5c96e;
      flex-shrink: 0;
    }
    .reviewer-name { font-size: 13px; color: #fff; }
    .reviewer-tag  { font-size: 9px; letter-spacing: .15em; color: rgba(255,255,255,.35); text-transform: uppercase; }

    /* ── CONTACT ── */
    #contact { background: var(--bg); }
    .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 48px; align-items: start; }
    .contact-row { display: flex; align-items: flex-start; gap: 16px; margin-bottom: 24px; }
    .contact-icon { font-size: 18px; color: var(--gold); margin-top: 2px; flex-shrink: 0; }
    .contact-meta { font-size: 9px; letter-spacing: .22em; text-transform: uppercase; color: var(--muted); margin-bottom: 4px; }
    .contact-val { font-family: 'Cormorant Garamond', serif; font-size: 1.2rem; }
    .contact-val a { transition: color .3s; }
    .contact-val a:hover { color: var(--gold); }

    .amenities-label { font-size: 9px; letter-spacing: .25em; text-transform: uppercase; color: var(--muted); margin-bottom: 14px; }
    .amenities-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
    .amenity-chip {
      display: flex; align-items: center; gap: 10px;
      background: var(--white); border: 1px solid var(--border);
      padding: 10px 14px; font-size: 13px;
    }
    .amenity-chip span.icon { font-size: 16px; color: var(--gold); }

    .payment-label { font-size: 9px; letter-spacing: .25em; text-transform: uppercase; color: var(--muted); margin: 24px 0 10px; }
    .payment-badges { display: flex; gap: 10px; }
    .badge {
      font-size: 11px; font-weight: 600; letter-spacing: .12em;
      padding: 6px 12px; border: 1px solid;
    }
    .badge-visa { color: var(--primary); border-color: rgba(11,61,145,.3); }
    .badge-mc   { color: #c0392b; border-color: rgba(192,57,43,.25); }

    .cta-card { background: var(--white); padding: 40px; box-shadow: 0 2px 16px rgba(0,0,0,.06); }
    .cta-title { font-family: 'Cormorant Garamond', serif; font-size: 1.8rem; margin-bottom: 8px; }
    .cta-rule  { width: 28px; height: 1px; background: var(--gold); margin-bottom: 20px; }
    .cta-desc  { font-size: 13px; color: var(--muted); line-height: 1.75; margin-bottom: 28px; }
    .btn-primary {
      display: block; text-align: center; font-size: 11px; letter-spacing: .22em;
      text-transform: uppercase; padding: 15px; background: var(--primary);
      color: #fff; margin-bottom: 12px; transition: opacity .3s;
    }
    .btn-primary:hover { opacity: .88; }
    .btn-outline {
      display: block; text-align: center; font-size: 11px; letter-spacing: .22em;
      text-transform: uppercase; padding: 15px;
      border: 1px solid var(--gold); color: var(--gold);
      transition: background .3s, color .3s;
    }
    .btn-outline:hover { background: var(--gold); color: #fff; }

    /* ── FOOTER ── */
    footer {
      background: #0d0d0d; padding: 36px 48px;
      display: flex; align-items: center; justify-content: space-between;
      flex-wrap: wrap; gap: 12px;
    }
    .footer-brand { font-family: 'Cormorant Garamond', serif; font-size: 18px; letter-spacing: .2em; color: #fff; }
    .footer-sub   { font-size: 9px; letter-spacing: .3em; color: rgba(255,255,255,.35); margin-top: 4px; }
    .footer-copy  { font-size: 10px; color: rgba(255,255,255,.25); letter-spacing: .1em; }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp   { from { opacity: 0; transform: translateY(24px); } to { opacity: 1; transform: translateY(0); } }
    @keyframes bounce   { 0%,100% { transform: translateX(-50%) translateY(0); } 50% { transform: translateX(-50%) translateY(8px); } }
    .fade-in { opacity: 0; transform: translateY(28px); transition: opacity .7s ease, transform .7s ease; }
    .fade-in.visible { opacity: 1; transform: translateY(0); }

    /* ── RESPONSIVE ── */
    @media (max-width: 768px) {
      #navbar { padding: 16px 20px; }
      #navbar.scrolled { padding: 10px 20px; }
      .nav-links { display: none; }
      .hamburger { display: flex; }
      .gallery-grid { grid-template-columns: repeat(2, 1fr); grid-auto-rows: 160px; }
      .gallery-item:first-child { grid-column: span 2; grid-row: span 1; }
      .contact-grid { grid-template-columns: 1fr; }
      footer { flex-direction: column; align-items: center; text-align: center; padding: 28px 20px; }
    }
    @media (max-width: 480px) {
      .gallery-grid { grid-template-columns: 1fr; }
      .gallery-item:first-child { grid-column: span 1; }
    }
  </style>
  
</head>
  
<body>

  <!-- ══ NAVBAR ══ -->
  <nav id="navbar">
    <div class="logo">
      <div class="logo-mark">ALNARO</div>
      <div class="logo-sub">Resort</div>
    </div>
    <div class="nav-links">
      <a href="#rooms">Rooms</a>
      <a href="#services">Services</a>
      <a href="#gallery">Gallery</a>
      <a href="#contact">Contact</a>
      <a href="#contact" class="nav-book">Book Now</a>
    </div>
    <button class="hamburger" id="ham" aria-label="Menu">
      <span></span><span></span><span></span>
    </button>
  </nav>
  <div class="mobile-menu" id="mobileMenu">
    <a href="#rooms"    onclick="closeMobile()">Rooms</a>
    <a href="#services" onclick="closeMobile()">Services</a>
    <a href="#gallery"  onclick="closeMobile()">Gallery</a>
    <a href="#contact"  onclick="closeMobile()">Contact</a>
  </div>

  <!-- ══ HERO ══ -->
  <section id="hero">
    <img class="hero-bg" src="https://media.base44.com/images/public/user_6a05f5e24a5e76f2b7ec447f/684e3e41b_alnaro.jpg" alt="Alnaro Resort" />
    <div class="hero-overlay"></div>
    <div class="hero-content">
      <p class="hero-eyebrow">Moratuwa, Sri Lanka</p>
      <h1 class="hero-title">Alnaro Resort</h1>
      <div class="hero-rule"></div>
      <p class="hero-tagline">Carry Memories Forever</p>
      <a href="#rooms" class="btn-gold">Explore Rooms</a>
    </div>
    <div class="scroll-down">&#8964;</div>
  </section>

  <!-- ══ SERVICES ══ -->
  <section id="services" class="section">
    <div class="container">
      <div class="section-header fade-in">
        <p class="section-label">What We Offer</p>
        <h2 class="section-title">Our Experiences</h2>
        <div class="divider"></div>
      </div>
      <div class="services-grid">
        <div class="service-card fade-in">
          <div class="service-icon">🍽️</div>
          <h3 class="service-title">Fine Dining</h3>
          <div class="service-rule"></div>
          <p class="service-desc">Authentic Sri Lankan cuisine and international dishes crafted with fresh local ingredients.</p>
        </div>
        <div class="service-card fade-in">
          <div class="service-icon">🌿</div>
          <h3 class="service-title">Hangouts</h3>
          <div class="service-rule"></div>
          <p class="service-desc">Lush garden spaces perfect for relaxing afternoons and casual gatherings.</p>
        </div>
        <div class="service-card fade-in">
          <div class="service-icon">🎉</div>
          <h3 class="service-title">Private Parties</h3>
          <div class="service-rule"></div>
          <p class="service-desc">Elegant banquet hall for weddings, birthdays, and corporate events.</p>
        </div>
        <div class="service-card fade-in">
          <div class="service-icon">🛏️</div>
          <h3 class="service-title">Luxury Rooms</h3>
          <div class="service-rule"></div>
          <p class="service-desc">Spacious rooms with canopy beds, modern amenities, and serene ambiance.</p>
        </div>
        <div class="service-card fade-in">
          <div class="service-icon">☀️</div>
          <h3 class="service-title">Day Outing</h3>
          <div class="service-rule"></div>
          <p class="service-desc">Full-day packages with meals, activities, and pool access for groups.</p>
        </div>
       
    
    </div>
  </section>

  <!-- ══ ROOMS ══ -->
  <section id="rooms" class="section" style="background:#f9f7f4;">
    <div class="container">
      <div class="section-header fade-in">
        <p class="section-label">Accommodations</p>
        <h2 class="section-title">Our Rooms</h2>
        <div class="divider"></div>
      </div>
      <div class="rooms-grid">
        <div class="room-card fade-in">
          <div class="room-img"><img src="https://media.base44.com/images/public/user_6a05f5e24a5e76f2b7ec447f/5b4d123f0_IMG_6351.jpg" alt="Deluxe Room" /></div>
          <div class="room-body">
            <p class="room-subtitle">Comfort &amp; Elegance</p>
            <h3 class="room-title">Deluxe Room</h3>
            <div class="room-rule"></div>
            <p class="room-desc">Tastefully furnished with dark wood, blue accents, warm lamps, and blackout curtains for a restful stay.</p>
            <a href="#contact" class="room-link">Enquire →</a>
          </div>
        </div>
        <div class="room-card fade-in">
          <div class="room-img"><img src="https://media.base44.com/images/public/user_6a05f5e24a5e76f2b7ec447f/72761c35f_IMG_7333.jpg" alt="Superior Suite" /></div>
          <div class="room-body">
            <p class="room-subtitle">Space &amp; Serenity</p>
            <h3 class="room-title">Superior Suite</h3>
            <div class="room-rule"></div>
            <p class="room-desc">A spacious suite with a four-poster canopy bed, sitting area, and soft teal tones throughout.</p>
            <a href="#contact" class="room-link">Enquire →</a>
          </div>
        </div>
        <div class="room-card fade-in">
          <div class="room-img"><img src="https://media.base44.com/images/public/user_6a05f5e24a5e76f2b7ec447f/1b4777fac_IMG_8141.jpg" alt="Luxury Suite" /></div>
          <div class="room-body">
            <p class="room-subtitle">Ultimate Indulgence</p>
            <h3 class="room-title">Luxury Suite</h3>
            <div class="room-rule"></div>
            <p class="room-desc">Our premier suite featuring a majestic canopy bed, lounge seating, and private tranquil ambiance.</p>
            <a href="#contact" class="room-link">Enquire →</a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ══ GALLERY ══ -->
  <section id="gallery" class="section" style="background:#fff;">
    <div class="container">
      <div class="section-header fade-in">
        <p class="section-label">Visual Tour</p>
        <h2 class="section-title">Gallery</h2>
        <div class="divider"></div>
      </div>
      <div class="gallery-grid fade-in">
        <div class="gallery-item" onclick="openLb(this)"><img src="https://media.base44.com/images/public/user_6a05f5e24a5e76f2b7ec447f/a3a382e37_hall.jpg" alt="Banquet Hall"/><div class="gallery-label">Banquet Hall</div></div>
        <div class="gallery-item" onclick="openLb(this)"><img src="https://media.base44.com/images/public/user_6a05f5e24a5e76f2b7ec447f/a0dd9cb91_IMG_6353.jpg" alt="Room Detail"/><div class="gallery-label">Room Detail</div></div>
        <div class="gallery-item" onclick="openLb(this)"><img src="https://media.base44.com/images/public/user_6a05f5e24a5e76f2b7ec447f/5979981c2_IMG_6355.jpg" alt="Deluxe Room"/><div class="gallery-label">Deluxe Room</div></div>
        <div class="gallery-item" onclick="openLb(this)"><img src="https://media.base44.com/images/public/user_6a05f5e24a5e76f2b7ec447f/a24b5c4bb_IMG_8145.jpg" alt="Suite Canopy"/><div class="gallery-label">Suite Canopy</div></div>
        <div class="gallery-item" onclick="openLb(this)"><img src="https://media.base44.com/images/public/user_6a05f5e24a5e76f2b7ec447f/3f551d860_IMG_8053.jpg" alt="Luxury Suite"/><div class="gallery-label">Luxury Suite</div></div>
        <div class="gallery-item" onclick="openLb(this)"><img src="https://media.base44.com/images/public/user_6a05f5e24a5e76f2b7ec447f/8ab9ce99f_IMG_8062.jpg" alt="Suite View"/><div class="gallery-label">Suite View</div></div>
        <div class="gallery-item" onclick="openLb(this)"><img src="https://media.base44.com/images/public/user_6a05f5e24a5e76f2b7ec447f/ea4cdf30d_IMG_8064.jpg" alt="Premium Suite"/><div class="gallery-label">Premium Suite</div></div>
      </div>
    </div>
  </section>

  <!-- Lightbox -->
  <div id="lightbox" onclick="closeLb()">
    <button id="lb-close" onclick="closeLb()">✕</button>
    <img id="lb-img" src="" alt="" onclick="event.stopPropagation()" />
  </div>

  <!-- ══ TESTIMONIALS ══ -->
  <section id="testimonials" class="section">
    <div class="container">
      <div class="section-header fade-in">
        <p class="section-label">Guest Experiences</p>
        <h2 class="section-title" style="color:#fff;">What Our Guests Say</h2>
        <div class="divider" style="background:#f5c96e;margin:12px auto 48px;"></div>
      </div>
      <div class="reviews-grid">
        <div class="review-card fade-in">
          <div class="stars">★★★★★</div>
          <p class="review-text">"Excellent place to stay. Room was very clean, modern, large and comfortable. Good value for money. Definitely gonna go back!"</p>
          <div class="reviewer">
            <div class="reviewer-avatar">S</div>
            <div><div class="reviewer-name">Sadeera Ekanayaka</div><div class="reviewer-tag">Verified Guest</div></div>
          </div>
        </div>
        <div class="review-card fade-in">
          <div class="stars">★★★★★</div>
          <p class="review-text">"The canopy suite was absolutely stunning. Staff were incredibly warm and attentive — a truly memorable experience."</p>
          <div class="reviewer">
            <div class="reviewer-avatar">P</div>
            <div><div class="reviewer-name">Priya Fernando</div><div class="reviewer-tag">Verified Guest</div></div>
          </div>
        </div>
        <div class="review-card fade-in">
          <div class="stars">★★★★★</div>
          <p class="review-text">"Held our company event at the banquet hall — perfectly arranged. Beautiful venue, great food, wonderful service throughout."</p>
          <div class="reviewer">
            <div class="reviewer-avatar">R</div>
            <div><div class="reviewer-name">Ranjith Perera</div><div class="reviewer-tag">Verified Guest</div></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ══ CONTACT ══ -->
  <section id="contact" class="section">
    <div class="container">
      <div class="section-header fade-in">
        <p class="section-label">Get In Touch</p>
        <h2 class="section-title">Contact &amp; Location</h2>
        <div class="divider"></div>
      </div>
      <div class="contact-grid fade-in">
        <div>
          <div class="contact-row">
            <div class="contact-icon">📍</div>
            <div>
              <div class="contact-meta">Address</div>
              <div class="contact-val">556/G De Soysa Rd, Molpe, Moratuwa</div>
            </div>
          </div>
          <div class="contact-row">
            <div class="contact-icon">📞</div>
            <div>
              <div class="contact-meta">Phone</div>
              <div class="contact-val"><a href="tel:0762409496">0762 409 496</a></div>
            </div>
          </div>
          <div>
            <div class="amenities-label">Amenities</div>
            <div class="amenities-grid">
              <div class="amenity-chip"><span class="icon">📶</span> Free Wi-Fi</div>
              <div class="amenity-chip"><span class="icon">🚗</span> Parking</div>
              <div class="amenity-chip"><span class="icon">☕</span> Restaurant</div>
              <div class="amenity-chip"><span class="icon">📺</span> Smart TV</div>
            </div>
          </div>
          <div class="payment-label">We Accept</div>
          <div class="payment-badges">
            <span class="badge badge-visa">VISA</span>
            <span class="badge badge-mc">MC</span>
          </div>
        </div>
        <div class="cta-card">
          <h3 class="cta-title">Make a Reservation</h3>
          <div class="cta-rule"></div>
          <p class="cta-desc">Ready for an unforgettable stay? Contact us directly to check availability, discuss packages, or plan your next event at Alnaro Resort.</p>
          <a href="tel:0762409496" class="btn-primary">Call to Book</a>
          <a href="https://wa.me/94762409496" target="_blank" class="btn-outline">WhatsApp Us</a>
        </div>
      </div>
    </div>
  </section>

  <!-- ══ FOOTER ══ -->
  <footer>
    <div>
      <div class="footer-brand">ALNARO RESORT</div>
      <div class="footer-sub">Moratuwa, Sri Lanka</div>
    </div>
    <div class="footer-copy">© 2026 Alnaro Resort. All rights reserved.</div>
  </footer>

  <script>
    // ── Sticky Navbar ──
    const nav = document.getElementById('navbar');
    window.addEventListener('scroll', () => {
      nav.classList.toggle('scrolled', window.scrollY > 60);
    });

    // ── Mobile Menu ──
    const ham = document.getElementById('ham');
    const mob = document.getElementById('mobileMenu');
    ham.addEventListener('click', () => mob.classList.toggle('open'));
    function closeMobile() { mob.classList.remove('open'); }

    // ── Lightbox ──
    const lb    = document.getElementById('lightbox');
    const lbImg = document.getElementById('lb-img');
    function openLb(el) {
      lbImg.src = el.querySelector('img').src;
      lbImg.alt = el.querySelector('img').alt;
      lb.classList.add('open');
      document.body.style.overflow = 'hidden';
    }
    function closeLb() {
      lb.classList.remove('open');
      document.body.style.overflow = '';
    }
    document.addEventListener('keydown', e => { if (e.key === 'Escape') closeLb(); });

    // ── Scroll Fade-in ──
    const observer = new IntersectionObserver(entries => {
      entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); } });
    }, { threshold: 0.12 });
    document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
  </script>
</body>
</html>
