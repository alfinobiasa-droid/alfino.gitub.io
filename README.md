<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Alfino Kausar - TKJ Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Rajdhani:wght@400;500;600;700&family=Exo+2:wght@300;400;600;800&display=swap" rel="stylesheet">
<style>
  *{margin:0;padding:0;box-sizing:border-box}
  :root{
    --green:#00ff88;--green2:#00cc66;--blue:#00aaff;--dark:#0a0e1a;--dark2:#0f1628;
    --dark3:#141d35;--card:#111827;--border:rgba(0,255,136,0.2);--text:#e2e8f0;--muted:#64748b;
  }
  html{scroll-behavior:smooth}
  body{background:var(--dark);color:var(--text);font-family:'Exo 2',sans-serif;overflow-x:hidden}

  /* GRID BACKGROUND */
  body::before{
    content:'';position:fixed;inset:0;
    background-image:linear-gradient(rgba(0,255,136,0.03) 1px,transparent 1px),linear-gradient(90deg,rgba(0,255,136,0.03) 1px,transparent 1px);
    background-size:40px 40px;pointer-events:none;z-index:0
  }

  /* NAV */
  nav{
    position:fixed;top:0;left:0;right:0;z-index:100;
    background:rgba(10,14,26,0.9);backdrop-filter:blur(12px);
    border-bottom:1px solid var(--border);
    display:flex;align-items:center;justify-content:space-between;
    padding:0 2rem;height:60px
  }
  .nav-logo{font-family:'Share Tech Mono',monospace;color:var(--green);font-size:1rem;letter-spacing:2px}
  .nav-links{display:flex;gap:1.5rem}
  .nav-links a{
    color:var(--muted);text-decoration:none;font-size:0.8rem;letter-spacing:2px;
    font-family:'Share Tech Mono',monospace;text-transform:uppercase;
    transition:color 0.3s;padding:4px 0;border-bottom:1px solid transparent
  }
  .nav-links a:hover{color:var(--green);border-bottom-color:var(--green)}

  /* HERO */
  .hero{
    min-height:100vh;display:flex;align-items:center;justify-content:center;
    position:relative;z-index:1;padding:80px 2rem 2rem
  }
  .hero-content{text-align:center;max-width:800px}
  .hero-tag{
    display:inline-block;font-family:'Share Tech Mono',monospace;font-size:0.75rem;
    color:var(--green);border:1px solid var(--border);padding:6px 16px;
    border-radius:2px;letter-spacing:3px;margin-bottom:1.5rem;
    background:rgba(0,255,136,0.05)
  }
  .hero-name{
    font-family:'Rajdhani',sans-serif;font-size:clamp(3rem,8vw,6rem);
    font-weight:700;line-height:1;letter-spacing:-1px;
    color:#fff;text-transform:uppercase
  }
  .hero-name span{
    display:block;background:linear-gradient(135deg,var(--green),var(--blue));
    -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text
  }
  .hero-sub{
    font-size:1rem;color:var(--muted);margin:1.5rem 0 2.5rem;
    font-family:'Share Tech Mono',monospace;letter-spacing:2px
  }
  .hero-sub b{color:var(--green);font-weight:400}
  .hero-btns{display:flex;gap:1rem;justify-content:center;flex-wrap:wrap}
  .btn-primary{
    background:var(--green);color:var(--dark);font-weight:700;
    padding:12px 28px;border:none;font-family:'Rajdhani',sans-serif;
    font-size:0.95rem;letter-spacing:2px;text-transform:uppercase;
    cursor:pointer;clip-path:polygon(8px 0%,100% 0%,calc(100% - 8px) 100%,0% 100%);
    transition:all 0.3s
  }
  .btn-primary:hover{background:#fff;transform:translateY(-2px)}
  .btn-outline{
    background:transparent;color:var(--green);font-weight:600;
    padding:12px 28px;border:1px solid var(--green);
    font-family:'Rajdhani',sans-serif;font-size:0.95rem;
    letter-spacing:2px;text-transform:uppercase;cursor:pointer;
    clip-path:polygon(8px 0%,100% 0%,calc(100% - 8px) 100%,0% 100%);
    transition:all 0.3s
  }
  .btn-outline:hover{background:rgba(0,255,136,0.1);transform:translateY(-2px)}

  /* STATS ROW */
  .stats{
    display:flex;justify-content:center;gap:3rem;margin-top:3rem;
    flex-wrap:wrap
  }
  .stat{text-align:center}
  .stat-num{
    font-family:'Rajdhani',sans-serif;font-size:2.5rem;font-weight:700;
    background:linear-gradient(135deg,var(--green),var(--blue));
    -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text
  }
  .stat-label{font-family:'Share Tech Mono',monospace;font-size:0.65rem;color:var(--muted);letter-spacing:2px;margin-top:4px}

  /* SECTIONS */
  section{position:relative;z-index:1;padding:5rem 2rem}
  .container{max-width:1100px;margin:0 auto}
  .section-header{text-align:center;margin-bottom:3.5rem}
  .section-tag{
    display:inline-block;font-family:'Share Tech Mono',monospace;font-size:0.7rem;
    color:var(--blue);letter-spacing:3px;text-transform:uppercase;margin-bottom:0.75rem
  }
  .section-title{
    font-family:'Rajdhani',sans-serif;font-size:clamp(2rem,4vw,2.8rem);
    font-weight:700;text-transform:uppercase;color:#fff
  }
  .section-line{
    width:60px;height:2px;background:linear-gradient(90deg,var(--green),var(--blue));
    margin:1rem auto 0
  }

  /* ABOUT */
  .about-grid{display:grid;grid-template-columns:1fr 1fr;gap:2rem;align-items:center}
  .about-card{
    background:var(--card);border:1px solid var(--border);
    padding:2rem;position:relative;overflow:hidden
  }
  .about-card::before{
    content:'';position:absolute;top:0;left:0;right:0;height:2px;
    background:linear-gradient(90deg,var(--green),var(--blue))
  }
  .about-label{font-family:'Share Tech Mono',monospace;font-size:0.65rem;color:var(--green);letter-spacing:3px;margin-bottom:1rem}
  .about-text{color:#94a3b8;line-height:1.8;font-size:0.9rem}
  .info-list{list-style:none}
  .info-list li{
    display:flex;align-items:center;gap:0.75rem;padding:0.6rem 0;
    border-bottom:1px solid rgba(255,255,255,0.05);font-size:0.85rem;color:#94a3b8
  }
  .info-list li span:first-child{color:var(--green);font-family:'Share Tech Mono',monospace;font-size:0.7rem;min-width:80px}

  /* SKILLS */
  .skills-grid{display:grid;grid-template-columns:1fr 1fr;gap:2rem}
  .skill-card{
    background:var(--card);border:1px solid var(--border);padding:2rem;
    position:relative;overflow:hidden;transition:transform 0.3s,border-color 0.3s
  }
  .skill-card:hover{transform:translateY(-4px);border-color:rgba(0,255,136,0.5)}
  .skill-card::after{
    content:'';position:absolute;bottom:0;left:0;right:0;height:1px;
    background:linear-gradient(90deg,transparent,var(--green),transparent)
  }
  .skill-icon{
    width:44px;height:44px;background:rgba(0,255,136,0.1);
    border:1px solid var(--border);display:flex;align-items:center;justify-content:center;
    font-size:1.2rem;margin-bottom:1rem
  }
  .skill-type{font-family:'Share Tech Mono',monospace;font-size:0.65rem;color:var(--green);letter-spacing:3px;margin-bottom:0.5rem}
  .skill-title{font-family:'Rajdhani',sans-serif;font-size:1.4rem;font-weight:700;color:#fff;margin-bottom:1rem}
  .skill-items{display:flex;flex-direction:column;gap:0.75rem}
  .skill-item{display:flex;flex-direction:column;gap:4px}
  .skill-name{font-size:0.8rem;color:#94a3b8;display:flex;justify-content:space-between}
  .skill-name span:last-child{color:var(--green);font-family:'Share Tech Mono',monospace;font-size:0.7rem}
  .skill-bar{height:3px;background:rgba(255,255,255,0.05);position:relative}
  .skill-fill{height:100%;background:linear-gradient(90deg,var(--green),var(--blue));width:0%;transition:width 1.5s ease}
  .soft-tag{
    display:inline-block;padding:5px 12px;border:1px solid var(--border);
    font-size:0.75rem;color:var(--text);background:rgba(0,255,136,0.05);
    margin:4px;font-family:'Share Tech Mono',monospace;letter-spacing:1px
  }

  /* CERT / HIGHLIGHT */
  .highlight-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.5rem}
  .highlight-card{
    background:var(--card);border:1px solid var(--border);
    padding:1.75rem;text-align:center;transition:all 0.3s;position:relative
  }
  .highlight-card:hover{border-color:rgba(0,170,255,0.5);transform:translateY(-4px)}
  .h-icon{font-size:2rem;margin-bottom:1rem}
  .h-title{font-family:'Rajdhani',sans-serif;font-size:1.1rem;font-weight:700;color:#fff;margin-bottom:0.5rem}
  .h-desc{font-size:0.8rem;color:var(--muted);line-height:1.6}
  .h-badge{
    display:inline-block;margin-top:0.75rem;padding:3px 10px;
    background:rgba(0,170,255,0.1);border:1px solid rgba(0,170,255,0.3);
    font-size:0.65rem;color:var(--blue);font-family:'Share Tech Mono',monospace;letter-spacing:2px
  }

  /* CONTACT */
  .contact-wrap{
    background:var(--card);border:1px solid var(--border);
    padding:3rem;text-align:center;position:relative;overflow:hidden
  }
  .contact-wrap::before{
    content:'';position:absolute;top:0;left:0;right:0;height:3px;
    background:linear-gradient(90deg,var(--green),var(--blue),var(--green))
  }
  .contact-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.5rem;margin-top:2rem}
  .contact-item{
    padding:1.5rem;border:1px solid rgba(255,255,255,0.05);
    transition:border-color 0.3s
  }
  .contact-item:hover{border-color:var(--border)}
  .contact-item-icon{font-size:1.5rem;margin-bottom:0.5rem}
  .contact-item-label{font-family:'Share Tech Mono',monospace;font-size:0.65rem;color:var(--muted);letter-spacing:2px;margin-bottom:0.25rem}
  .contact-item-val{font-size:0.85rem;color:var(--text)}

  /* FOOTER */
  footer{
    border-top:1px solid var(--border);padding:1.5rem 2rem;
    text-align:center;font-family:'Share Tech Mono',monospace;
    font-size:0.65rem;color:var(--muted);letter-spacing:2px;
    position:relative;z-index:1
  }
  footer span{color:var(--green)}

  /* TERMINAL LINE */
  .terminal{
    display:inline-flex;align-items:center;gap:8px;
    font-family:'Share Tech Mono',monospace;font-size:0.75rem;
    color:var(--muted);margin-bottom:1rem
  }
  .terminal::before{content:'>';color:var(--green);font-size:0.9rem}
  .cursor{display:inline-block;width:8px;height:14px;background:var(--green);animation:blink 1s infinite}
  @keyframes blink{0%,50%{opacity:1}51%,100%{opacity:0}}

  /* DECORATIVE */
  .deco-circle{
    position:absolute;border-radius:50%;filter:blur(80px);pointer-events:none;z-index:0
  }

  @media(max-width:700px){
    .about-grid,.skills-grid,.highlight-grid,.contact-grid{grid-template-columns:1fr}
    nav{padding:0 1rem}.nav-links{display:none}
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">AK.TKJ</div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#highlights">Highlights</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-content">
    <div class="terminal">Initializing portfolio system... <span class="cursor"></span></div>
    <div class="hero-tag">&#x2022; TEKNIK KOMPUTER & JARINGAN &#x2022;</div>
    <h1 class="hero-name">
      Alfino
      <span>Kausar</span>
    </h1>
    <p class="hero-sub">Network Technician &nbsp;/&nbsp; <b>Linux Enthusiast</b> &nbsp;/&nbsp; Cisco Student</p>
    <div class="hero-btns">
      <button class="btn-primary" onclick="document.getElementById('skills').scrollIntoView({behavior:'smooth'})">Lihat Skill</button>
      <button class="btn-outline" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">Hubungi Saya</button>
    </div>
    <div class="stats">
      <div class="stat"><div class="stat-num">7+</div><div class="stat-label">Hard Skills</div></div>
      <div class="stat"><div class="stat-num">3+</div><div class="stat-label">Soft Skills</div></div>
      <div class="stat"><div class="stat-num">TKJ</div><div class="stat-label">Jurusan</div></div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about" style="background:var(--dark2)">
  <div class="container">
    <div class="section-header">
      <div class="section-tag">// 01. profile</div>
      <h2 class="section-title">Tentang Saya</h2>
      <div class="section-line"></div>
    </div>
    <div class="about-grid">
      <div class="about-card">
        <div class="about-label">// BIOGRAPHY</div>
        <p class="about-text">
          Halo! Saya <strong style="color:#fff">Alfino Kausar</strong>, seorang siswa Teknik Komputer dan Jaringan (TKJ) yang memiliki passion di bidang networking, konfigurasi sistem, dan infrastruktur jaringan komputer.
        </p>
        <br>
        <p class="about-text">
          Dengan kemampuan teknis yang terus berkembang, saya siap menghadapi tantangan dunia kerja di bidang IT, terutama dalam instalasi dan konfigurasi jaringan berbasis LAN, Linux, maupun perangkat Cisco dan Mikrotik.
        </p>
      </div>
      <div class="about-card">
        <div class="about-label">// INFO</div>
        <ul class="info-list">
          <li><span>Nama</span><span>Alfino Kausar</span></li>
          <li><span>Jurusan</span><span>Teknik Komputer & Jaringan</span></li>
          <li><span>Fokus</span><span>Networking & Infrastructure</span></li>
          <li><span>OS</span><span>Linux / Windows Server</span></li>
          <li><span>Tools</span><span>Cisco Packet Tracer, Winbox</span></li>
          <li><span>Status</span><span style="color:var(--green)">&#x25cf; Available for Work</span></li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="container">
    <div class="section-header">
      <div class="section-tag">// 02. skills</div>
      <h2 class="section-title">Keahlian</h2>
      <div class="section-line"></div>
    </div>
    <div class="skills-grid">
      <!-- HARD SKILLS -->
      <div class="skill-card">
        <div class="skill-icon">⚙️</div>
        <div class="skill-type">// HARD SKILLS</div>
        <div class="skill-title">Technical Expertise</div>
        <div class="skill-items">
          <div class="skill-item">
            <div class="skill-name"><span>Instalasi Jaringan LAN</span><span>90%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="90"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name"><span>Konfigurasi IP Address</span><span>85%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="85"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name"><span>Crimping Straight / Cross</span><span>95%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="95"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name"><span>Dasar Mikrotik</span><span>75%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="75"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name"><span>Instalasi OS Linux</span><span>80%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="80"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name"><span>Dasar Cisco (Packet Tracer)</span><span>72%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="72"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name"><span>Troubleshooting Jaringan</span><span>78%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="78"></div></div>
          </div>
        </div>
      </div>

      <!-- SOFT SKILLS -->
      <div class="skill-card">
        <div class="skill-icon">🤝</div>
        <div class="skill-type">// SOFT SKILLS</div>
        <div class="skill-title">Interpersonal Skills</div>
        <div class="skill-items">
          <div class="skill-item">
            <div class="skill-name"><span>Kerja Sama Tim</span><span>92%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="92"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name"><span>Disiplin</span><span>88%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="88"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name"><span>Bertanggung Jawab</span><span>90%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="90"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name"><span>Problem Solving</span><span>80%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="80"></div></div>
          </div>
          <div class="skill-item">
            <div class="skill-name"><span>Komunikasi</span><span>82%</span></div>
            <div class="skill-bar"><div class="skill-fill" data-width="82"></div></div>
          </div>
        </div>
        <br>
        <div>
          <span class="soft-tag">Teamwork</span>
          <span class="soft-tag">Discipline</span>
          <span class="soft-tag">Responsible</span>
          <span class="soft-tag">Adaptable</span>
          <span class="soft-tag">Detail-oriented</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- HIGHLIGHTS -->
<section id="highlights" style="background:var(--dark2)">
  <div class="container">
    <div class="section-header">
      <div class="section-tag">// 03. highlights</div>
      <h2 class="section-title">Keunggulan & Bidang</h2>
      <div class="section-line"></div>
    </div>
    <div class="highlight-grid">
      <div class="highlight-card">
        <div class="h-icon">🔌</div>
        <div class="h-title">Network Infrastructure</div>
        <div class="h-desc">Mampu melakukan instalasi jaringan LAN dari awal, mulai dari perencanaan topologi hingga konfigurasi perangkat aktif.</div>
        <div class="h-badge">LAN / WAN</div>
      </div>
      <div class="highlight-card">
        <div class="h-icon">🐧</div>
        <div class="h-title">Linux System</div>
        <div class="h-desc">Berpengalaman dalam instalasi berbagai distro Linux, konfigurasi dasar, manajemen paket, dan penggunaan terminal.</div>
        <div class="h-badge">Ubuntu / Debian</div>
      </div>
      <div class="highlight-card">
        <div class="h-icon">🌐</div>
        <div class="h-title">Cisco Networking</div>
        <div class="h-desc">Memahami konsep routing, switching, dan konfigurasi dasar perangkat Cisco menggunakan Packet Tracer.</div>
        <div class="h-badge">CCNA Fundamental</div>
      </div>
      <div class="highlight-card">
        <div class="h-icon">🔧</div>
        <div class="h-title">Mikrotik Router</div>
        <div class="h-desc">Menguasai konfigurasi dasar Mikrotik seperti DHCP Server, firewall rules, dan manajemen bandwidth via Winbox.</div>
        <div class="h-badge">RouterOS</div>
      </div>
      <div class="highlight-card">
        <div class="h-icon">🔩</div>
        <div class="h-title">Cable Crimping</div>
        <div class="h-desc">Terampil dalam proses crimping kabel UTP standar TIA/EIA-568B untuk kabel straight-through maupun crossover.</div>
        <div class="h-badge">Cat5e / Cat6</div>
      </div>
      <div class="highlight-card">
        <div class="h-icon">🛠️</div>
        <div class="h-title">Troubleshooting</div>
        <div class="h-desc">Mampu mengidentifikasi dan menyelesaikan masalah koneksi jaringan secara sistematis dan efisien.</div>
        <div class="h-badge">Network Support</div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="container">
    <div class="section-header">
      <div class="section-tag">// 04. contact</div>
      <h2 class="section-title">Hubungi Saya</h2>
      <div class="section-line"></div>
    </div>
    <div class="contact-wrap">
      <div class="terminal">Ready to connect... <span class="cursor"></span></div>
      <p style="color:var(--muted);font-size:0.9rem;margin-top:0.5rem">Tertarik bekerja sama atau punya pertanyaan? Jangan ragu untuk menghubungi saya!</p>
      <div class="contact-grid">
        <div class="contact-item">
          <div class="contact-item-icon">📧</div>
          <div class="contact-item-label">EMAIL</div>
          <div class="contact-item-val">alfinokausar@email.com</div>
        </div>
        <div class="contact-item">
          <div class="contact-item-icon">📱</div>
          <div class="contact-item-label">WHATSAPP</div>
          <div class="contact-item-val">+62 8xx-xxxx-xxxx</div>
        </div>
        <div class="contact-item">
          <div class="contact-item-icon">🏫</div>
          <div class="contact-item-label">SEKOLAH</div>
          <div class="contact-item-val">Jurusan TKJ — SMK</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <span>Alfino Kausar</span> &nbsp;&#x25cf;&nbsp; TKJ Portfolio &nbsp;&#x25cf;&nbsp; Built with passion for networking
</footer>

<script>
  const fills = document.querySelectorAll('.skill-fill');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if(e.isIntersecting){
        const w = e.target.getAttribute('data-width');
        e.target.style.width = w + '%';
      }
    });
  },{threshold:0.3});
  fills.forEach(f => observer.observe(f));
</script>
</body>
</html>
