<div class="luxury-root">

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
    --line: rgba(212,175,55,0.18);
    --shadow: rgba(0,0,0,0.6);
  }

  .luxury-root{
    max-width: 1100px;
    margin: 26px auto;
    padding: 28px 18px 20px;
    border-radius: 18px;
    background:
      radial-gradient(circle at top, rgba(212,175,55,0.07), transparent 26%),
      linear-gradient(180deg, rgba(17,18,20,0.96), rgba(8,8,10,0.98));
    border: 1px solid rgba(255,255,255,0.04);
    box-shadow:
      0 0 0 1px rgba(255,255,255,0.02),
      0 16px 52px rgba(0,0,0,0.8),
      inset 0 1px 0 rgba(255,255,255,0.02);
    position: relative;
    overflow: hidden;
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    color: var(--platinum);
  }

  .luxury-root::before{
    content:"";
    position:absolute;
    inset:-35% auto auto -10%;
    width:420px; height:420px;
    background: radial-gradient(circle, rgba(212,175,55,0.18), transparent 62%);
    filter: blur(30px);
    pointer-events:none;
  }

  .luxury-root::after{
    content:"";
    position:absolute;
    right:-10%; bottom:-20%;
    width:420px; height:420px;
    background: radial-gradient(circle, rgba(255,255,255,0.08), transparent 60%);
    filter: blur(28px);
    pointer-events:none;
  }

  a{
    color: var(--gold-2);
    text-decoration: none;
  }

  a:hover{
    text-decoration: underline;
  }

  .hero{
    display:grid;
    grid-template-columns: 1fr auto;
    gap: 18px;
    align-items:center;
    margin-bottom: 22px;
  }

  .hero-svg{
    width:100%;
    max-width: 780px;
    height: 110px;
    display:block;
    filter: drop-shadow(0 0 18px rgba(212,175,55,0.18));
  }

  .glint{
    position: relative;
    overflow: visible;
  }

  .glint::after{
    content:"";
    position:absolute;
    left:-30%;
    top:-54%;
    width:40%;
    height:220%;
    transform: skewX(-20deg);
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.12), transparent);
    animation: shimmer 7s ease-in-out infinite;
    pointer-events:none;
  }

  @keyframes shimmer{
    0% { left:-35%; opacity:0; }
    20% { opacity:1; }
    55% { left:120%; opacity:1; }
    100% { left:120%; opacity:0; }
  }

  .status-card{
    min-width: 330px;
    background: linear-gradient(180deg, rgba(255,255,255,0.024), rgba(255,255,255,0.01));
    border: 1px solid var(--line);
    border-radius: 16px;
    padding: 12px 14px;
    box-shadow:
      0 0 0 1px rgba(255,255,255,0.02),
      0 18px 42px rgba(0,0,0,0.5),
      inset 0 1px 0 rgba(255,255,255,0.05);
    position: relative;
    transition: transform .34s ease, box-shadow .34s ease;
  }

  .status-card:hover{
    transform: translateY(-4px);
    box-shadow:
      0 0 0 1px rgba(255,255,255,0.02),
      0 28px 58px rgba(0,0,0,0.72),
      0 0 18px rgba(212,175,55,0.1);
  }

  .status-card::before{
    content:"";
    position:absolute;
    inset:-8px;
    border-radius:18px;
    background: linear-gradient(90deg, rgba(212,175,55,0.08), transparent, rgba(255,255,255,0.05));
    filter: blur(14px);
    z-index:-1;
  }

  .status-row{
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:14px;
  }

  .status-left{
    display:flex;
    align-items:center;
    gap:12px;
    flex:1;
  }

  .crest{
    width:42px; height:42px;
    display:grid; place-items:center;
    border-radius:12px;
    background: linear-gradient(180deg, rgba(255,255,255,0.04), rgba(255,255,255,0.015));
    border:1px solid rgba(255,255,255,0.03);
    box-shadow: inset 0 1px 0 rgba(255,255,255,0.04);
  }

  .status-tag{
    font-size:12px;
    letter-spacing:0.12em;
    color: var(--gold-2);
    text-transform: uppercase;
    margin-bottom:4px;
    opacity:0.9;
  }

  .status-text{
    font-size:13px;
    color: var(--platinum);
    font-weight: 600;
    line-height:1.4;
  }

  .status-meta{
    font-size:11px;
    color: var(--muted);
    margin-top:2px;
  }

  .live-pill{
    padding: 7px 10px;
    border-radius: 999px;
    background: linear-gradient(180deg, rgba(212,175,55,0.12), rgba(255,255,255,0.02));
    border:1px solid rgba(212,175,55,0.12);
    color: var(--gold-2);
    font-size:11px;
    font-weight:700;
    letter-spacing:0.08em;
    text-transform: uppercase;
    white-space: nowrap;
  }

  .grid{
    display:grid;
    grid-template-columns: 1.2fr 0.8fr;
    gap:18px;
    align-items:start;
  }

  .card{
    background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.015));
    border: 1px solid rgba(255,255,255,0.04);
    border-radius: 16px;
    padding: 18px 18px 16px;
    box-shadow:
      0 12px 30px rgba(0,0,0,0.42),
      inset 0 1px 0 rgba(255,255,255,0.04);
    position: relative;
    overflow: hidden;
  }

  .card::before{
    content:"";
    position:absolute; inset:0;
    background: linear-gradient(120deg, rgba(255,255,255,0.05), transparent 18%, transparent 82%, rgba(255,255,255,0.02));
    pointer-events:none;
  }

  .title{
    position: relative;
    display:flex;
    align-items:center;
    gap:12px;
    margin-bottom: 10px;
    z-index:1;
  }

  .title h3{
    margin:0;
    font-size: 17px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--platinum);
  }

  .rule{
    height: 1px;
    background: linear-gradient(90deg, rgba(212,175,55,0.30), rgba(255,255,255,0.04));
    margin: 6px 0 12px;
  }

  .about-body{
    font-size: 14px;
    color: var(--muted);
    line-height:1.72;
    position: relative;
    z-index:1;
  }

  .profile-points{
    margin-top: 10px;
    padding-left: 18px;
    color: var(--muted);
    line-height:1.8;
  }

  .profile-points li::marker{
    color: var(--gold-2);
  }

  .stack{
    display:grid;
    grid-template-columns: repeat(auto-fit, minmax(110px,1fr));
    gap: 12px;
    position: relative;
    z-index:1;
  }

  .badge{
    display:flex;
    align-items:center;
    gap:10px;
    min-height: 62px;
    padding: 8px 10px;
    border-radius: 12px;
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border: 1px solid rgba(212,175,55,0.08);
    box-shadow:
      0 10px 18px rgba(0,0,0,0.18),
      inset 0 1px 0 rgba(255,255,255,0.04);
    transition: transform .3s ease, box-shadow .3s ease, border-color .3s ease;
  }

  .badge:hover{
    transform: translateY(-6px);
    border-color: rgba(212,175,55,0.18);
    box-shadow:
      0 20px 28px rgba(0,0,0,0.3),
      0 0 18px rgba(212,175,55,0.08);
  }

  .logo-box{
    width: 46px; height: 46px;
    display:grid; place-items:center;
    border-radius: 10px;
    background: linear-gradient(180deg, rgba(255,255,255,0.04), rgba(255,255,255,0.015));
    border: 1px solid rgba(255,255,255,0.03);
    box-shadow: inset 0 1px 0 rgba(255,255,255,0.04);
  }

  .logo-box svg{
    width: 38px; height: 38px;
    display:block;
  }

  .badge-name{
    font-size: 12px;
    font-weight: 700;
    color: var(--platinum);
    letter-spacing: 0.04em;
  }

  .pillars{
    display:grid;
    grid-template-columns: repeat(3,1fr);
    gap: 12px;
    margin-top: 14px;
    position: relative;
    z-index:1;
  }

  .pillar{
    text-align:center;
    padding: 16px 10px 12px;
    border-radius: 14px;
    background: linear-gradient(180deg, rgba(255,255,255,0.022), rgba(255,255,255,0.01));
    border: 1px solid rgba(212,175,55,0.08);
    box-shadow: inset 0 1px 0 rgba(255,255,255,0.04);
    transition: transform .3s ease, box-shadow .3s ease, border-color .3s ease;
  }

  .pillar:hover{
    transform: translateY(-4px);
    border-color: rgba(212,175,55,0.18);
    box-shadow: 0 18px 32px rgba(0,0,0,0.3);
  }

  .pillar h4{
    margin: 12px 0 6px;
    font-size: 14px;
    color: var(--platinum);
  }

  .pillar p{
    margin:0;
    font-size: 12px;
    line-height:1.5;
    color: var(--muted);
  }

  .stats-box{
    display:flex;
    flex-direction:column;
    gap: 10px;
    position: relative;
    z-index:1;
  }

  .stats-box img{
    width:100%;
    border-radius: 12px;
    border:1px solid rgba(255,255,255,0.04);
    box-shadow: 0 12px 28px rgba(0,0,0,0.45);
  }

  .connect{
    display:flex;
    flex-wrap:wrap;
    justify-content:center;
    gap:10px;
    margin-top: 14px;
    position: relative;
    z-index:1;
  }

  .chip{
    display:inline-flex;
    align-items:center;
    justify-content:center;
    padding: 8px 12px;
    border-radius: 999px;
    background: linear-gradient(180deg, rgba(212,175,55,0.08), rgba(255,255,255,0.02));
    border: 1px solid rgba(212,175,55,0.12);
    color: var(--platinum);
    font-size:12px;
    font-weight:600;
    transition: transform .25s ease, box-shadow .25s ease;
  }

  .chip:hover{
    transform: translateY(-2px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.2), 0 0 16px rgba(212,175,55,0.1);
  }

  .footer-note{
    margin-top: 18px;
    text-align:center;
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 0.04em;
  }

  @media (max-width: 980px){
    .hero{
      grid-template-columns: 1fr;
    }
    .status-card{
      min-width: 0;
      width: 100%;
    }
    .grid{
      grid-template-columns: 1fr;
    }
  }

  @media (max-width: 720px){
    .pillars{
      grid-template-columns: 1fr;
    }
    .status-row{
      flex-direction: column;
      align-items:flex-start;
    }
  }
</style>

<div class="hero">
  <div class="glint">
    <svg class="hero-svg" viewBox="0 0 1200 140" xmlns="http://www.w3.org/2000/svg" aria-label="Dev Dangi premium banner">
      <defs>
        <linearGradient id="goldHead" x1="0" x2="1">
          <stop offset="0%" stop-color="#fff4d9"/>
          <stop offset="28%" stop-color="#f8df9a"/>
          <stop offset="58%" stop-color="#d4af37"/>
          <stop offset="100%" stop-color="#8a6b1c"/>
        </linearGradient>
        <filter id="goldGlow">
          <feGaussianBlur stdDeviation="5" result="blur"/>
          <feMerge>
            <feMergeNode in="blur"/>
            <feMergeNode in="SourceGraphic"/>
          </feMerge>
        </filter>
      </defs>

      <text x="42" y="90" fill="#050607" font-size="72" font-weight="700" font-family="Georgia, 'Times New Roman', serif" opacity="0.9" transform="translate(0,6)">Dev Dangi</text>
      <text x="44" y="88" fill="#0a0b0c" font-size="72" font-weight="700" font-family="Georgia, 'Times New Roman', serif" opacity="0.75" transform="translate(0,3)">Dev Dangi</text>
      <text x="44" y="86" fill="url(#goldHead)" font-size="72" font-weight="700" font-family="Georgia, 'Times New Roman', serif" filter="url(#goldGlow)">Dev Dangi</text>

      <text x="46" y="116" fill="#9ea7b4" font-size="18" font-weight="700" font-family="Segoe UI, sans-serif" letter-spacing="1.6">FULL STACK DEVELOPER • PYTHON • DJANGO • SCALABLE SYSTEMS</text>
    </svg>
  </div>

  <div class="status-card">
    <div class="status-row">
      <div class="status-left">
        <div class="crest">
          <svg width="22" height="22" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <defs>
              <linearGradient id="goldCrest" x1="0" x2="1">
                <stop offset="0%" stop-color="#f9d77e"/>
                <stop offset="100%" stop-color="#d4af37"/>
              </linearGradient>
            </defs>
            <rect x="1" y="1" width="22" height="22" rx="6" fill="#0d0d10" stroke="rgba(255,255,255,0.05)"/>
            <path d="M5 15 L9 9 L13 14 L19 7" stroke="url(#goldCrest)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>

        <div>
          <div class="status-tag">Status</div>
          <div class="status-text">Crafting Digital Luxury & High-Performance Code</div>
          <div class="status-meta">Django • FastAPI • SaaS • Design-Led Products</div>
        </div>
      </div>

      <div class="live-pill">Building NovaChat</div>
    </div>
  </div>
</div>

<div class="grid">
  <div>
    <div class="card">
      <div class="title">
        <svg width="26" height="26" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <rect x="2" y="2" width="20" height="20" rx="5" fill="#111214" stroke="rgba(212,175,55,0.18)"/>
          <path d="M7 13 L11 8 L17 16" stroke="url(#goldIconA)" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/>
          <defs>
            <linearGradient id="goldIconA" x1="0" x2="1"><stop offset="0%" stop-color="#f9d77e"/><stop offset="100%" stop-color="#d4af37"/></linearGradient>
          </defs>
        </svg>
        <h3>About Me</h3>
      </div>

      <div class="rule"></div>

      <div class="about-body">
        I’m Dev Dangi — a full stack developer focused on building polished digital products that feel premium, perform fast, and scale with confidence. I work across backend architecture, API systems, and product-driven frontend experiences.
        <ul class="profile-points">
          <li>Strong in Python, Django, FastAPI, and scalable backend design</li>
          <li>Frontend engineering with React, TypeScript, and modern UI systems</li>
          <li>Building SaaS products, internal tools, and product experiences with real-world impact</li>
        </ul>
      </div>
    </div>

    <div class="card" style="margin-top: 14px;">
      <div class="title">
        <svg width="26" height="26" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <rect x="2" y="2" width="20" height="20" rx="5" fill="#111214" stroke="rgba(212,175,55,0.18)"/>
          <path d="M6 8h12M6 12h12M6 16h8" stroke="rgba(255,255,255,0.3)" stroke-width="1.5" stroke-linecap="round"/>
        </svg>
        <h3>Tech Stack</h3>
      </div>

      <div class="rule"></div>

      <div class="stack">
        <div class="badge">
          <div class="logo-box">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
              <defs>
                <linearGradient id="pyGrad" x1="0" x2="1">
                  <stop offset="0%" stop-color="#3d8bd1"/>
                  <stop offset="100%" stop-color="#2d6bab"/>
                </linearGradient>
              </defs>
              <rect width="48" height="48" rx="10" fill="url(#pyGrad)"/>
              <text x="24" y="30" font-size="18" font-weight="700" text-anchor="middle" fill="#fff" font-family="Segoe UI, sans-serif">Py</text>
            </svg>
          </div>
          <div class="badge-name">Python</div>
        </div>

        <div class="badge">
          <div class="logo-box">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
              <rect width="48" height="48" rx="10" fill="#0b2f25"/>
              <text x="24" y="31" font-size="13" font-weight="700" text-anchor="middle" fill="#9ee9d3" font-family="Segoe UI, sans-serif">Dj</text>
            </svg>
          </div>
          <div class="badge-name">Django</div>
        </div>

        <div class="badge">
          <div class="logo-box">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
              <rect width="48" height="48" rx="10" fill="#009688"/>
              <text x="24" y="31" font-size="12" font-weight="700" text-anchor="middle" fill="#fff" font-family="Segoe UI, sans-serif">Fast</text>
            </svg>
          </div>
          <div class="badge-name">FastAPI</div>
        </div>

        <div class="badge">
          <div class="logo-box">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
              <rect width="48" height="48" rx="10" fill="#20232A"/>
              <g fill="none" stroke="#61dafb" stroke-width="1.8">
                <ellipse cx="24" cy="24" rx="11" ry="20" transform="rotate(0 24 24)"/>
                <ellipse cx="24" cy="24" rx="11" ry="20" transform="rotate(60 24 24)"/>
                <ellipse cx="24" cy="24" rx="11" ry="20" transform="rotate(120 24 24)"/>
              </g>
            </svg>
          </div>
          <div class="badge-name">React</div>
        </div>

        <div class="badge">
          <div class="logo-box">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
              <rect width="48" height="48" rx="10" fill="#3178C6"/>
              <text x="24" y="31" font-size="14" font-weight="700" text-anchor="middle" fill="#fff" font-family="Segoe UI, sans-serif">TS</text>
            </svg>
          </div>
          <div class="badge-name">TypeScript</div>
        </div>

        <div class="badge">
          <div class="logo-box">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
              <rect width="48" height="48" rx="10" fill="#06B6D4"/>
              <path d="M6 30c8-10 14-11 20-4 7 8 12 8 16 3" stroke="#022d3a" stroke-width="2.2" fill="none" stroke-linecap="round"/>
            </svg>
          </div>
          <div class="badge-name">Tailwind</div>
        </div>

        <div class="badge">
          <div class="logo-box">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
              <rect width="48" height="48" rx="10" fill="#316192"/>
              <text x="24" y="31" font-size="12" font-weight="700" text-anchor="middle" fill="#EAF5FF" font-family="Segoe UI, sans-serif">PG</text>
            </svg>
          </div>
          <div class="badge-name">Postgres</div>
        </div>

        <div class="badge">
          <div class="logo-box">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
              <rect width="48" height="48" rx="10" fill="#DC382D"/>
              <g fill="#fff" opacity="0.9">
                <ellipse cx="24" cy="14" rx="12" ry="4"/>
                <ellipse cx="24" cy="22" rx="10" ry="3"/>
                <ellipse cx="24" cy="30" rx="8" ry="2.5"/>
              </g>
            </svg>
          </div>
          <div class="badge-name">Redis</div>
        </div>

        <div class="badge">
          <div class="logo-box">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
              <rect width="48" height="48" rx="10" fill="#2496ED"/>
              <g fill="#fff" opacity="0.9">
                <rect x="6" y="20" width="18" height="9" rx="2"/>
                <rect x="18" y="15" width="16" height="9" rx="2"/>
                <rect x="30" y="20" width="14" height="9" rx="2"/>
              </g>
            </svg>
          </div>
          <div class="badge-name">Docker</div>
        </div>

        <div class="badge">
          <div class="logo-box">
            <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
              <rect width="48" height="48" rx="10" fill="#0b0b0b"/>
              <g fill="#2088FF">
                <circle cx="16" cy="22" r="5"/>
                <circle cx="32" cy="22" r="5"/>
                <rect x="18" y="20" width="12" height="4" rx="2"/>
              </g>

