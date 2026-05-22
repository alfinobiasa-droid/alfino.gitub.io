<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Portfolio TKJ — Network Engineer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com"/>
  <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg: #060a10;
      --bg2: #0b1120;
      --blue: #1a7fff;
      --blue-dim: #0f4fa8;
      --blue-glow: rgba(26,127,255,0.18);
      --cyan: #00d4ff;
      --text: #e8edf5;
      --muted: #6b7a99;
      --border: rgba(26,127,255,0.2);
      --card: rgba(11,17,32,0.85);
      --radius: 12px;
      --mono: 'Space Mono', monospace;
      --sans: 'Syne', sans-serif;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--sans);
      line-height: 1.7;
      overflow-x: hidden;
    }

    /* ── SCROLLBAR ── */
    ::-webkit-scrollbar { width: 4px; }
    ::-webkit-scrollbar-track { background: var(--bg); }
    ::-webkit-scrollbar-thumb { background: var(--blue); border-radius: 2px; }

    /* ── NOISE OVERLAY ── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 0;
      opacity: 0.5;
    }

    /* ── GRID BG ── */
    .grid-bg {
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(var(--border) 1px, transparent 1px),
        linear-gradient(90deg, var(--border) 1px, transparent 1px);
      background-size: 60px 60px;
      z-index: 0;
      pointer-events: none;
      mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 30%, transparent 100%);
    }

    /* ── NAVBAR ── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      padding: 0 5%;
      height: 64px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      background: rgba(6,10,16,0.8);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
    }

    .nav-logo {
      font-family: var(--mono);
      font-size: 0.9rem;
      color: var(--blue);
      letter-spacing: 0.05em;
    }

    .nav-logo span { color: var(--cyan); }

    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .nav-links a {
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--muted);
      text-decoration: none;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      transition: color 0.25s;
      position: relative;
    }

    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -4px; left: 0;
      width: 0; height: 1px;
      background: var(--blue);
      transition: width 0.3s;
    }

    .nav-links a:hover { color: var(--blue); }
    .nav-links a:hover::after { width: 100%; }

    .hamburger {
      display: none;
      flex-direction: column;
      gap: 5px;
      cursor: pointer;
      background: none;
      border: none;
      padding: 4px;
    }

    .hamburger span {
      display: block;
      width: 24px;
      height: 2px;
      background: var(--blue);
      border-radius: 2px;
      transition: 0.3s;
    }

    /* ── SECTION BASE ── */
    section {
      position: relative;
      z-index: 1;
      padding: 100px 5%;
      max-width: 1100px;
      margin: 0 auto;
    }

    .section-label {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--blue);
      letter-spacing: 0.18em;
      text-transform: uppercase;
      margin-bottom: 0.5rem;
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }

    .section-label::before {
      content: '';
      display: inline-block;
      width: 24px;
      height: 1px;
      background: var(--blue);
    }

    h2 {
      font-family: var(--sans);
      font-size: clamp(1.8rem, 4vw, 2.8rem);
      font-weight: 800;
      color: var(--text);
      margin-bottom: 2.5rem;
      line-height: 1.15;
    }

    /* ── HERO ── */
    #hero {
      min-height: 100vh;
      padding-top: 120px;
      display: flex;
      align-items: center;
    }

    .hero-inner {
      display: grid;
      grid-template-columns: 1fr 300px;
      gap: 4rem;
      align-items: center;
      width: 100%;
    }

    .hero-tag {
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--cyan);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 1.25rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .hero-tag::before {
      content: '▸';
      animation: blink 1.2s step-end infinite;
    }

    @keyframes blink { 50% { opacity: 0; } }

    h1 {
      font-family: var(--sans);
      font-size: clamp(2.8rem, 6vw, 5rem);
      font-weight: 800;
      line-height: 1.05;
      margin-bottom: 1rem;
    }

    h1 .accent { color: var(--blue); }

    .hero-sub {
      font-family: var(--mono);
      font-size: 0.9rem;
      color: var(--muted);
      max-width: 480px;
      margin-bottom: 2.5rem;
      line-height: 1.8;
    }

    .hero-cta {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.75rem 1.75rem;
      border-radius: 6px;
      font-family: var(--mono);
      font-size: 0.8rem;
      letter-spacing: 0.06em;
      cursor: pointer;
      text-decoration: none;
      transition: all 0.25s;
    }

    .btn-primary {
      background: var(--blue);
      color: #fff;
      border: 1px solid var(--blue);
    }

    .btn-primary:hover {
      background: transparent;
      color: var(--blue);
      box-shadow: 0 0 24px var(--blue-glow);
    }

    .btn-ghost {
      background: transparent;
      color: var(--muted);
      border: 1px solid var(--border);
    }

    .btn-ghost:hover {
      border-color: var(--blue);
      color: var(--blue);
    }

    /* ── PROFILE CARD ── */
    .profile-card {
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 1rem;
    }

    .avatar-wrap {
      position: relative;
      width: 180px;
      height: 180px;
    }

    .avatar-wrap::before {
      content: '';
      position: absolute;
      inset: -6px;
      border-radius: 50%;
      border: 2px solid transparent;
      background: linear-gradient(135deg, var(--blue), var(--cyan)) border-box;
      -webkit-mask: linear-gradient(#fff 0 0) padding-box, linear-gradient(#fff 0 0);
      -webkit-mask-composite: destination-out;
      mask-composite: exclude;
      animation: spin 8s linear infinite;
    }

    @keyframes spin { to { transform: rotate(360deg); } }

    .avatar-wrap::after {
      content: '';
      position: absolute;
      inset: 0;
      border-radius: 50%;
      background: radial-gradient(circle at 30% 30%, rgba(26,127,255,0.3), transparent 70%);
    }

    .avatar-img {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      object-fit: cover;
      background: linear-gradient(135deg, #0b1a35 0%, #0d2060 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 4rem;
      user-select: none;
      position: relative;
      overflow: hidden;
    }

    .avatar-placeholder {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      background: linear-gradient(135deg, #0b1a35, #0d2060);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 3.5rem;
    }

    .status-badge {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--muted);
      background: var(--card);
      border: 1px solid var(--border);
      padding: 0.35rem 0.85rem;
      border-radius: 20px;
    }

    .dot {
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background: #22c55e;
      animation: pulse-dot 2s ease-in-out infinite;
    }

    @keyframes pulse-dot {
      0%, 100% { box-shadow: 0 0 0 0 rgba(34,197,94,0.5); }
      50% { box-shadow: 0 0 0 6px rgba(34,197,94,0); }
    }

    /* ── ABOUT ── */
    #about .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 3rem;
      align-items: start;
    }

    .about-text p {
      color: var(--muted);
      font-size: 0.95rem;
      margin-bottom: 1.25rem;
      line-height: 1.85;
    }

    .about-text p strong { color: var(--text); }

    .info-list {
      display: flex;
      flex-direction: column;
      gap: 0.75rem;
    }

    .info-item {
      display: flex;
      gap: 1rem;
      align-items: flex-start;
      font-family: var(--mono);
      font-size: 0.8rem;
    }

    .info-key {
      color: var(--blue);
      min-width: 90px;
      flex-shrink: 0;
    }

    .info-val { color: var(--muted); }

    /* ── SKILLS ── */
    #skills .skills-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.25rem;
    }

    .skill-item {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.25rem 1.5rem;
      transition: border-color 0.3s, transform 0.3s;
    }

    .skill-item:hover {
      border-color: var(--blue);
      transform: translateY(-2px);
    }

    .skill-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 0.75rem;
    }

    .skill-name {
      font-family: var(--mono);
      font-size: 0.8rem;
      color: var(--text);
    }

    .skill-pct {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--blue);
    }

    .bar-track {
      height: 4px;
      background: rgba(255,255,255,0.06);
      border-radius: 2px;
      overflow: hidden;
    }

    .bar-fill {
      height: 100%;
      border-radius: 2px;
      background: linear-gradient(90deg, var(--blue-dim), var(--blue), var(--cyan));
      width: 0;
      transition: width 1.2s cubic-bezier(0.4,0,0.2,1);
    }

    .skill-cat {
      font-size: 0.65rem;
      font-family: var(--mono);
      color: var(--muted);
      margin-top: 0.4rem;
    }

    /* ── PROJECTS ── */
    #projects .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 1.5rem;
    }

    .project-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1.75rem;
      transition: border-color 0.3s, transform 0.3s, box-shadow 0.3s;
      position: relative;
      overflow: hidden;
    }

    .project-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 2px;
      background: linear-gradient(90deg, var(--blue), var(--cyan));
      transform: scaleX(0);
      transform-origin: left;
      transition: transform 0.4s;
    }

    .project-card:hover {
      border-color: var(--blue);
      transform: translateY(-4px);
      box-shadow: 0 16px 40px rgba(26,127,255,0.12);
    }

    .project-card:hover::before { transform: scaleX(1); }

    .project-icon {
      font-size: 1.75rem;
      margin-bottom: 1rem;
    }

    .project-title {
      font-size: 1rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
      color: var(--text);
    }

    .project-desc {
      font-size: 0.85rem;
      color: var(--muted);
      line-height: 1.75;
      margin-bottom: 1rem;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
    }

    .tag {
      font-family: var(--mono);
      font-size: 0.65rem;
      padding: 0.25rem 0.65rem;
      border-radius: 4px;
      background: rgba(26,127,255,0.1);
      color: var(--blue);
      border: 1px solid rgba(26,127,255,0.25);
      letter-spacing: 0.04em;
    }

    /* ── CONTACT ── */
    #contact .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 3rem;
    }

    .contact-info p {
      color: var(--muted);
      font-size: 0.9rem;
      line-height: 1.85;
      margin-bottom: 2rem;
    }

    .contact-links {
      display: flex;
      flex-direction: column;
      gap: 0.75rem;
    }

    .contact-link {
      display: flex;
      align-items: center;
      gap: 0.85rem;
      font-family: var(--mono);
      font-size: 0.8rem;
      color: var(--muted);
      text-decoration: none;
      padding: 0.75rem 1rem;
      border: 1px solid var(--border);
      border-radius: 8px;
      transition: all 0.25s;
    }

    .contact-link:hover {
      border-color: var(--blue);
      color: var(--blue);
      background: var(--blue-glow);
    }

    .contact-link .icon { font-size: 1.1rem; }

    .contact-form {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .field-wrap {
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
    }

    label {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--muted);
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }

    input, textarea {
      background: rgba(255,255,255,0.03);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 0.75rem 1rem;
      color: var(--text);
      font-family: var(--mono);
      font-size: 0.85rem;
      outline: none;
      transition: border-color 0.25s;
      resize: vertical;
    }

    input:focus, textarea:focus {
      border-color: var(--blue);
      background: rgba(26,127,255,0.04);
    }

    textarea { min-height: 120px; }

    /* ── FOOTER ── */
    footer {
      position: relative;
      z-index: 1;
      border-top: 1px solid var(--border);
      padding: 2rem 5%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .footer-left {
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--muted);
    }

    .footer-left span { color: var(--blue); }

    .footer-right {
      display: flex;
      gap: 1.25rem;
    }

    .footer-link {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--muted);
      text-decoration: none;
      text-transform: uppercase;
      letter-spacing: 0.1em;
      transition: color 0.25s;
    }

    .footer-link:hover { color: var(--blue); }

    /* ── FADE IN ANIMATION ── */
    .reveal {
      opacity: 0;
      transform: translateY(24px);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ── MOBILE MENU ── */
    .mobile-menu {
      display: none;
      position: fixed;
      inset: 0;
      z-index: 99;
      background: rgba(6,10,16,0.97);
      backdrop-filter: blur(20px);
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 2.5rem;
    }

    .mobile-menu.open { display: flex; }

    .mobile-menu a {
      font-family: var(--sans);
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--text);
      text-decoration: none;
      transition: color 0.25s;
    }

    .mobile-menu a:hover { color: var(--blue); }

    .close-btn {
      position: absolute;
      top: 1.25rem;
      right: 5%;
      background: none;
      border: none;
      color: var(--muted);
      font-size: 1.5rem;
      cursor: pointer;
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 800px) {
      .nav-links { display: none; }
      .hamburger { display: flex; }

      .hero-inner {
        grid-template-columns: 1fr;
        text-align: center;
      }

      .hero-cta { justify-content: center; }

      .profile-card { order: -1; }

      .avatar-wrap { width: 130px; height: 130px; }

      #about .about-grid,
      #contact .contact-grid {
        grid-template-columns: 1fr;
      }

      #skills .skills-grid {
        grid-template-columns: 1fr;
      }

      footer {
        flex-direction: column;
        text-align: center;
      }
    }
  </style>
</head>
<body>

<div class="grid-bg"></div>

<!-- NAVBAR -->
<nav>
  <div class="nav-logo"><span>ALFINO KAUSAR</span></div>
  <ul class="nav-links">
    <li><a href="#about">Tentang</a></li>
    <li><a href="#skills">Skill</a></li>
    <li><a href="#projects">Proyek</a></li>
    <li><a href="#contact">Kontak</a></li>
  </ul>
  <button class="hamburger" id="hamburger" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- MOBILE MENU -->
<div class="mobile-menu" id="mobileMenu">
  <button class="close-btn" id="closeMenu">✕</button>
  <a href="#about" class="nav-mobile">Tentang</a>
  <a href="#skills" class="nav-mobile">Skill</a>
  <a href="#projects" class="nav-mobile">Proyek</a>
  <a href="#contact" class="nav-mobile">Kontak</a>
</div>

<!-- HERO -->
<section id="hero">
  <div class="hero-inner">
    <div class="hero-content">
      <div class="hero-tag">Teknik Komputer & Jaringan</div>
      <h1>
        Halo, Saya<br/>
        <span class="accent">Alfino</span><br/>
        Kausar.
      </h1>
      <p class="hero-sub">
        Siswa TKJ yang bersemangat mempelajari dunia jaringan komputer — dari konfigurasi IP hingga routing Mikrotik. Siap berkontribusi di era digital.
      </p>
      <div class="hero-cta">
        <a href="#projects" class="btn btn-primary">▸ Lihat Proyek</a>
        <a href="#contact" class="btn btn-ghost">Hubungi Saya</a>
      </div>
    </div>

    <div class="profile-card">
      <div class="avatar-wrap">
        <div class="avatar-placeholder">👨‍💻</div>
      </div>
      <div class="status-badge">
        <span class="dot"></span>
        <span>Open to opportunity</span>
      </div>
    </div>
  </div>
</section>

<!-- TENTANG SAYA -->
<section id="about">
  <div class="section-label">01. Tentang</div>
  <h2>Tentang Saya</h2>
  <div class="about-grid reveal">
    <div class="about-text">
      <p>
        Saya adalah siswa <strong>Teknik Komputer dan Jaringan (TKJ)</strong> yang memiliki ketertarikan besar di bidang infrastruktur jaringan, administrasi sistem, dan troubleshooting. Saya menikmati setiap proses belajar, mulai dari menyusun kabel hingga mengkonfigurasi perangkat jaringan.
      </p>
      <p>
        Selain jaringan, saya juga belajar pengembangan web dasar dan tertarik mengombinasikan keduanya untuk membangun sistem monitoring jaringan berbasis web di masa depan.
      </p>
      <p>
        Saya percaya bahwa konektivitas yang handal adalah fondasi dari dunia digital yang kita gunakan setiap hari.
      </p>
    </div>
    <div class="info-list">
      <div class="info-item">
        <span class="info-key">Nama</span>
        <span class="info-val">Alfino Kausar</span>
      </div>
      <div class="info-item">
        <span class="info-key">Jurusan</span>
        <span class="info-val">Teknik Komputer & Jaringan</span>
      </div>
      <div class="info-item">
        <span class="info-key">Sekolah</span>
        <span class="info-val">SMKS Sansikta</span>
      </div>
      <div class="info-item">
        <span class="info-key">Kelas</span>
        <span class="info-val">XI TKJ 2</span>
      </div>
      <div class="info-item">
        <span class="info-key">Fokus</span>
        <span class="info-val">Network & Infrastructure</span>
      </div>
      <div class="info-item">
        <span class="info-key">Kota</span>
        <span class="info-val">BEKASI</span>
      </div>
    </div>
  </div>
</section>

<!-- SKILL -->
<section id="skills">
  <div class="section-label">02. Keahlian</div>
  <h2>Skill & Kompetensi</h2>
  <div class="skills-grid reveal" id="skillGrid">

    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">Konfigurasi IP Address</span>
        <span class="skill-pct">85%</span>
      </div>
      <div class="bar-track"><div class="bar-fill" data-pct="85"></div></div>
      <div class="skill-cat">// Network Fundamentals</div>
    </div>

    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">DHCP Server & Client</span>
        <span class="skill-pct">80%</span>
      </div>
      <div class="bar-track"><div class="bar-fill" data-pct="80"></div></div>
      <div class="skill-cat">// Network Services</div>
    </div>

    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">Troubleshooting Jaringan</span>
        <span class="skill-pct">78%</span>
      </div>
      <div class="bar-track"><div class="bar-fill" data-pct="78"></div></div>
      <div class="skill-cat">// Diagnostics</div>
    </div>

    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">Ping & Cek Koneksi</span>
        <span class="skill-pct">90%</span>
      </div>
      <div class="bar-track"><div class="bar-fill" data-pct="90"></div></div>
      <div class="skill-cat">// Network Tools</div>
    </div>

    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">Linux Dasar</span>
        <span class="skill-pct">65%</span>
      </div>
      <div class="bar-track"><div class="bar-fill" data-pct="65"></div></div>
      <div class="skill-cat">// Operating System</div>
    </div>

    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">Mikrotik Dasar</span>
        <span class="skill-pct">70%</span>
      </div>
      <div class="bar-track"><div class="bar-fill" data-pct="70"></div></div>
      <div class="skill-cat">// Routing & Switching</div>
    </div>

    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">HTML Dasar</span>
        <span class="skill-pct">72%</span>
      </div>
      <div class="bar-track"><div class="bar-fill" data-pct="72"></div></div>
      <div class="skill-cat">// Web Development</div>
    </div>

    <div class="skill-item">
      <div class="skill-header">
        <span class="skill-name">GitHub Pages</span>
        <span class="skill-pct">68%</span>
      </div>
      <div class="bar-track"><div class="bar-fill" data-pct="68"></div></div>
      <div class="skill-cat">// Deployment</div>
    </div>

  </div>
</section>

<!-- PROYEK / PENGALAMAN -->
<section id="projects">
  <div class="section-label">03. Proyek</div>
  <h2>Proyek & Pengalaman</h2>
  <div class="projects-grid reveal">

    <div class="project-card">
      <div class="project-icon">🌐</div>
      <div class="project-title">Konfigurasi Jaringan LAN Sekolah</div>
      <p class="project-desc">
        Membantu konfigurasi topologi jaringan LAN di laboratorium komputer sekolah, meliputi pengaturan IP statis, subnet mask, dan gateway untuk 30 komputer.
      </p>
      <div class="project-tags">
        <span class="tag">IP Address</span>
        <span class="tag">LAN</span>
        <span class="tag">Subnet</span>
      </div>
    </div>

    <div class="project-card">
      <div class="project-icon">🖥️</div>
      <div class="project-title">Instalasi DHCP Server Linux</div>
      <p class="project-desc">
        Praktik instalasi dan konfigurasi DHCP Server menggunakan Debian Linux di lingkungan virtual, memungkinkan distribusi IP otomatis ke klien.
      </p>
      <div class="project-tags">
        <span class="tag">DHCP</span>
        <span class="tag">Debian</span>
        <span class="tag">Linux</span>
      </div>
    </div>

    <div class="project-card">
      <div class="project-icon">📡</div>
      <div class="project-title">Routing Mikrotik RouterOS</div>
      <p class="project-desc">
        Melakukan konfigurasi dasar Mikrotik RouterOS menggunakan Winbox: NAT, DHCP Server, routing statis, dan pembatasan bandwidth untuk jaringan rumahan.
      </p>
      <div class="project-tags">
        <span class="tag">Mikrotik</span>
        <span class="tag">NAT</span>
        <span class="tag">Routing</span>
      </div>
    </div>

    <div class="project-card">
      <div class="project-icon">🔍</div>
      <div class="project-title">Troubleshooting Lab PKL</div>
      <p class="project-desc">
        Pengalaman PKL menangani gangguan jaringan: identifikasi masalah koneksi, penggantian kabel RJ-45, reset perangkat, dan konfigurasi ulang switch managed.
      </p>
      <div class="project-tags">
        <span class="tag">Troubleshooting</span>
        <span class="tag">PKL</span>
        <span class="tag">Switch</span>
      </div>
    </div>

    <div class="project-card">
      <div class="project-icon">🌍</div>
      <div class="project-title">Website Portfolio ini</div>
      <p class="project-desc">
        Membangun website portfolio personal menggunakan HTML, CSS, dan JavaScript murni, kemudian di-deploy melalui GitHub Pages sebagai project pertama di web.
      </p>
      <div class="project-tags">
        <span class="tag">HTML</span>
        <span class="tag">CSS</span>
        <span class="tag">GitHub Pages</span>
      </div>
    </div>

    <div class="project-card">
      <div class="project-icon">🔒</div>
      <div class="project-title">Keamanan Jaringan Dasar</div>
      <p class="project-desc">
        Mempelajari konsep dasar keamanan jaringan: firewall rules di Mikrotik, penggunaan password pada akses perangkat, dan pemantauan trafik jaringan sederhana.
      </p>
      <div class="project-tags">
        <span class="tag">Security</span>
        <span class="tag">Firewall</span>
        <span class="tag">Monitoring</span>
      </div>
    </div>

  </div>
</section>

<!-- KONTAK -->
<section id="contact">
  <div class="section-label">04. Kontak</div>
  <h2>Hubungi Saya</h2>
  <div class="contact-grid reveal">
    <div class="contact-info">
      <p>
        Tertarik berkolaborasi, berbagi ilmu, atau sekadar berdiskusi tentang jaringan? Jangan ragu untuk menghubungi saya melalui platform di bawah ini.
      </p>
      <div class="contact-links">
        <a href="mailto:alfinokausar2@gmail.com" class="contact-link">
          <span class="icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
              <rect x="2" y="4" width="20" height="16" rx="2"/>
              <path d="M2 7l10 7 10-7"/>
            </svg>
          </span>
          <span>alfinokausar2@gmail.com</span>
        </a>
        <a href="wa.me/+6281386966266" target="_blank" class="contact-link">
          <span class="icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
              <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51a12.8 12.8 0 0 0-.57-.01c-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 0 1-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 0 1-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 0 1 2.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0 0 12.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 0 0 5.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 0 0-3.48-8.413Z"/>
            </svg>
          </span>
          <span>whatsapp</span>
        </a>
        <a href="https://instagram.com/alvn.gt" target="_blank" class="contact-link">
          <span class="icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round">
              <rect x="2" y="2" width="20" height="20" rx="5" ry="5"/>
              <circle cx="12" cy="12" r="4"/>
              <circle cx="17.5" cy="6.5" r="0.5" fill="currentColor" stroke="none"/>
            </svg>
          </span>
          <span>@alvn.gt</span>
        </a>
      </div>
    </div>

<form action="https://formspree.io/f/xyzabcde" method="POST" class="contact-form">
  <div class="field-wrap">
    <label>Nama</label>
    <input type="text" name="name" placeholder="Nama kamu..."/>
  </div>
  <div class="field-wrap">
    <label>Email</label>
    <input type="email" name="email" placeholder="email@kamu.com"/>
  </div>
  <div class="field-wrap">
    <label>Pesan</label>
    <textarea name="message" placeholder="Tulis pesanmu di sini..."></textarea>
  </div>
  <button type="submit" class="btn btn-primary" style="align-self:flex-start;">▸ Kirim Pesan</button>
</form>

<!-- FOOTER -->
<footer>
  <div class="footer-left">
    © 2025 <span>ALFINO KAUSAR</span>
  </div>
  <div class="footer-right">
    <a href="#hero" class="footer-link">↑ Back to Top</a>
    <a href="#about" class="footer-link">About</a>
    <a href="#contact" class="footer-link">Contact</a>
  </div>
</footer>

<script>
  // ── HAMBURGER MENU ──
  const hamburger = document.getElementById('hamburger');
  const mobileMenu = document.getElementById('mobileMenu');
  const closeMenu = document.getElementById('closeMenu');

  hamburger.addEventListener('click', () => mobileMenu.classList.add('open'));
  closeMenu.addEventListener('click', () => mobileMenu.classList.remove('open'));

  document.querySelectorAll('.nav-mobile').forEach(link => {
    link.addEventListener('click', () => mobileMenu.classList.remove('open'));
  });

  // ── REVEAL ON SCROLL ──
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.12 });

  reveals.forEach(r => observer.observe(r));

  // ── SKILL PROGRESS BARS ──
  const skillGrid = document.getElementById('skillGrid');
  const barObserver = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        document.querySelectorAll('.bar-fill').forEach(bar => {
          const pct = bar.getAttribute('data-pct');
          setTimeout(() => { bar.style.width = pct + '%'; }, 200);
        });
        barObserver.unobserve(e.target);
      }
    });
  }, { threshold: 0.3 });

  if (skillGrid) barObserver.observe(skillGrid);

  // ── NAVBAR SCROLL STYLE ──
  const nav = document.querySelector('nav');
  window.addEventListener('scroll', () => {
    if (window.scrollY > 60) {
      nav.style.borderBottomColor = 'rgba(26,127,255,0.35)';
    } else {
      nav.style.borderBottomColor = 'rgba(26,127,255,0.2)';
    }
  });

  // ── CONTACT FORM ──
  function handleSubmit(e) {
    e.preventDefault();
    const btn = e.target.querySelector('button[type=submit]');
    btn.textContent = '✓ Pesan Terkirim!';
    btn.style.background = '#22c55e';
    btn.style.borderColor = '#22c55e';
    setTimeout(() => {
      btn.textContent = '▸ Kirim Pesan';
      btn.style.background = '';
      btn.style.borderColor = '';
      e.target.reset();
    }, 2500);
  }

  // ── STAGGERED REVEAL DELAY ──
  document.querySelectorAll('.skills-grid .skill-item, .projects-grid .project-card').forEach((el, i) => {
    el.style.transitionDelay = `${i * 0.06}s`;
    el.classList.add('reveal');
    observer.observe(el);
  });
</script>
</body>
</html>
