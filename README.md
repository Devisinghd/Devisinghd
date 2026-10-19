<!--
  README.md — Premium Pseudo-3D Glassmorphism Profile
  Username: Devisinghd
  Paste this file content directly into your repository README.md
  NOTE: Replace repo links and small copy where needed.
-->

<div class="isometric-root">

<style>
  :root{
    --obsidian: #09090b;
    --charcoal: #111214;
    --ink: #171a1d;
    --gold: #d4af37;
    --gold-2: #f9d77e;
    --champagne: #f2e8cf;
    --platinum: #edf2f7;
    --muted: #a8b0b8;
    --glass: rgba(255,255,255,0.04);
    --line: rgba(212,175,55,0.12);
    --shadow: rgba(0,0,0,0.65);
  }

  /* Root container */
  .isometric-root {
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    color: var(--platinum);
    max-width: 1080px;
    margin: 24px auto;
    padding: 28px;
    border-radius: 14px;
    background:
      linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.005)),
      radial-gradient(800px 200px at 10% 10%, rgba(212,175,55,0.03), transparent 12%),
      var(--obsidian);
    border: 1px solid rgba(255,255,255,0.02);
    box-shadow:
      0 18px 40px var(--shadow),
      0 2px 0 rgba(255,255,255,0.01) inset;
    position: relative;
    overflow: hidden;
  }

  /* Top SVG banner */
  .banner {
    display:block;
    width:100%;
    height:140px;
    margin-bottom:18px;
    border-radius:10px;
    overflow:visible;
  }
  .banner svg { display:block; width:100%; height:100%; }

  /* subtle animated ambient glow behind entire layout */
  .isometric-root::before{
    content:"";
    position:absolute;
    inset:auto -10% -40% auto;
    width:520px; height:520px;
    background: radial-gradient(circle at 30% 30%, rgba(212,175,55,0.06), transparent 30%);
    filter: blur(34px);
    pointer-events:none;
  }

  /* Layout grid */
  .layout {
    display:grid;
    grid-template-columns: 1fr 380px;
    gap:18px;
    align-items:start;
  }
  @media (max-width:1000px){
    .layout { grid-template-columns: 1fr; }
  }

  /* Isometric / layered hero */
  .hero-stack {
    display:flex;
    gap:14px;
    align-items:flex-start;
    transform-style:preserve-3d;
    perspective:900px;
  }

  .card {
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border-radius:12px;
    padding:16px;
    border:1px solid rgba(255,255,255,0.03);
    box-shadow: 0 18px 36px rgba(0,0,0,0.5);
    position:relative;
    overflow:hidden;
    transition: transform .36s cubic-bezier(.2,.9,.2,1), box-shadow .36s;
  }

  /* angled/isometric visual treatment: use skew to suggest depth */
  .iso-card {
    transform: skewY(-6deg) translateZ(0);
    will-change: transform;
  }
  .iso-card .card-inner { transform: skewY(6deg); } /* counter-skew for content legibility */

  /* layered offset pseudo element for 3D stacking effect */
  .card::after{
    content:"";
    position:absolute;
    left:12px; right:12px; bottom:-12px; top:12px;
    border-radius:10px;
    background: linear-gradient(180deg, transparent, rgba(0,0,0,0.18));
    z-index:-1;
    transform: translateY(10px) scale(0.995);
    filter: blur(8px);
    pointer-events:none;
  }

  .card:hover { transform: translateY(-8px); box-shadow: 0 30px 60px rgba(0,0,0,0.7); }

  /* header typography */
  .name {
    font-size:22px;
    font-weight:800;
    letter-spacing:0.4px;
    color: var(--champagne);
    margin:0 0 6px 0;
  }
  .role {
    font-size:13px;
    color: var(--gold-2);
    font-weight:700;
    margin-bottom:8px;
  }
  .tagline {
    font-size:13px;
    color: var(--muted);
    margin-bottom:12px;
    line-height:1.45;
  }

  /* isometric tech grid */
  .tech-iso {
    display:grid;
    grid-template-columns: repeat(auto-fit,minmax(96px,1fr));
    gap:12px;
    transform: translateZ(0);
  }

  .tech-block {
    background: linear-gradient(180deg, rgba(255,255,255,0.012), rgba(255,255,255,0.008));
    border-radius:10px;
    border:1px solid rgba(212,175,55,0.06);
    padding:10px;
    display:flex;
    gap:8px;
    align-items:center;
    box-shadow: 0 10px 20px rgba(0,0,0,0.45);
    transition: transform .28s ease, box-shadow .28s ease;
    transform-origin: left top;
  }
  .tech-block:hover { transform: translateY(-8px) rotateX(4deg); box-shadow: 0 26px 44px rgba(0,0,0,0.6), 0 0 18px rgba(212,175,55,0.06); }

  .tech-logo {
    width:44px; height:44px; display:grid; place-items:center;
    border-radius:8px;
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border:1px solid rgba(255,255,255,0.02);
  }
  .tech-label { font-weight:700; color:var(--platinum); font-size:13px; }

  /* repo showcase: grid of 3D cards */
  .repos {
    display:grid;
    grid-template-columns: repeat(auto-fit,minmax(220px,1fr));
    gap:14px;
    margin-top:12px;
  }
  .repo {
    padding:12px;
    border-radius:10px;
    background: linear-gradient(180deg, rgba(255,255,255,0.018), rgba(255,255,255,0.006));
    border:1px solid rgba(255,255,255,0.02);
    box-shadow: 0 14px 30px rgba(0,0,0,0.48);
    transition: transform .28s ease, box-shadow .28s ease;
  }
  .repo:hover { transform: translateY(-10px) rotateX(3deg); box-shadow: 0 34px 64px rgba(0,0,0,0.7); }

  .repo h4 { margin:0 0 6px 0; font-size:15px; color:var(--champagne); }
  .repo p { margin:0; font-size:13px; color:var(--muted); line-height:1.5; }

  /* status & stats panel */
  .stats-panel {
    display:flex;
    flex-direction:column;
    gap:12px;
    position:relative;
  }

  .stats-glow {
    border-radius:12px;
    padding:12px;
    border:1px solid var(--line);
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.006));
    box-shadow: 0 18px 42px rgba(0,0,0,0.55), 0 0 28px rgba(212,175,55,0.06);
  }

  .stats-glow img { width:100%; border-radius:10px; display:block; }

  .small-note { font-size:12px; color:var(--muted); text-align:center; margin-top:6px; }

  /* floating animation for subtle motion */
  @keyframes floatY {
    0% { transform: translateY(0px); }
    50% { transform: translateY(-6px); }
    100% { transform: translateY(0px); }
  }
  .float { animation: floatY 6s ease-in-out infinite; }

  /* small helpers */
  .muted { color: var(--muted); font-size:13px; }
  .link { color: var(--gold-2); font-weight:700; text-decoration:none; }

  /* compatibility: reduce use of advanced filters for GitHub sanitizer */
  /* keep all transforms, box-shadows, gradients and inline SVGs only */
</style>

<!-- Top geometric wireframe banner (inline SVG, animated glow) -->
<div class="banner" aria-hidden="true">
  <svg viewBox="0 0 1200 220" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="3D geometric banner">
    <defs>
      <linearGradient id="gA" x1="0" x2="1">
        <stop offset="0" stop-color="#ffd86b" stop-opacity="0.95"/>
        <stop offset="1" stop-color="#d4af37" stop-opacity="0.95"/>
      </linearGradient>
      <linearGradient id="gB" x1="0" x2="1">
        <stop offset="0" stop-color="#00d4ff" stop-opacity="0.06"/>
        <stop offset="1" stop-color="#00d4ff" stop-opacity="0.02"/>
      </linearGradient>
      <filter id="soft" x="-20%" y="-20%" width="140%" height="140%">
        <feGaussianBlur stdDeviation="8" result="b"/>
        <feMerge><feMergeNode in="b"/><feMergeNode in="SourceGraphic"/></feMerge>
      </filter>
    </defs>

    <!-- dark background rectangle -->
    <rect width="1200" height="220" fill="url(#gB)" opacity="0.06"/>

    <!-- isometric grid (wireframe) -->
    <g stroke="rgba(255,255,255,0.04)" stroke-width="1" fill="none">
      <!-- horizontal lines -->
      <g opacity="0.28">
        <path d="M40 140 L1160 140" />
        <path d="M20 170 L1180 170" />
        <path d="M80 110 L1120 110" />
      </g>

      <!-- diagonal wireframe (3D grid feel) -->
      <g stroke="rgba(212,175,55,0.06)">
        <path d="M60 190 L360 30 L720 70 L1100 12" stroke-width="1"/>
        <path d="M120 190 L420 30 L780 70 L1160 12" stroke-width="1"/>
      </g>
    </g>

    <!-- floating nodes with glow -->
    <g filter="url(#soft)">
      <circle cx="200" cy="70" r="6" fill="url(#gA)" opacity="0.95" />
      <circle cx="420" cy="60" r="4" fill="#f9d77e" opacity="0.9" />
      <circle cx="760" cy="48" r="5" fill="#d4af37" opacity="0.92" />
      <circle cx="980" cy="86" r="3" fill="#f9d77e" opacity="0.9" />
    </g>

    <!-- minimal title overlay (non-essential for accessibility) -->
    <text x="48" y="46" font-family="Inter, Arial" font-size="18" fill="#f8f1df" font-weight="700">Devisinghd</text>
    <text x="48" y="68" font-family="Inter, Arial" font-size="12" fill="#c8cfcf">Python Backend Developer — Scalable Systems & High‑Quality UX</text>
  </svg>
</div>

<!-- Main layout -->
<div class="layout">

  <!-- LEFT: Hero + repos -->
  <main>
    <!-- Hero / Isometric stack -->
    <div class="hero-stack">
      <!-- Primary hero card (iso) -->
      <div class="card iso-card" style="flex:1;">
        <div class="card-inner">
          <h1 class="name">Dev Dangi</h1>
          <div class="role">Python Backend Developer • Systems & APIs</div>
          <div class="tagline">I build reliable, high-performance platforms with beautiful developer ergonomics — from API design to production-grade deployments.</div>

          <!-- isometric tech grid -->
          <div class="tech-iso" style="margin-top:6px;">
            <!-- Python -->
            <div class="tech-block">
              <div class="tech-logo" aria-hidden="true">
                <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg" role="img"><rect width="64" height="64" rx="10" fill="#306998"/><text x="32" y="40" text-anchor="middle" font-size="20" fill="#fff" font-family="Inter, Arial">Py</text></svg>
              </div>
              <div class="tech-label">Python</div>
            </div>

            <!-- Django -->
            <div class="tech-block">
              <div class="tech-logo" aria-hidden="true">
                <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg"><rect width="64" height="64" rx="10" fill="#092E20"/><text x="32" y="40" text-anchor="middle" font-size="18" fill="#9EE9D3" font-family="Inter">Dj</text></svg>
              </div>
              <div class="tech-label">Django</div>
            </div>

            <!-- FastAPI -->
            <div class="tech-block">
              <div class="tech-logo" aria-hidden="true">
                <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg"><rect width="64" height="64" rx="10" fill="#009688"/><text x="32" y="38" text-anchor="middle" font-size="14" fill="#fff" font-family="Inter">Fast</text></svg>
              </div>
              <div class="tech-label">FastAPI</div>
            </div>

            <!-- React -->
            <div class="tech-block">
              <div class="tech-logo" aria-hidden="true">
                <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg"><rect width="64" height="64" rx="10" fill="#20232A"/><g transform="translate(8,8)" fill="none" stroke="#61DAFB" stroke-width="2"><ellipse cx="24" cy="24" rx="11" ry="20"/><ellipse cx="24" cy="24" rx="11" ry="20" transform="rotate(60 24 24)"/><ellipse cx="24" cy="24" rx="11" ry="20" transform="rotate(120 24 24)"/></g></svg>
              </div>
              <div class="tech-label">React</div>
            </div>

            <!-- TypeScript -->
            <div class="tech-block">
              <div class="tech-logo" aria-hidden="true">
                <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg"><rect width="64" height="64" rx="10" fill="#3178C6"/><text x="32" y="40" text-anchor="middle" font-size="18" fill="#fff" font-family="Inter">TS</text></svg>
              </div>
              <div class="tech-label">TypeScript</div>
            </div>

            <!-- Tailwind -->
            <div class="tech-block">
              <div class="tech-logo" aria-hidden="true">
                <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg"><rect width="64" height="64" rx="10" fill="#06B6D4"/><path d="M12 38c10-12 20-12 30-4 10 8 18 8 24 4" stroke="#022D3A" stroke-width="2.6" fill="none" stroke-linecap="round"/></svg>
              </div>
              <div class="tech-label">Tailwind</div>
            </div>

            <!-- Postgres -->
            <div class="tech-block">
              <div class="tech-logo" aria-hidden="true">
                <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg"><rect width="64" height="64" rx="10" fill="#316192"/><text x="32" y="40" text-anchor="middle" font-size="14" fill="#EAF5FF" font-family="Inter">PG</text></svg>
              </div>
              <div class="tech-label">Postgres</div>
            </div>

            <!-- Redis -->
            <div class="tech-block">
              <div class="tech-logo" aria-hidden="true">
                <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg"><rect width="64" height="64" rx="10" fill="#DC382D"/><g fill="#fff" opacity="0.9"><ellipse cx="32" cy="20" rx="18" ry="6"/><ellipse cx="32" cy="34" rx="14" ry="5"/><ellipse cx="32" cy="46" rx="10" ry="4"/></g></svg>
              </div>
              <div class="tech-label">Redis</div>
            </div>

            <!-- Docker -->
            <div class="tech-block">
              <div class="tech-logo" aria-hidden="true">
                <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg"><rect width="64" height="64" rx="10" fill="#2496ED"/><g fill="#fff" opacity="0.9"><rect x="7" y="28" width="16" height="9" rx="2"/><rect x="25" y="22" width="16" height="9" rx="2"/><rect x="43" y="28" width="14" height="9" rx="2"/></g></svg>
              </div>
              <div class="tech-label">Docker</div>
            </div>
          </div>
        </div>
      </div>

      <!-- Secondary floating card (short profile summary) -->
      <div class="card float" style="width:260px; transform: translateZ(0) skewY(-6deg);">
        <div class="card-inner">
          <div class="role">Core Philosophy</div>
          <div class="tagline">Deliver minimal, resilient systems — optimize for reliability, observability, and delightful developer experience.</div>
          <div style="margin-top:10px;" class="muted">Available for backend engineering, architectural reviews, and SaaS collaborations.</div>
        </div>
      </div>
    </div>

    <!-- Repositories showcase -->
    <section style="margin-top:18px;">
      <div style="display:flex;align-items:center;gap:12px;margin-bottom:10px;">
        <h3 style="margin:0;font-size:16px;color:var(--champagne)">Repository Showcase</h3>
        <div class="muted" style="font-size:13px;">Selected projects • hover to preview</div>
      </div>

      <div class="repos">
        <a class="repo" href="https://github.com/Devisinghd/NovaChat-Social-App" target="_blank" rel="noreferrer">
          <h4>NovaChat — Social App</h4>
          <p>Realtime messaging, modern auth flows, scalable notification pipelines, and beautiful UX components.</p>
        </a>

        <a class="repo" href="https://github.com/Devisinghd/Example-API-Project" target="_blank" rel="noreferrer">
          <h4>Example API — Production-ready</h4>
          <p>Opinionated API architecture with FastAPI, background workers, and SMS/email integrations for production systems.</p>
        </a>

        <a class="repo" href="https://github.com/Devisinghd/Tooling" target="_blank" rel="noreferrer">
          <h4>Infra Tooling & CI</h4>
          <p>Docker stacks, GitHub Actions workflows, and reproducible dev environments for fast iteration.</p>
        </a>
      </div>
    </section>
  </main>

  <!-- RIGHT: Stats & status -->
  <aside>
    <div class="stats-panel">
      <div class="stats-glow">
        <div style="display:flex;align-items:center;justify-content:space-between;">
          <div>
            <div style="font-weight:800;color:var(--champagne);">Status & Stats</div>
            <div class="muted" style="margin-top:4px;">Live metrics — updated automatically</div>
          </div>
          <div style="font-weight:700;color:var(--gold);">Devisinghd</div>
        </div>

        <div style="margin-top:12px;display:grid;gap:8px;">
          <!-- GitHub Readme Stats (dark/gold theme) -->
          <img src="https://github-readme-stats.vercel.app/api?username=Devisinghd&show_icons=true&hide_border=true&bg_color=0b0b0b&title_color=FFD86B&icon_color=FFD86B&text_color=E7E7E9" alt="GitHub Stats for Devisinghd" />

          <!-- Top languages -->
          <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Devisinghd&layout=compact&hide_border=true&bg_color=0b0b0b&title_color=FFD86B&text_color=E7E7E9" alt="Top languages for Devisinghd" />

          <!-- Streak / activity -->
          <img src="https://github-readme-streak-stats.herokuapp.com/?user=Devisinghd&theme=dark&hide_border=true&background=0b0b0b&ring=FFD86B&fire=FFD86B" alt="GitHub Streak" style="border-radius:8px;" />
        </div>

        <div class="small-note">Tip: Swap the readme-stats params (title_color, bg_color) to perfectly match the palette.</div>
      </div>

      <div class="card" style="margin-top:12px;">
        <div style="display:flex;align-items:center;justify-content:space-between;">
          <div>
            <div style="font-weight:800;color:var(--champagne)">Connect</div>
            <div class="muted" style="margin-top:4px;">Open to collaborations & mentorship</div>
          </div>
          <div style="text-align:right;">
            <div style="font-weight:700;color:var(--gold)">Open to Work</div>
            <div class="muted" style="font-size:12px;margin-top:4px;">Django • FastAPI • SaaS</div>
          </div>
        </div>

        <div style="margin-top:12px;display:flex;gap:8px;flex-wrap:wrap;">
          <a class="link" href="https://github.com/Devisinghd" target="_blank" rel="noreferrer">GitHub</a>
          <a class="link" href="mailto:devisinghdangi786@gmail.com">Email</a>
          <a class="link" href="https://www.linkedin.com/in/your-linkedin" target="_blank" rel="noreferrer">LinkedIn</a>
          <a class="link" href="https://x.com/your-handle" target="_blank" rel="noreferrer">X</a>
        </div>
      </div>

      <div class="card" style="margin-top:12px;">
        <div style="font-weight:800;color:var(--champagne);margin-bottom:8px;">Core Pillars</div>
        <div style="display:grid;gap:8px;">
          <div style="display:flex;gap:10px;align-items:flex-start;">
            <div style="width:8px;height:8px;background:var(--gold);border-radius:2px;margin-top:6px;"></div>
            <div>
              <div style="font-weight:700;color:var(--platinum);">Architecture</div>
              <div class="muted">Modular, secure design with clear domain boundaries.</div>
            </div>
          </div>

          <div style="display:flex;gap:10px;align-items:flex-start;">
            <div style="width:8px;height:8px;background:var(--gold);border-radius:2px;margin-top:6px;"></div>
            <div>
              <div style="font-weight:700;color:var(--platinum);">Scalability</div>
              <div class="muted">Horizontal scaling, caching strategies, and observability.</div>
            </div>
          </div>

          <div style="display:flex;gap:10px;align-items:flex-start;">
            <div style="width:8px;height:8px;background:var(--gold);border-radius:2px;margin-top:6px;"></div>
            <div>
              <div style="font-weight:700;color:var(--platinum);">Design</div>
              <div class="muted">Accessibility-first UI and careful motion for premium feel.</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </aside>
</div>

<!-- Footer -->
<div style="margin-top:18px;text-align:center;color:var(--muted);font-size:13px;">
  Crafted with a premium glassmorphism aesthetic • Dark charcoal • Gold accents • Built for clarity and scale
</div>

</div>
