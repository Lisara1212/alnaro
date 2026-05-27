<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Alnaro Resort</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet" />
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
