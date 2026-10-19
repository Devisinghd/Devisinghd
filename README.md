<!--
  Premium / Luxury 3D GitHub Profile README
  - Dark luxury palette: obsidian, charcoal, gold accents, champagne glows
  - Pure HTML + inline SVG + CSS (no JS)
  - Replace `DEVISE_YOUR_USERNAME` and links where needed
-->

<div class="luxury-root">

<style>
  /* ====== Palette & base ====== */
  :root{
    --bg-obsidian: #0b0b0c;
    --charcoal: #111214;
    --gold: #D4AF37;
    --gold-2: #FFD86B;
    --platinum: rgba(255,255,255,0.06);
    --glass: rgba(255,255,255,0.04);
    --accent: #00d4ff;
    --text: #E7E7E9;
    --muted: #9AA0A6;
  }

  .luxury-root{
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    color: var(--text);
    background: linear-gradient(180deg, rgba(10,10,10,0.85) 0%, rgba(3,3,3,0.95) 100%);
    padding: 28px 18px;
    border-radius: 14px;
    box-shadow:
      0 6px 30px rgba(0,0,0,0.7),
      inset 0 1px 0 rgba(255,255,255,0.02);
    max-width: 980px;
    margin: 20px auto;
    backdrop-filter: blur(6px);
  }

  a { color: var(--gold-2); text-decoration: none; }
  a:hover { text-decoration: underline; }

  /* ====== 3D Hero / Typographic Banner (SVG) ====== */
  .hero {
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: center;
    gap: 18px;
    margin-bottom: 22px;
  }

  .hero-svg {
    width: 100%;
    max-width: 720px;
    height: 96px;
    display:block;
  }

  /* animated glint across text */
  .glint {
    position: relative;
    overflow: visible;
  }
  .glint::after{
    content: "";
    position: absolute;
    left: -40%;
    top: -50%;
    width: 40%;
    height: 200%;
    transform: skewX(-22deg);
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.12), transparent);
    animation: glintMove 6s linear infinite;
    mix-blend-mode: screen;
    pointer-events: none;
  }
  @keyframes glintMove{
    0% { left: -40%; opacity: 0; }
    30% { opacity: 1; }
    55% { left: 120%; opacity: 1; }
    100% { left: 120%; opacity: 0; }
  }

  /* Status card */
  .status-wrapper {
    display:flex;
    align-items:center;
    gap:12px;
  }
  .status-card{
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border-radius: 12px;
    padding: 12px 16px;
    min-width: 300px;
    border: 1px solid rgba(212,175,55,0.12);
    box-shadow:
      0 8px 30px rgba(0,0,0,0.6),
      0 0 18px rgba(212,175,55,0.04),
      inset 0 1px 0 rgba(255,255,255,0.02);
    position: relative;
    transform-style: preserve-3d;
    transition: transform .45s cubic-bezier(.2,.9,.2,1), box-shadow .45s;
  }
  .status-card:hover{
    transform: translateY(-6px) rotateX(3deg);
    box-shadow:
      0 18px 48px rgba(0,0,0,0.7),
      0 0 30px rgba(212,175,55,0.08);
  }
  .status-card::before{
    content:"";
    position:absolute;
    inset: -2px;
    border-radius:14px;
    background: linear-gradient(90deg, rgba(212,175,55,0.06), rgba(255,255,255,0.02));
    filter: blur(10px);
    z-index:-1;
    opacity:0.9;
    transform: translateZ(-1px);
    pointer-events:none;
  }
  .status-tagline{
    font-weight:600;
    color: var(--text);
    letter-spacing:0.2px;
  }
  .status-mini {
    display:flex;
    gap:8px;
    align-items:center;
    color:var(--muted);
    font-size:12px;
  }

  /* ====== Layout sections ====== */
  .grid {
    display:grid;
    grid-template-columns: 1fr;
    gap: 18px;
  }
  @media(min-width:980px){
    .grid { grid-template-columns: 1fr 420px; align-items:start; }
  }

  /* About card glass / brushed metal */
  .card {
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border-radius: 12px;
    padding: 18px;
    border: 1px solid rgba(255,255,255,0.03);
    box-shadow:
      0 10px 30px rgba(0,0,0,0.6),
      inset 0 1px 0 rgba(255,255,255,0.02);
    position: relative;
    overflow: hidden;
  }
  .card .title {
    display:flex;
    align-items:center;
    gap:12px;
    margin-bottom: 8px;
  }
  .card .title h3 {
    margin:0;
    font-size:18px;
    letter-spacing:0.6px;
  }
  .about-body{
    font-size:14px;
    color:var(--muted);
    line-height:1.55;
  }

  /* micro decorative brushed-metal stripe */
  .brushed {
    height: 6px;
    background: linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.04), rgba(255,255,255,0.02));
    border-radius: 4px;
    margin-bottom:12px;
    box-shadow: 0 1px 0 rgba(255,255,255,0.02) inset;
  }

  /* Tech stack badges (grid + 3D hover) */
  .stack {
    display:grid;
    grid-template-columns: repeat(auto-fit, minmax(96px,1fr));
    gap:12px;
    margin-top:6px;
  }
  .badge {
    background: linear-gradient(180deg, rgba(255,255,255,0.015), rgba(255,255,255,0.01));
    border-radius: 10px;
    padding: 10px;
    display:flex;
    align-items:center;
    gap:10px;
    border: 1px solid rgba(212,175,55,0.08);
    transition: transform .36s cubic-bezier(.2,.9,.2,1), box-shadow .36s, filter .36s;
    cursor: default;
    box-shadow: 0 6px 18px rgba(0,0,0,0.6);
  }
  .badge svg { width:40px; height:40px; flex-shrink:0; }
  .badge .label { font-weight:600; font-size:13px; color:var(--text); }
  .badge:hover{
    transform: translateY(-8px) rotateX(6deg);
    box-shadow: 0 26px 42px rgba(0,0,0,0.7), 0 0 30px rgba(212,175,55,0.06);
    filter: saturate(1.08);
  }
  .badge .logo-wrap {
    width:44px;height:44px;border-radius:8px;
    display:grid;place-items:center;
    background: linear-gradient(145deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border:1px solid rgba(255,255,255,0.02);
    box-shadow: 0 4px 18px rgba(0,0,0,0.5), inset 0 1px 0 rgba(255,255,255,0.02);
  }

  /* Core pillars 3-column */
  .pillars {
    display:grid;
    grid-template-columns: 1fr;
    gap:12px;
    margin-top:12px;
  }
  @media(min-width:720px){
    .pillars { grid-template-columns: repeat(3,1fr); }
  }
  .pillar {
    background: linear-gradient(180deg, rgba(255,255,255,0.012), rgba(255,255,255,0.008));
    border-radius: 12px;
    padding: 14px;
    text-align:center;
    border:1px solid rgba(212,175,55,0.06);
    transition: transform .36s;
  }
  .pillar:hover { transform: translateY(-6px); box-shadow: 0 18px 40px rgba(0,0,0,0.6); }
  .pillar h4 { margin:8px 0 6px 0; font-size:15px; color:var(--text); }
  .pillar p { margin:0; color:var(--muted); font-size:13px; line-height:1.45; }

  /* Stats panel - framed */
  .stats-frame {
    margin-top: 12px;
    border-radius: 12px;
    padding: 14px;
    background: linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.005));
    border: 1px solid rgba(212,175,55,0.06);
    box-shadow: 0 12px 30px rgba(0,0,0,0.65);
    display:flex;
    gap:12px;
    align-items:center;
    justify-content:center;
    flex-direction:column;
  }
  .stats-frame img {
    border-radius:10px;
    border: 1px solid rgba(255,255,255,0.02);
    box-shadow: 0 8px 20px rgba(0,0,0,0.6);
    max-width:100%;
  }

  /* footer small */
  .connect {
    display:flex;
    gap:12px;
    align-items:center;
    justify-content:center;
    margin-top:16px;
  }
  .chip {
    padding:8px 12px;
    border-radius:999px;
    background:linear-gradient(90deg, rgba(212,175,55,0.04), rgba(255,255,255,0.01));
    border: 1px solid rgba(212,175,55,0.06);
    font-size:13px;color:var(--muted);
  }

  /* subtle animated gradient background details */
  .luxury-root::after{
    content:"";
    position:absolute;
    left:50%;
    transform:translateX(-50%);
    bottom:-80px;
    width:760px;height:240px;
    background: radial-gradient(closest-side, rgba(212,175,55,0.04), transparent 40%);
    filter: blur(28px);
    pointer-events:none;
    mix-blend-mode: screen;
  }
</style>

<!-- ====== HERO: 3D banner + status ====== -->
<div class="hero">

  <!-- Inline SVG 3D-style text -->
  <div class="glint" aria-hidden="true">
    <svg class="hero-svg" viewBox="0 0 1200 140" preserveAspectRatio="xMidYMid meet" xmlns="http://www.w3.org/2000/svg" role="img" aria-labelledby="titleDesc">
      <title id="titleDesc">Dev Dangi — Full Stack Developer — 3D Premium Banner</title>
      <defs>
        <linearGradient id="gradText" x1="0" x2="1">
          <stop offset="0%" stop-color="#f6f0e6"/>
          <stop offset="40%" stop-color="#e6d6b0"/>
          <stop offset="100%" stop-color="#b08a2e"/>
        </linearGradient>

        <!-- soft blur for glow -->
        <filter id="softGlow" x="-50%" y="-50%" width="200%" height="200%">
          <feGaussianBlur stdDeviation="8" result="blur"/>
          <feMerge>
            <feMergeNode in="blur"/>
            <feMergeNode in="SourceGraphic"/>
          </feMerge>
        </filter>

        <!-- subtle beveled lighting -->
        <linearGradient id="shine" x1="0" x2="0">
          <stop offset="0%" stop-color="rgba(255,255,255,0.14)"/>
          <stop offset="70%" stop-color="rgba(255,255,255,0.02)"/>
        </linearGradient>
      </defs>

      <!-- extruded shadow layers for 3D depth -->
      <g font-family="Georgia, 'Times New Roman', serif" font-weight="700" font-size="72" text-anchor="start">
        <!-- Back shadow slices -->
        <text x="40" y="90" fill="#050607" opacity="0.85" transform="translate(0,6)">
          Dev Dangi
        </text>
        <text x="42" y="88" fill="#0c0c0d" opacity="0.8" transform="translate(0,3)">
          Dev Dangi
        </text>

        <!-- Main gradient text -->
        <text x="44" y="86" fill="url(#gradText)" style="filter:url(#softGlow);">
          Dev Dangi
        </text>

        <!-- subtle highlight stroke -->
        <text x="44" y="86" fill="none" stroke="rgba(255,255,255,0.15)" stroke-width="0.6">
          Dev Dangi
        </text>

        <!-- subtitle -->
        <text x="44" y="122" fill="#9ea6ad" font-size="20" font-weight="600">
          Crafting Digital Luxury & High‑Performance Code
        </text>
      </g>

    </svg>
  </div>

  <!-- status card -->
  <div class="status-wrapper" aria-hidden="false">
    <div class="status-card" title="Crafting Digital Luxury & High‑Performance Code">
      <div style="display:flex;flex-direction:column;gap:6px;">
        <div style="display:flex;justify-content:space-between;align-items:center;">
          <div style="display:flex;gap:10px;align-items:center;">
            <div style="width:40px;height:40px;border-radius:10px;background:linear-gradient(135deg,#1b1b1c,#0f0f10);display:grid;place-items:center;border:1px solid rgba(255,255,255,0.02)">
              <!-- mini crest (SVG) -->
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" aria-hidden="true">
                <rect x="2" y="2" width="20" height="20" rx="4" fill="#0f0f10"/>
                <path d="M6 15 L10 9 L14 14 L18 8" stroke="url(#gld)" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/>
                <defs>
                  <linearGradient id="gld" x1="0" x2="1"><stop offset="0" stop-color="#FFD86B"/><stop offset="1" stop-color="#D4AF37"/></linearGradient>
                </defs>
              </svg>
            </div>
            <div>
              <div class="status-tagline">Crafting Digital Luxury & High‑Performance Code</div>
              <div class="status-mini">Full-Stack • Django / FastAPI • Scalable Platforms</div>
            </div>
          </div>
          <div style="display:flex;gap:8px;align-items:center;">
            <span style="font-size:12px;color:var(--muted);">Current</span>
            <span style="padding:6px 10px;border-radius:999px;background:linear-gradient(90deg,#2a2a2b,#151515);border:1px solid rgba(212,175,55,0.08);color:var(--gold);font-weight:700;">Building NovaChat</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ====== MAIN GRID: Left (About/Stack/Pillars) / Right (Stats & Connect) ====== -->
<div class="grid">

  <!-- LEFT COLUMN -->
  <div>

    <!-- About -->
    <div class="card" aria-labelledby="aboutTitle">
      <div class="title">
        <svg width="34" height="34" viewBox="0 0 24 24" fill="none" aria-hidden="true">
          <rect x="0.5" y="0.5" width="23" height="23" rx="5" fill="#0f0f10" stroke="rgba(212,175,55,0.08)"/>
          <path d="M7 13 L11 8 L17 15" stroke="url(#g2)" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/>
          <defs><linearGradient id="g2" x1="0" x2="1"><stop offset="0" stop-color="#FFD86B"/><stop offset="1" stop-color="#D4AF37"/></linearGradient></defs>
        </svg>
        <h3 id="aboutTitle">About Me</h3>
      </div>

      <div class="brushed" aria-hidden="true"></div>

      <div class="about-body">
        I'm Dev Dangi — a Full Stack developer who blends high-performance backend architecture with refined, pixel-perfect frontend experiences. I build mission-critical web platforms and APIs that scale reliably under real user load, while keeping UX delightful and accessible.
        <ul style="margin-top:10px;color:var(--muted);">
          <li>Primary: Python, Django, FastAPI</li>
          <li>Frontend: React, TypeScript, Tailwind</li>
          <li>Infra: PostgreSQL, Redis, Docker, GitHub Actions</li>
        </ul>
      </div>
    </div>

    <!-- Tech Stack -->
    <div class="card" style="margin-top:12px;">
      <div class="title">
        <svg width="34" height="34" viewBox="0 0 24 24" fill="none" aria-hidden="true">
          <rect x="1" y="1" width="22" height="22" rx="5" fill="#0f0f10" stroke="rgba(212,175,55,0.06)"/>
          <path d="M6 12h12M6 7h12M6 17h12" stroke="rgba(255,255,255,0.06)" stroke-width="1.4" stroke-linecap="round"/>
        </svg>
        <h3 style="margin:0">Tech Stack</h3>
      </div>

      <div class="stack" aria-hidden="false">
        <!-- Python -->
        <div class="badge">
          <div class="logo-wrap">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Python">
              <defs><linearGradient id="pyGrad" x1="0" x2="1"><stop offset="0" stop-color="#3776AB"/><stop offset="1" stop-color="#2E6CB2"/></linearGradient></defs>
              <rect width="48" height="48" rx="8" fill="url(#pyGrad)"/>
              <text x="24" y="32" font-size="18" font-weight="700" text-anchor="middle" fill="white" font-family="Inter,Arial">Py</text>
            </svg>
          </div>
          <div class="label">Python</div>
        </div>

        <!-- Django -->
        <div class="badge">
          <div class="logo-wrap">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Django">
              <rect width="48" height="48" rx="8" fill="#092E20"/>
              <text x="24" y="32" font-size="14" font-weight="700" text-anchor="middle" fill="#9EE9D3" font-family="Inter,Arial">Dj</text>
            </svg>
          </div>
          <div class="label">Django</div>
        </div>

        <!-- FastAPI -->
        <div class="badge">
          <div class="logo-wrap">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="FastAPI">
              <rect width="48" height="48" rx="8" fill="#009688"/>
              <text x="24" y="32" font-size="12" font-weight="700" text-anchor="middle" fill="white" font-family="Inter,Arial">Fast</text>
            </svg>
          </div>
          <div class="label">FastAPI</div>
        </div>

        <!-- React -->
        <div class="badge">
          <div class="logo-wrap">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="React">
              <rect width="48" height="48" rx="8" fill="#20232A"/>
              <g transform="translate(6,6)" fill="none" stroke="#61DAFB" stroke-width="1.8">
                <ellipse cx="18" cy="18" rx="10" ry="18" transform="rotate(0 18 18)"/>
                <ellipse cx="18" cy="18" rx="10" ry="18" transform="rotate(60 18 18)"/>
                <ellipse cx="18" cy="18" rx="10" ry="18" transform="rotate(120 18 18)"/>
              </g>
            </svg>
          </div>
          <div class="label">React</div>
        </div>

        <!-- TypeScript -->
        <div class="badge">
          <div class="logo-wrap">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="TypeScript">
              <rect width="48" height="48" rx="8" fill="#3178C6"/>
              <text x="24" y="32" font-size="14" font-weight="700" text-anchor="middle" fill="white" font-family="Inter,Arial">TS</text>
            </svg>
          </div>
          <div class="label">TypeScript</div>
        </div>

        <!-- Tailwind -->
        <div class="badge">
          <div class="logo-wrap">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Tailwind">
              <rect width="48" height="48" rx="8" fill="#06B6D4"/>
              <path d="M8 30c8 0 8-10 20-10 4 0 8 4 12 4" stroke="#022D3A" stroke-width="2" fill="none" stroke-linecap="round"/>
            </svg>
          </div>
          <div class="label">Tailwind</div>
        </div>

        <!-- PostgreSQL -->
        <div class="badge">
          <div class="logo-wrap">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="PostgreSQL">
              <rect width="48" height="48" rx="8" fill="#316192"/>
              <text x="24" y="32" font-size="12" font-weight="700" text-anchor="middle" fill="#EAF5FF" font-family="Inter,Arial">PG</text>
            </svg>
          </div>
          <div class="label">Postgres</div>
        </div>

        <!-- Redis -->
        <div class="badge">
          <div class="logo-wrap">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Redis">
              <rect width="48" height="48" rx="8" fill="#DC382D"/>
              <circle cx="24" cy="24" r="8" fill="#FFF1F0" opacity="0.06"/>
              <text x="24" y="32" font-size="12" font-weight="700" text-anchor="middle" fill="#fff" font-family="Inter,Arial">RD</text>
            </svg>
          </div>
          <div class="label">Redis</div>
        </div>

        <!-- Docker -->
        <div class="badge">
          <div class="logo-wrap">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Docker">
              <rect width="48" height="48" rx="8" fill="#2496ED"/>
              <text x="24" y="32" font-size="12" font-weight="700" text-anchor="middle" fill="#fff" font-family="Inter,Arial">DK</text>
            </svg>
          </div>
          <div class="label">Docker</div>
        </div>

        <!-- GitHub Actions -->
        <div class="badge">
          <div class="logo-wrap">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="GitHub Actions">
              <rect width="48" height="48" rx="8" fill="#0b0b0b"/>
              <text x="24" y="32" font-size="10" font-weight="700" text-anchor="middle" fill="#2088FF" font-family="Inter,Arial">GHA</text>
            </svg>
          </div>
          <div class="label">CI / CD</div>
        </div>
      </div>
    </div>

    <!-- Core Pillars -->
    <div class="pillars" style="margin-top:12px;">
      <div class="pillar">
        <svg width="36" height="36" viewBox="0 0 24 24" aria-hidden="true">
          <rect x="1" y="1" width="22" height="22" rx="5" fill="#0f0f10" stroke="rgba(212,175,55,0.06)"/>
          <path d="M6 12h12" stroke="#FFD86B" stroke-width="1.6" stroke-linecap="round"/>
        </svg>
        <h4>Architecture</h4>
        <p>Clean, modular systems with business-driven domain models and secure API design.</p>
      </div>

      <div class="pillar">
        <svg width="36" height="36" viewBox="0 0 24 24" aria-hidden="true">
          <rect x="1" y="1" width="22" height="22" rx="5" fill="#0f0f10" stroke="rgba(212,175,55,0.06)"/>
          <path d="M6 12 L10 8 L14 12 L18 8" stroke="#FFD86B" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <h4>Scalability</h4>
        <p>Horizontal scaling patterns, caching strategies, and resilient background processing.</p>
      </div>

      <div class="pillar">
        <svg width="36" height="36" viewBox="0 0 24 24" aria-hidden="true">
          <rect x="1" y="1" width="22" height="22" rx="5" fill="#0f0f10" stroke="rgba(212,175,55,0.06)"/>
          <path d="M8 16c3-4 5-4 8 0" stroke="#FFD86B" stroke-width="1.6" stroke-linecap="round"/>
        </svg>
        <h4>Design</h4>
        <p>Pixel-aware UI, accessibility-first components and delightful motion design.</p>
      </div>
    </div>

  </div>

  <!-- RIGHT COLUMN -->
  <aside>
    <div class="card" aria-labelledby="statsTitle">
      <div class="title">
        <h3 id="statsTitle">GitHub Stats</h3>
      </div>
      <div class="brushed" aria-hidden="true"></div>

      <!-- Styled frame for external readme images (replace username) -->
      <div class="stats-frame">
        <!-- Main stats (replace username in URL) -->
        <img src="https://github-readme-stats.vercel.app/api?username=Devisinghd&show_icons=true&hide_border=true&bg_color=0b0b0b&title_color=FFD86B&icon_color=FFD86B&text_color=E7E7E9" alt="GitHub stats for Devisinghd" />

        <!-- Top langs -->
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Devisinghd&layout=compact&hide_border=true&bg_color=0b0b0b&title_color=FFD86B&text_color=E7E7E9" alt="Top languages for Devisinghd" style="margin-top:10px;"/>

        <!-- Trophy (optional) -->
        <img src="https://github-profile-trophy.vercel.app/?username=Devisinghd&theme=gruvbox&no-frame=true&no-bg=true" alt="Trophies for Devisinghd" style="margin-top:10px;filter: hue-rotate(10deg) saturate(0.9)"/>
      </div>

      <div style="font-size:12px;color:var(--muted);margin-top:10px;text-align:center;">
        Tip: customize the images' query params (title_color, bg_color, icon_color) to match theme.
      </div>
    </div>

    <!-- Connect -->
    <div style="margin-top:12px;" class="card">
      <div class="title"><h3 style="margin:0">Connect</h3></div>
      <div style="margin-top:10px;text-align:center;color:var(--muted);font-size:13px;">
        <div style="display:flex;gap:8px;justify-content:center;margin-bottom:8px;">
          <a href="https://github.com/Devisinghd" target="_blank" rel="noreferrer" class="chip">GitHub</a>
          <a href="https://www.linkedin.com/in/your-linkedin" target="_blank" rel="noreferrer" class="chip">LinkedIn</a>
          <a href="https://x.com/your-handle" target="_blank" rel="noreferrer" class="chip">X</a>
        </div>
        <div style="color:var(--muted);font-size:13px;">Or email: <a href="mailto:devisinghdangi786@gmail.com" style="color:var(--gold-2)">devisinghdangi786@gmail.com</a></div>
      </div>
    </div>

  </aside>

</div>

<!-- small footer note: usage & customizations -->
<div style="margin-top:18px;text-align:center;color:var(--muted);font-size:13px;">
  <div>Made with care • Dark luxury theme • 3D text & subtle motion — paste into <code>README.md</code> and replace links & username</div>
</div>

</div>
