<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>B.M. Rafin Rahman — ECE & ML Enthusiast</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  :root {
    --emerald: #10b981;
    --purple: #8b5cf6;
    --bg: #050d0a;
    --surface: #0a1a12;
    --surface2: #0f2218;
    --border: #1a3a28;
    --text: #d1fae5;
    --muted: #6b7c74;
    --white: #f0fdf4;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-size: 15px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── NOISE OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
    opacity: .5;
  }

  /* ── GRID BACKGROUND ── */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(16,185,129,.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(16,185,129,.04) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  main { position: relative; z-index: 1; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 80px 24px 60px;
    position: relative;
  }

  .hero-glow {
    position: absolute;
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(16,185,129,.15) 0%, transparent 70%);
    top: 50%; left: 50%;
    transform: translate(-50%, -55%);
    pointer-events: none;
  }

  .hero-glow2 {
    position: absolute;
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(139,92,246,.1) 0%, transparent 70%);
    top: 30%; right: 10%;
    pointer-events: none;
  }

  .badge-row {
    display: flex; gap: 10px; flex-wrap: wrap; justify-content: center;
    margin-bottom: 28px;
    animation: fadeUp .6s ease both;
  }

  .badge {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    padding: 5px 14px;
    border-radius: 20px;
    border: 1px solid var(--border);
    background: rgba(16,185,129,.06);
    color: var(--emerald);
    letter-spacing: .04em;
  }

  .hero h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(42px, 7vw, 80px);
    font-weight: 800;
    line-height: 1.05;
    background: linear-gradient(135deg, var(--white) 30%, var(--emerald) 70%, var(--purple) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 16px;
    animation: fadeUp .6s .1s ease both;
  }

  .hero .subtitle {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--emerald);
    letter-spacing: .12em;
    text-transform: uppercase;
    margin-bottom: 20px;
    animation: fadeUp .6s .2s ease both;
  }

  .hero p {
    max-width: 540px;
    color: var(--muted);
    font-size: 15px;
    margin-bottom: 36px;
    animation: fadeUp .6s .3s ease both;
  }

  .social-row {
    display: flex; gap: 12px; flex-wrap: wrap; justify-content: center;
    animation: fadeUp .6s .4s ease both;
  }

  .social-btn {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 10px 20px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 500;
    text-decoration: none;
    transition: all .25s;
    border: 1px solid var(--border);
    color: var(--text);
    background: var(--surface);
  }

  .social-btn:hover {
    border-color: var(--emerald);
    color: var(--emerald);
    background: rgba(16,185,129,.08);
    transform: translateY(-2px);
  }

  .social-btn svg { width: 16px; height: 16px; fill: currentColor; }

  /* ── SCROLL INDICATOR ── */
  .scroll-hint {
    position: absolute; bottom: 32px; left: 50%; transform: translateX(-50%);
    display: flex; flex-direction: column; align-items: center; gap: 8px;
    font-family: 'Space Mono', monospace; font-size: 10px;
    color: var(--muted); letter-spacing: .1em;
    animation: fadeUp .6s .8s ease both;
  }

  .scroll-line {
    width: 1px; height: 40px;
    background: linear-gradient(var(--emerald), transparent);
    animation: scrollPulse 2s ease-in-out infinite;
  }

  @keyframes scrollPulse {
    0%,100% { opacity: .3; transform: scaleY(.8); }
    50% { opacity: 1; transform: scaleY(1); }
  }

  /* ── SECTIONS ── */
  section { padding: 100px 24px; max-width: 1100px; margin: 0 auto; }

  .section-label {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--emerald);
    letter-spacing: .16em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: clamp(28px, 4vw, 46px);
    font-weight: 800;
    color: var(--white);
    margin-bottom: 48px;
    line-height: 1.15;
  }

  .section-title span {
    background: linear-gradient(90deg, var(--emerald), var(--purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  /* ── DIVIDER ── */
  .divider {
    width: 100%; height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 0 auto;
  }

  /* ── ABOUT ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 40px;
    align-items: start;
  }

  @media(max-width:700px) { .about-grid { grid-template-columns: 1fr; } }

  .code-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
    font-family: 'Space Mono', monospace;
    font-size: 12px;
  }

  .code-header {
    background: var(--surface2);
    border-bottom: 1px solid var(--border);
    padding: 12px 16px;
    display: flex; align-items: center; gap: 8px;
  }

  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot-red { background: #ff5f57; }
  .dot-yellow { background: #febc2e; }
  .dot-green { background: #28c840; }

  .code-body { padding: 20px; line-height: 1.9; }
  .code-kw { color: var(--purple); }
  .code-cls { color: #f59e0b; }
  .code-fn { color: var(--emerald); }
  .code-str { color: #fb7185; }
  .code-cmt { color: var(--muted); }
  .code-num { color: #60a5fa; }

  .info-cards { display: flex; flex-direction: column; gap: 16px; }

  .info-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 18px 22px;
    display: flex; align-items: flex-start; gap: 14px;
    transition: border-color .25s, transform .25s;
  }

  .info-card:hover {
    border-color: var(--emerald);
    transform: translateX(4px);
  }

  .info-icon {
    font-size: 22px;
    flex-shrink: 0;
    margin-top: 2px;
  }

  .info-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: .1em;
    text-transform: uppercase;
    margin-bottom: 4px;
  }

  .info-value {
    font-size: 14px;
    color: var(--white);
    font-weight: 500;
  }

  /* ── SKILLS ── */
  .skills-container { display: flex; flex-direction: column; gap: 40px; }

  .skill-group-title {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: .14em;
    text-transform: uppercase;
    margin-bottom: 16px;
    padding-bottom: 8px;
    border-bottom: 1px solid var(--border);
  }

  .skill-tags {
    display: flex; flex-wrap: wrap; gap: 10px;
  }

  .skill-tag {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 8px 16px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 500;
    border: 1px solid var(--border);
    background: var(--surface);
    color: var(--text);
    transition: all .2s;
    cursor: default;
  }

  .skill-tag:hover {
    border-color: var(--emerald);
    color: var(--emerald);
    background: rgba(16,185,129,.07);
    transform: translateY(-2px);
  }

  /* ── PROGRESS BARS ── */
  .progress-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
    margin-top: 40px;
  }

  @media(max-width:600px) { .progress-grid { grid-template-columns: 1fr; } }

  .progress-item {}

  .progress-header {
    display: flex;
    justify-content: space-between;
    margin-bottom: 8px;
    font-size: 13px;
    font-weight: 500;
    color: var(--white);
  }

  .progress-pct {
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    color: var(--emerald);
  }

  .progress-track {
    height: 5px;
    border-radius: 4px;
    background: var(--surface2);
    overflow: hidden;
  }

  .progress-fill {
    height: 100%;
    border-radius: 4px;
    background: linear-gradient(90deg, var(--emerald), var(--purple));
    width: 0%;
    transition: width 1.2s cubic-bezier(.16,1,.3,1);
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
  }

  @media(max-width:700px) { .projects-grid { grid-template-columns: 1fr; } }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px;
    display: flex; flex-direction: column;
    transition: border-color .25s, transform .3s, box-shadow .3s;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--emerald), var(--purple));
    transform: scaleX(0);
    transition: transform .3s;
  }

  .project-card:hover {
    border-color: transparent;
    transform: translateY(-6px);
    box-shadow: 0 20px 60px rgba(16,185,129,.12);
  }

  .project-card:hover::before { transform: scaleX(1); }

  .project-emoji { font-size: 36px; margin-bottom: 16px; }

  .project-title {
    font-family: 'Syne', sans-serif;
    font-size: 18px;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 12px;
  }

  .project-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.7;
    flex: 1;
    margin-bottom: 20px;
  }

  .project-tags { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 20px; }

  .project-tag {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    padding: 4px 10px;
    border-radius: 4px;
    background: rgba(16,185,129,.1);
    color: var(--emerald);
    border: 1px solid rgba(16,185,129,.2);
  }

  .project-link {
    display: inline-flex; align-items: center; gap: 6px;
    font-size: 13px;
    color: var(--emerald);
    text-decoration: none;
    font-weight: 500;
    transition: gap .2s;
  }

  .project-link:hover { gap: 10px; }

  /* ── COMING SOON CARD ── */
  .project-card.coming-soon {
    border-style: dashed;
    background: transparent;
  }

  .project-card.coming-soon .project-title,
  .project-card.coming-soon .project-desc { color: var(--muted); }

  /* ── EDUCATION ── */
  .edu-timeline { display: flex; flex-direction: column; gap: 0; }

  .edu-item {
    display: grid;
    grid-template-columns: 24px 1fr;
    gap: 24px;
    padding-bottom: 36px;
    position: relative;
  }

  .edu-item:last-child { padding-bottom: 0; }

  .edu-line {
    display: flex; flex-direction: column; align-items: center;
  }

  .edu-dot {
    width: 14px; height: 14px;
    border-radius: 50%;
    background: var(--emerald);
    border: 3px solid var(--bg);
    box-shadow: 0 0 0 2px var(--emerald);
    flex-shrink: 0;
    margin-top: 4px;
  }

  .edu-connector {
    width: 1px; flex: 1;
    background: linear-gradient(var(--border), var(--border));
    margin-top: 8px;
  }

  .edu-item:last-child .edu-connector { display: none; }

  .edu-content {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 24px;
    transition: border-color .25s;
  }

  .edu-content:hover { border-color: var(--emerald); }

  .edu-degree {
    font-family: 'Syne', sans-serif;
    font-size: 16px;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 6px;
  }

  .edu-inst {
    font-size: 13px;
    color: var(--emerald);
    margin-bottom: 4px;
  }

  .edu-year {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
  }

  /* ── CERTS ── */
  .cert-list { display: flex; flex-direction: column; gap: 12px; margin-top: 0; }

  .cert-item {
    display: flex; align-items: center; gap: 14px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 20px;
    transition: border-color .25s;
  }

  .cert-item:hover { border-color: var(--emerald); }

  .cert-medal { font-size: 22px; }

  .cert-name {
    font-size: 14px;
    font-weight: 500;
    color: var(--white);
  }

  .cert-by {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    margin-top: 2px;
  }

  /* ── FOOTER ── */
  footer {
    text-align: center;
    padding: 60px 24px;
    border-top: 1px solid var(--border);
    position: relative;
  }

  .footer-quote {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--muted);
    font-style: italic;
    margin-bottom: 8px;
  }

  .footer-attr {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--emerald);
    letter-spacing: .08em;
  }

  .footer-copy {
    margin-top: 28px;
    font-size: 12px;
    color: #3a5040;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity .7s ease, transform .7s ease;
  }

  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 40px;
    background: rgba(5,13,10,.8);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid rgba(16,185,129,.08);
  }

  .nav-logo {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--emerald);
    letter-spacing: .08em;
  }

  .nav-links {
    display: flex; gap: 28px;
    list-style: none;
  }

  .nav-links a {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    text-decoration: none;
    letter-spacing: .1em;
    text-transform: uppercase;
    transition: color .2s;
  }

  .nav-links a:hover { color: var(--emerald); }

  @media(max-width:600px) { .nav-links { display: none; } nav { padding: 14px 24px; } }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">rafin57</div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#education">Education</a></li>
  </ul>
</nav>

<main>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-glow"></div>
    <div class="hero-glow2"></div>

    <div class="badge-row">
      <span class="badge">ECE Undergraduate</span>
      <span class="badge">ML Enthusiast</span>
      <span class="badge">IoT Builder</span>
    </div>

    <h1>B.M. Rafin Rahman</h1>
    <p class="subtitle">Electronics &amp; Communication Engineer</p>
    <p>Building ML projects &amp; exploring Deep Learning from Khulna, Bangladesh. Passionate about AI, IoT, and open source.</p>

    <div class="social-row">
      <a class="social-btn" href="https://www.linkedin.com/in/b-m-rafin-rahman-2b1333325/" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="social-btn" href="mailto:rafinrahman698@gmail.com">
        <svg viewBox="0 0 24 24"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.907 1.528-1.148C21.69 2.28 24 3.434 24 5.457z"/></svg>
        Gmail
      </a>
      <a class="social-btn" href="https://rafin57.github.io/portfolio_website/" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.6.11.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
        Portfolio
      </a>
    </div>

    <div class="scroll-hint">
      <span>scroll</span>
      <div class="scroll-line"></div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ABOUT -->
  <section id="about">
    <div class="reveal">
      <p class="section-label">01 — About</p>
      <h2 class="section-title">Who am <span>I?</span></h2>
    </div>

    <div class="about-grid reveal">
      <div class="code-block">
        <div class="code-header">
          <div class="dot dot-red"></div>
          <div class="dot dot-yellow"></div>
          <div class="dot dot-green"></div>
        </div>
        <div class="code-body">
          <span class="code-kw">class</span> <span class="code-cls">RafinRahman</span>:<br>
          &nbsp;&nbsp;<span class="code-kw">def</span> <span class="code-fn">__init__</span>(self):<br>
          &nbsp;&nbsp;&nbsp;&nbsp;self.name &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = <span class="code-str">"B.M. Rafin Rahman"</span><br>
          &nbsp;&nbsp;&nbsp;&nbsp;self.university = <span class="code-str">"Khulna University"</span><br>
          &nbsp;&nbsp;&nbsp;&nbsp;self.degree &nbsp;&nbsp;&nbsp; = <span class="code-str">"B.Sc. in ECE"</span><br>
          &nbsp;&nbsp;&nbsp;&nbsp;self.batch &nbsp;&nbsp;&nbsp;&nbsp; = <span class="code-str">"2023 – Present"</span><br>
          &nbsp;&nbsp;&nbsp;&nbsp;self.location &nbsp; = <span class="code-str">"Khulna, Bangladesh"</span><br>
          &nbsp;&nbsp;&nbsp;&nbsp;self.dob &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = <span class="code-str">"21 May, 2005"</span><br>
          &nbsp;&nbsp;&nbsp;&nbsp;self.interests &nbsp;= [<br>
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-str">"Machine Learning"</span>,<br>
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-str">"Data Science"</span>,<br>
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-str">"IoT"</span>, <span class="code-str">"Web Dev"</span><br>
          &nbsp;&nbsp;&nbsp;&nbsp;]<br>
          &nbsp;&nbsp;&nbsp;&nbsp;self.goal &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = <span class="code-str">"Higher studies in AI/ML"</span><br><br>
          &nbsp;&nbsp;<span class="code-kw">def</span> <span class="code-fn">say_hi</span>(self):<br>
          &nbsp;&nbsp;&nbsp;&nbsp;<span class="code-fn">print</span>(<span class="code-str">"Let's build something amazing 🚀"</span>)<br><br>
          <span class="code-cls">me</span> = RafinRahman()<br>
          <span class="code-cls">me</span>.say_hi()
        </div>
      </div>

      <div class="info-cards">
        <div class="info-card">
          <div class="info-icon">🎓</div>
          <div>
            <div class="info-label">Degree</div>
            <div class="info-value">B.Sc. in Electronics &amp; Communication Engineering</div>
          </div>
        </div>
        <div class="info-card">
          <div class="info-icon">🏫</div>
          <div>
            <div class="info-label">University</div>
            <div class="info-value">Khulna University, Bangladesh</div>
          </div>
        </div>
        <div class="info-card">
          <div class="info-icon">📍</div>
          <div>
            <div class="info-label">Location</div>
            <div class="info-value">Khulna, Bangladesh</div>
          </div>
        </div>
        <div class="info-card">
          <div class="info-icon">🎯</div>
          <div>
            <div class="info-label">Goal</div>
            <div class="info-value">Pursue higher studies abroad in AI / ML</div>
          </div>
        </div>
        <div class="info-card">
          <div class="info-icon">🔭</div>
          <div>
            <div class="info-label">Currently</div>
            <div class="info-value">Building ML projects &amp; exploring Deep Learning</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- SKILLS -->
  <section id="skills">
    <div class="reveal">
      <p class="section-label">02 — Skills</p>
      <h2 class="section-title">Tech <span>Stack</span></h2>
    </div>

    <div class="skills-container reveal">
      <div>
        <div class="skill-group-title">💻 Programming Languages</div>
        <div class="skill-tags">
          <span class="skill-tag">⚙️ C++</span>
          <span class="skill-tag">🐍 Python</span>
          <span class="skill-tag">☕ Java</span>
          <span class="skill-tag">📐 MATLAB</span>
        </div>
      </div>
      <div>
        <div class="skill-group-title">🤖 Machine Learning &amp; Data Science</div>
        <div class="skill-tags">
          <span class="skill-tag">🔬 Scikit-Learn</span>
          <span class="skill-tag">🔢 NumPy</span>
          <span class="skill-tag">🐼 Pandas</span>
          <span class="skill-tag">📊 Plotly</span>
          <span class="skill-tag">🚀 Streamlit</span>
          <span class="skill-tag">🧠 TensorFlow</span>
        </div>
      </div>
      <div>
        <div class="skill-group-title">🌐 Web Development</div>
        <div class="skill-tags">
          <span class="skill-tag">🌐 HTML5</span>
          <span class="skill-tag">🎨 CSS3</span>
          <span class="skill-tag">⚡ JavaScript</span>
          <span class="skill-tag">🐘 PHP</span>
          <span class="skill-tag">🗄️ MySQL</span>
        </div>
      </div>
      <div>
        <div class="skill-group-title">⚙️ Tools &amp; Platforms</div>
        <div class="skill-tags">
          <span class="skill-tag">🔧 Git</span>
          <span class="skill-tag">🐙 GitHub</span>
          <span class="skill-tag">💻 VS Code</span>
          <span class="skill-tag">🎨 Figma</span>
          <span class="skill-tag">📡 ESP32</span>
          <span class="skill-tag">🔌 Arduino</span>
          <span class="skill-tag">📓 Jupyter</span>
          <span class="skill-tag">🏆 Kaggle</span>
        </div>
      </div>
    </div>

    <!-- PROGRESS BARS -->
    <div class="progress-grid reveal" id="progress-section">
      <div class="progress-item">
        <div class="progress-header"><span>HTML5</span><span class="progress-pct">92%</span></div>
        <div class="progress-track"><div class="progress-fill" data-pct="92"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-header"><span>C++</span><span class="progress-pct">90%</span></div>
        <div class="progress-track"><div class="progress-fill" data-pct="90"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-header"><span>Python</span><span class="progress-pct">88%</span></div>
        <div class="progress-track"><div class="progress-fill" data-pct="88"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-header"><span>CSS3</span><span class="progress-pct">88%</span></div>
        <div class="progress-track"><div class="progress-fill" data-pct="88"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-header"><span>NumPy / Pandas</span><span class="progress-pct">70%</span></div>
        <div class="progress-track"><div class="progress-fill" data-pct="70"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-header"><span>Data Analysis</span><span class="progress-pct">65%</span></div>
        <div class="progress-track"><div class="progress-fill" data-pct="65"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-header"><span>Java</span><span class="progress-pct">65%</span></div>
        <div class="progress-track"><div class="progress-fill" data-pct="65"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-header"><span>MATLAB</span><span class="progress-pct">60%</span></div>
        <div class="progress-track"><div class="progress-fill" data-pct="60"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-header"><span>Machine Learning</span><span class="progress-pct">55%</span></div>
        <div class="progress-track"><div class="progress-fill" data-pct="55"></div></div>
      </div>
      <div class="progress-item">
        <div class="progress-header"><span>Deep Learning</span><span class="progress-pct">45%</span></div>
        <div class="progress-track"><div class="progress-fill" data-pct="45"></div></div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- PROJECTS -->
  <section id="projects">
    <div class="reveal">
      <p class="section-label">03 — Projects</p>
      <h2 class="section-title">Featured <span>Work</span></h2>
    </div>

    <div class="projects-grid reveal">
      <div class="project-card">
        <div class="project-emoji">🫀</div>
        <div class="project-title">Heart Disease Prediction Web App</div>
        <p class="project-desc">A machine learning web application predicting heart disease risk using patient health data. End-to-end pipeline from data preprocessing → model training → Streamlit deployment.</p>
        <div class="project-tags">
          <span class="project-tag">Python</span>
          <span class="project-tag">Scikit-Learn</span>
          <span class="project-tag">Streamlit</span>
          <span class="project-tag">Pandas</span>
          <span class="project-tag">Plotly</span>
        </div>
        <a class="project-link" href="https://github.com/rafin57" target="_blank">View on GitHub →</a>
      </div>

      <div class="project-card">
        <div class="project-emoji">🌱</div>
        <div class="project-title">Smart Irrigation System</div>
        <p class="project-desc">A solar-powered IoT system that automatically controls water supply using soil moisture data, with remote monitoring &amp; manual override via a mobile app.</p>
        <div class="project-tags">
          <span class="project-tag">ESP32</span>
          <span class="project-tag">IoT</span>
          <span class="project-tag">Arduino</span>
          <span class="project-tag">Solar Power</span>
        </div>
        <a class="project-link" href="https://github.com/rafin57/Smart-Irrigation-System/tree/main" target="_blank">View on GitHub →</a>
      </div>

      <div class="project-card">
        <div class="project-emoji">🌐</div>
        <div class="project-title">Portfolio Website</div>
        <p class="project-desc">A fully responsive personal portfolio with dark theme, smooth scroll-reveal animations, interactive skills section, and project showcase.</p>
        <div class="project-tags">
          <span class="project-tag">HTML5</span>
          <span class="project-tag">CSS3</span>
          <span class="project-tag">JavaScript</span>
        </div>
        <a class="project-link" href="https://rafin57.github.io/portfolio_website/" target="_blank">Live Demo →</a>
      </div>

      <div class="project-card coming-soon">
        <div class="project-emoji">💡</div>
        <div class="project-title">More Coming Soon…</div>
        <p class="project-desc">Currently exploring Deep Learning, Computer Vision, and NLP projects. Stay tuned for more exciting builds! 🔭</p>
        <div class="project-tags">
          <span class="project-tag">Deep Learning</span>
          <span class="project-tag">Computer Vision</span>
          <span class="project-tag">NLP</span>
        </div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- EDUCATION + CERTS -->
  <section id="education">
    <div class="reveal">
      <p class="section-label">04 — Background</p>
      <h2 class="section-title">Education &amp; <span>Certifications</span></h2>
    </div>

    <div class="about-grid reveal">
      <div>
        <div class="edu-timeline">
          <div class="edu-item">
            <div class="edu-line">
              <div class="edu-dot"></div>
              <div class="edu-connector"></div>
            </div>
            <div class="edu-content">
              <div class="edu-degree">🎓 B.Sc. in Electronics &amp; Communication Engineering</div>
              <div class="edu-inst">Khulna University, Khulna</div>
              <div class="edu-year">2023 – Present</div>
            </div>
          </div>
          <div class="edu-item">
            <div class="edu-line">
              <div class="edu-dot" style="background:var(--purple); box-shadow:0 0 0 2px var(--purple)"></div>
              <div class="edu-connector"></div>
            </div>
            <div class="edu-content">
              <div class="edu-degree">📚 Higher Secondary Certificate (HSC) — Science</div>
              <div class="edu-inst">Government Science College, Dhaka</div>
              <div class="edu-year">2022</div>
            </div>
          </div>
          <div class="edu-item">
            <div class="edu-line">
              <div class="edu-dot" style="background:var(--muted); box-shadow:0 0 0 2px var(--muted)"></div>
              <div class="edu-connector"></div>
            </div>
            <div class="edu-content">
              <div class="edu-degree">📖 Secondary School Certificate (SSC) — Science</div>
              <div class="edu-inst">Mrigi High School, Rajbari</div>
              <div class="edu-year">2020</div>
            </div>
          </div>
        </div>
      </div>

      <div>
        <div class="skill-group-title" style="margin-bottom:20px;">🏆 Certifications</div>
        <div class="cert-list">
          <div class="cert-item">
            <div class="cert-medal">🥇</div>
            <div>
              <div class="cert-name">Machine Learning</div>
              <div class="cert-by">Andrew Ng, Stanford University · Coursera</div>
            </div>
          </div>
          <div class="cert-item">
            <div class="cert-medal">🥇</div>
            <div>
              <div class="cert-name">Python for Data Science</div>
              <div class="cert-by">IBM · Coursera</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

</main>

<!-- FOOTER -->
<footer>
  <p class="footer-quote">"The science of today is the technology of tomorrow."</p>
  <p class="footer-attr">— Edward Teller</p>
  <p class="footer-copy">© 2024 B.M. Rafin Rahman · Built with ♥ in Khulna</p>
</footer>

<script>
  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.12 }).observe && reveals.forEach(el =>
    new IntersectionObserver((entries) => {
      entries.forEach(e => { if (e.isIntersecting) el.classList.add('visible'); });
    }, { threshold: 0.12 }).observe(el)
  );

  // Progress bars
  const progressSection = document.querySelector('.progress-grid');
  if (progressSection) {
    new IntersectionObserver((entries) => {
      entries.forEach(e => {
        if (e.isIntersecting) {
          document.querySelectorAll('.progress-fill').forEach((bar, i) => {
            setTimeout(() => { bar.style.width = bar.dataset.pct + '%'; }, i * 80);
          });
        }
      });
    }, { threshold: 0.2 }).observe(progressSection);
  }
</script>

</body>
</html>
