<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>George Josy — LIMS Integration Specialist</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Mono:wght@300;400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --cream: #F5F0E8;
    --ink: #1A1714;
    --gold: #C9A84C;
    --gold-light: #E8D5A3;
    --rust: #8B4A2F;
    --slate: #3D3A35;
    --muted: #7A756E;
    --rule: #D4C9B5;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--cream);
    color: var(--ink);
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* NOISE TEXTURE OVERLAY */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1000;
    opacity: 0.4;
  }

  /* HEADER */
  header {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
    overflow: hidden;
  }

  .header-left {
    padding: 80px 60px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: relative;
    z-index: 2;
  }

  .header-right {
    background: var(--ink);
    position: relative;
    overflow: hidden;
    display: flex;
    align-items: flex-end;
    padding: 60px;
  }

  .header-right::before {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      45deg,
      transparent,
      transparent 30px,
      rgba(201, 168, 76, 0.04) 30px,
      rgba(201, 168, 76, 0.04) 31px
    );
  }

  .header-right .big-initial {
    font-family: 'Playfair Display', serif;
    font-size: clamp(200px, 25vw, 380px);
    line-height: 0.8;
    color: transparent;
    -webkit-text-stroke: 1px rgba(201, 168, 76, 0.3);
    position: absolute;
    right: -30px;
    bottom: -20px;
    user-select: none;
    animation: fadeInRight 1.2s ease forwards;
    opacity: 0;
    animation-delay: 0.4s;
  }

  .eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 12px;
    animation: fadeInUp 0.8s ease forwards;
    opacity: 0;
  }

  .eyebrow::before {
    content: '';
    width: 40px;
    height: 1px;
    background: var(--gold);
  }

  h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(42px, 5vw, 72px);
    line-height: 1.05;
    font-weight: 700;
    margin-bottom: 8px;
    animation: fadeInUp 0.8s ease 0.15s forwards;
    opacity: 0;
  }

  h1 em {
    font-style: italic;
    color: var(--rust);
  }

  .tagline {
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    color: var(--muted);
    margin-bottom: 40px;
    letter-spacing: 0.05em;
    animation: fadeInUp 0.8s ease 0.25s forwards;
    opacity: 0;
  }

  .header-desc {
    font-size: 16px;
    max-width: 420px;
    color: var(--slate);
    margin-bottom: 48px;
    animation: fadeInUp 0.8s ease 0.35s forwards;
    opacity: 0;
  }

  .header-meta {
    display: flex;
    flex-direction: column;
    gap: 8px;
    animation: fadeInUp 0.8s ease 0.45s forwards;
    opacity: 0;
  }

  .meta-item {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }

  .meta-dot {
    width: 5px;
    height: 5px;
    border-radius: 50%;
    background: var(--gold);
  }

  .right-caption {
    position: relative;
    z-index: 2;
    animation: fadeInUp 1s ease 0.6s forwards;
    opacity: 0;
  }

  .right-caption p {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: rgba(245, 240, 232, 0.4);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    writing-mode: vertical-rl;
    text-orientation: mixed;
    transform: rotate(180deg);
  }

  /* DIVIDER */
  .section-rule {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--rule), transparent);
    margin: 0 60px;
  }

  /* SECTIONS */
  section {
    padding: 100px 60px;
    max-width: 1200px;
    margin: 0 auto;
  }

  .section-header {
    display: flex;
    align-items: baseline;
    gap: 20px;
    margin-bottom: 60px;
  }

  .section-num {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--gold);
    letter-spacing: 0.2em;
  }

  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(28px, 3vw, 40px);
    font-weight: 400;
  }

  /* STACK */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
    gap: 12px;
  }

  .stack-item {
    border: 1px solid var(--rule);
    padding: 14px 18px;
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: var(--slate);
    letter-spacing: 0.05em;
    transition: all 0.25s ease;
    cursor: default;
    position: relative;
    overflow: hidden;
  }

  .stack-item::before {
    content: '';
    position: absolute;
    inset: 0;
    background: var(--ink);
    transform: translateY(100%);
    transition: transform 0.25s ease;
  }

  .stack-item:hover::before { transform: translateY(0); }
  .stack-item:hover { color: var(--gold); border-color: var(--ink); }
  .stack-item span { position: relative; z-index: 1; }

  /* PROJECTS */
  .project-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
  }

  .project-card {
    background: var(--ink);
    padding: 48px 40px;
    position: relative;
    overflow: hidden;
    cursor: default;
    transition: transform 0.3s ease;
  }

  .project-card:hover { transform: translateY(-4px); }

  .project-card::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--gold), var(--rust));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
  }

  .project-card:hover::after { transform: scaleX(1); }

  .project-num {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: rgba(201, 168, 76, 0.5);
    letter-spacing: 0.2em;
    margin-bottom: 32px;
  }

  .project-title {
    font-family: 'Playfair Display', serif;
    font-size: 22px;
    color: var(--cream);
    margin-bottom: 16px;
    font-weight: 400;
  }

  .project-desc {
    font-size: 14px;
    color: rgba(245, 240, 232, 0.5);
    line-height: 1.7;
    margin-bottom: 32px;
  }

  .project-stats {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .stat {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--gold);
    letter-spacing: 0.1em;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .stat::before {
    content: '↑';
    font-size: 10px;
  }

  .project-tech {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-top: 20px;
  }

  .tech-tag {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: rgba(245, 240, 232, 0.35);
    border: 1px solid rgba(245, 240, 232, 0.1);
    padding: 3px 8px;
    letter-spacing: 0.08em;
  }

  /* ABOUT / DOING */
  .doing-list {
    list-style: none;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0;
  }

  .doing-item {
    padding: 28px 0;
    border-bottom: 1px solid var(--rule);
    display: grid;
    grid-template-columns: 24px 1fr;
    gap: 16px;
    align-items: start;
  }

  .doing-item:nth-child(odd) { padding-right: 60px; }
  .doing-item:nth-child(even) { padding-left: 60px; border-left: 1px solid var(--rule); }

  .doing-num {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: var(--gold);
    padding-top: 4px;
  }

  .doing-text {
    font-size: 16px;
    color: var(--slate);
  }

  /* EDUCATION & LEADERSHIP */
  .two-col {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
  }

  .col-title {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 32px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .col-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--rule);
  }

  .edu-block {
    margin-bottom: 24px;
  }

  .edu-title {
    font-family: 'Playfair Display', serif;
    font-size: 20px;
    margin-bottom: 4px;
  }

  .edu-sub {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: var(--muted);
  }

  .leadership-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 14px;
  }

  .leadership-list li {
    font-size: 15px;
    color: var(--slate);
    padding-left: 18px;
    position: relative;
  }

  .leadership-list li::before {
    content: '—';
    position: absolute;
    left: 0;
    color: var(--gold);
    font-family: 'DM Mono', monospace;
  }

  /* CONTACT FOOTER */
  footer {
    background: var(--ink);
    padding: 100px 60px;
    position: relative;
    overflow: hidden;
  }

  footer::before {
    content: 'CONNECT';
    font-family: 'Playfair Display', serif;
    font-size: clamp(80px, 15vw, 200px);
    color: transparent;
    -webkit-text-stroke: 1px rgba(201, 168, 76, 0.08);
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    white-space: nowrap;
    pointer-events: none;
    user-select: none;
  }

  .footer-inner {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    position: relative;
    z-index: 2;
  }

  .footer-left h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(36px, 4vw, 60px);
    color: var(--cream);
    font-weight: 400;
    margin-bottom: 8px;
  }

  .footer-left h2 em {
    font-style: italic;
    color: var(--gold);
  }

  .footer-left p {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: rgba(245, 240, 232, 0.4);
    letter-spacing: 0.1em;
  }

  .footer-links {
    display: flex;
    flex-direction: column;
    gap: 20px;
    align-items: flex-end;
  }

  .footer-link {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: rgba(245, 240, 232, 0.5);
    text-decoration: none;
    letter-spacing: 0.1em;
    display: flex;
    align-items: center;
    gap: 12px;
    transition: color 0.2s ease;
  }

  .footer-link:hover { color: var(--gold); }

  .footer-link::after {
    content: '→';
    color: var(--gold);
    opacity: 0;
    transition: opacity 0.2s ease;
  }

  .footer-link:hover::after { opacity: 1; }

  .footer-bottom {
    max-width: 1200px;
    margin: 60px auto 0;
    padding-top: 40px;
    border-top: 1px solid rgba(245, 240, 232, 0.1);
    display: flex;
    justify-content: space-between;
    position: relative;
    z-index: 2;
  }

  .footer-bottom span {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: rgba(245, 240, 232, 0.2);
    letter-spacing: 0.1em;
  }

  /* ANIMATIONS */
  @keyframes fadeInUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeInRight {
    from { opacity: 0; transform: translateX(40px); }
    to { opacity: 1; transform: translateX(0); }
  }

  /* Scroll reveal */
  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }

  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* RESPONSIVE */
  @media (max-width: 900px) {
    header { grid-template-columns: 1fr; }
    .header-right { display: none; }
    section { padding: 70px 30px; }
    .header-left { padding: 60px 30px; }
    .project-grid { grid-template-columns: 1fr; }
    .doing-list { grid-template-columns: 1fr; }
    .doing-item:nth-child(even) { padding-left: 0; border-left: none; }
    .two-col { grid-template-columns: 1fr; gap: 50px; }
    .footer-inner { flex-direction: column; gap: 50px; align-items: flex-start; }
    .footer-links { align-items: flex-start; }
    footer { padding: 70px 30px; }
    .section-rule { margin: 0 30px; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<header>
  <div class="header-left">
    <div class="eyebrow">Software Developer</div>
    <h1>George<br><em>Josy</em></h1>
    <p class="tagline">LIMS Integration Specialist · Kerala, India</p>
    <p class="header-desc">
      I make machines talk to software — without drama. Building real-time laboratory integration systems using .NET, connecting the physical world to the digital one.
    </p>
    <div class="header-meta">
      <div class="meta-item"><span class="meta-dot"></span>TCP/IP & RS232 Communication</div>
      <div class="meta-item"><span class="meta-dot"></span>HL7 & ASTM Data Processing</div>
      <div class="meta-item"><span class="meta-dot"></span>georgejosy23@gmail.com</div>
    </div>
  </div>
  <div class="header-right">
    <div class="big-initial">G</div>
    <div class="right-caption">
      <p>Machine Integration · Real-World Systems</p>
    </div>
  </div>
</header>

<div class="section-rule"></div>

<!-- WHAT I'M DOING -->
<section>
  <div class="section-header reveal">
    <span class="section-num">01</span>
    <h2 class="section-title">Current Focus</h2>
  </div>
  <ul class="doing-list">
    <li class="doing-item reveal">
      <span class="doing-num">01</span>
      <span class="doing-text">Building machine-to-LIMS integration systems for real-time lab automation</span>
    </li>
    <li class="doing-item reveal" style="transition-delay:0.1s">
      <span class="doing-num">02</span>
      <span class="doing-text">Deepening backend development skills and system architecture patterns</span>
    </li>
    <li class="doing-item reveal" style="transition-delay:0.15s">
      <span class="doing-num">03</span>
      <span class="doing-text">Exploring scalable application architecture for enterprise systems</span>
    </li>
    <li class="doing-item reveal" style="transition-delay:0.2s">
      <span class="doing-num">04</span>
      <span class="doing-text">Preparing for global tech opportunities and expanding professional reach</span>
    </li>
  </ul>
</section>

<div class="section-rule"></div>

<!-- PROJECTS -->
<section>
  <div class="section-header reveal">
    <span class="section-num">02</span>
    <h2 class="section-title">Selected Work</h2>
  </div>
  <div class="project-grid reveal">
    <div class="project-card">
      <div class="project-num">Project 01</div>
      <div class="project-title">Machine Integration Application</div>
      <div class="project-desc">
        A Windows-based integration system bridging laboratory equipment with LIMS software, eliminating manual data entry at scale.
      </div>
      <div class="project-stats">
        <div class="stat">75% reduction in manual lab entry</div>
        <div class="stat">30% improvement in turnaround time</div>
      </div>
      <div class="project-tech">
        <span class="tech-tag">C#</span>
        <span class="tech-tag">.NET</span>
        <span class="tech-tag">TCP/IP</span>
        <span class="tech-tag">RS232</span>
        <span class="tech-tag">HL7/ASTM</span>
      </div>
    </div>
    <div class="project-card">
      <div class="project-num">Project 02</div>
      <div class="project-title">Smart Flow</div>
      <div class="project-desc">
        An intelligent traffic management system using computer vision to dynamically optimize signal timing and urban traffic flow.
      </div>
      <div class="project-tech">
        <span class="tech-tag">Python</span>
        <span class="tech-tag">YOLOv4</span>
        <span class="tech-tag">OpenCV</span>
        <span class="tech-tag">ML</span>
      </div>
    </div>
    <div class="project-card">
      <div class="project-num">Project 03</div>
      <div class="project-title">CRM VISAT</div>
      <div class="project-desc">
        A comprehensive college reception management system streamlining visitor and administrative workflows across the campus.
      </div>
      <div class="project-tech">
        <span class="tech-tag">Flutter</span>
        <span class="tech-tag">Firebase</span>
        <span class="tech-tag">Dart</span>
      </div>
    </div>
  </div>
</section>

<div class="section-rule"></div>

<!-- TECH STACK -->
<section>
  <div class="section-header reveal">
    <span class="section-num">03</span>
    <h2 class="section-title">Tech Stack</h2>
  </div>
  <div class="stack-grid reveal">
    <div class="stack-item"><span>C#</span></div>
    <div class="stack-item"><span>C / C++</span></div>
    <div class="stack-item"><span>Java</span></div>
    <div class="stack-item"><span>Python</span></div>
    <div class="stack-item"><span>JavaScript</span></div>
    <div class="stack-item"><span>SQL</span></div>
    <div class="stack-item"><span>.NET</span></div>
    <div class="stack-item"><span>REST APIs</span></div>
    <div class="stack-item"><span>MySQL</span></div>
    <div class="stack-item"><span>Oracle</span></div>
    <div class="stack-item"><span>Git / GitHub</span></div>
    <div class="stack-item"><span>Postman</span></div>
    <div class="stack-item"><span>Bootstrap</span></div>
    <div class="stack-item"><span>Visual Studio</span></div>
  </div>
</section>

<div class="section-rule"></div>

<!-- EDUCATION & LEADERSHIP -->
<section>
  <div class="section-header reveal">
    <span class="section-num">04</span>
    <h2 class="section-title">Education & Leadership</h2>
  </div>
  <div class="two-col">
    <div class="reveal">
      <div class="col-title">Education</div>
      <div class="edu-block">
        <div class="edu-title">B.Tech in Computer Science & Engineering</div>
        <div class="edu-sub">Graduating with a foundation in systems, networks & software engineering</div>
      </div>
    </div>
    <div class="reveal" style="transition-delay:0.15s">
      <div class="col-title">Leadership</div>
      <ul class="leadership-list">
        <li>CEO, IEDC VISAT</li>
        <li>Google Crowdsource Volunteer</li>
        <li>IQAC Student Coordinator</li>
        <li>Anti-Ragging Committee Member</li>
      </ul>
    </div>
  </div>
</section>

<!-- FOOTER / CONTACT -->
<footer>
  <div class="footer-inner">
    <div class="footer-left">
      <h2>Let's build<br>something <em>real.</em></h2>
      <p>Open to global opportunities · Kerala, India</p>
    </div>
    <div class="footer-links">
      <a href="mailto:georgejosy23@gmail.com" class="footer-link">georgejosy23@gmail.com</a>
      <a href="https://www.linkedin.com/in/georgejosy" target="_blank" class="footer-link">linkedin.com/in/georgejosy</a>
    </div>
  </div>
  <div class="footer-bottom">
    <span>George Josy · LIMS Integration Specialist</span>
    <span>Kerala, India · 2025</span>
  </div>
</footer>

<script>
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
      }
    });
  }, { threshold: 0.12 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
</script>
</body>
</html>
