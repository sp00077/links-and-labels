# links-and-labels
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Links & Labels – Smart RFID Asset Tagging</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      --primary: #0052cc;
      --primary-dark: #003c99;
      --accent: #ffb100;
      --bg: #f5f7fb;
      --text: #1b2330;
      --muted: #6b7280;
      --radius: 10px;
      --shadow-soft: 0 16px 40px rgba(15, 23, 42, 0.12);
      --transition-fast: 0.18s ease-out;
      --transition-med: 0.28s ease-out;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.6;
      scroll-behavior: smooth;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    img {
      max-width: 100%;
      display: block;
    }

    /* Layout */

    header {
      position: sticky;
      top: 0;
      z-index: 20;
      backdrop-filter: blur(12px);
      background: rgba(245, 247, 251, 0.9);
      border-bottom: 1px solid rgba(148, 163, 184, 0.2);
    }

    .nav {
      max-width: 1120px;
      margin: 0 auto;
      padding: 0.9rem 1.25rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1.5rem;
    }

    .logo {
      display: flex;
      align-items: center;
      gap: 0.55rem;
      font-weight: 700;
      font-size: 1.1rem;
      letter-spacing: 0.02em;
    }

    .logo-mark {
      width: 32px;
      height: 32px;
      border-radius: 999px;
      background: radial-gradient(circle at 30% 30%, #fff, #0f172a);
      display: grid;
      place-items: center;
      color: #fff;
      font-size: 0.8rem;
      box-shadow: 0 10px 25px rgba(15, 23, 42, 0.35);
    }

    .nav-links {
      display: flex;
      gap: 1.5rem;
      font-size: 0.95rem;
      color: var(--muted);
    }

    .nav-links a {
      position: relative;
      padding-bottom: 2px;
      transition: color var(--transition-fast);
    }

    .nav-links a::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: 0;
      width: 0;
      height: 2px;
      border-radius: 999px;
      background: var(--primary);
      transition: width var(--transition-fast);
    }

    .nav-links a:hover {
      color: var(--text);
    }

    .nav-links a:hover::after {
      width: 100%;
    }

    .nav-cta {
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.4rem;
      padding: 0.6rem 1.2rem;
      border-radius: 999px;
      font-size: 0.95rem;
      font-weight: 600;
      border: none;
      cursor: pointer;
      transition: transform var(--transition-fast), box-shadow var(--transition-fast),
        background var(--transition-fast), color var(--transition-fast);
    }

    .btn-primary {
      background: radial-gradient(circle at 10% 0, #3b82f6, var(--primary-dark));
      color: #fff;
      box-shadow: 0 14px 30px rgba(37, 99, 235, 0.35);
    }

    .btn-primary:hover {
      transform: translateY(-1px) scale(1.02);
      box-shadow: 0 20px 40px rgba(37, 99, 235, 0.45);
    }

    .btn-outline {
      background: rgba(255, 255, 255, 0.7);
      border: 1px solid rgba(148, 163, 184, 0.4);
      color: var(--text);
    }

    .btn-outline:hover {
      background: #fff;
      transform: translateY(-1px);
      box-shadow: 0 10px 25px rgba(148, 163, 184, 0.4);
    }

    main {
      max-width: 1120px;
      margin: 0 auto;
      padding: 1.8rem 1.25rem 4rem;
    }

    section {
      margin-top: 3.5rem;
    }

    .section-label {
      text-transform: uppercase;
      font-size: 0.8rem;
      letter-spacing: 0.16em;
      color: var(--accent);
      font-weight: 600;
      margin-bottom: 0.5rem;
    }

    .section-title {
      font-size: clamp(1.7rem, 3vw, 2.1rem);
      margin-bottom: 0.75rem;
    }

    .section-subtitle {
      font-size: 0.98rem;
      color: var(--muted);
      max-width: 620px;
    }

    /* Hero */

    .hero {
      display: grid;
      grid-template-columns: minmax(0, 1.3fr) minmax(0, 1.1fr);
      gap: 1.75rem;
      align-items: center;
      margin-top: 2.5rem;
    }

    .hero-heading {
      font-size: clamp(2.1rem, 4vw, 2.7rem);
      line-height: 1.1;
      margin-bottom: 0.8rem;
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 0.35rem;
      padding: 0.2rem 0.6rem;
      border-radius: 999px;
      border: 1px solid rgba(59, 130, 246, 0.35);
      background: rgba(239, 246, 255, 0.9);
      color: #1d4ed8;
      font-size: 0.8rem;
      margin-bottom: 0.7rem;
    }

    .hero-p {
      color: var(--muted);
      margin-bottom: 1.2rem;
      font-size: 0.98rem;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 0.7rem;
      margin-bottom: 1.1rem;
    }

    .hero-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 1.2rem;
      font-size: 0.85rem;
      color: var(--muted);
    }

    .hero-meta span {
      display: inline-flex;
      align-items: center;
      gap: 0.35rem;
    }

    .hero-visual {
      position: relative;
      border-radius: 24px;
      padding: 1.1rem;
      background: radial-gradient(circle at 0 0, #eff6ff 0, #e0ecff 33%, #eef2ff 100%);
      box-shadow: var(--shadow-soft);
      overflow: hidden;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 0.6rem;
    }

    .asset-card {
      border-radius: 12px;
      padding: 0.6rem;
      background: rgba(255, 255, 255, 0.9);
      box-shadow: 0 10px 25px rgba(15, 23, 42, 0.08);
      font-size: 0.75rem;
      display: flex;
      flex-direction: column;
      gap: 0.22rem;
      transform-origin: center;
      transition: transform var(--transition-med), box-shadow var(--transition-med),
        background var(--transition-fast);
    }

    .asset-card:hover {
      transform: translateY(-3px) scale(1.03);
      box-shadow: 0 16px 35px rgba(15, 23, 42, 0.16);
      background: #fff;
    }

    .asset-tag-pill {
      display: inline-flex;
      align-items: center;
      gap: 0.25rem;
      padding: 0.1rem 0.45rem;
      border-radius: 999px;
      background: rgba(37, 99, 235, 0.08);
      color: #1d4ed8;
      font-size: 0.7rem;
      font-weight: 600;
    }

    .asset-label {
      font-weight: 600;
    }

    .asset-meta {
      font-size: 0.7rem;
      color: var(--muted);
    }

    .hero-orbit {
      position: absolute;
      inset: -40%;
      background: radial-gradient(circle at 50% 20%, rgba(59, 130, 246, 0.12), transparent 60%);
      opacity: 0.85;
      pointer-events: none;
      animation: heroGlow 12s linear infinite alternate;
    }

    .hero-badge-floating {
      position: absolute;
      bottom: 0.7rem;
      right: 0.9rem;
      background: #0f172a;
      color: #e5e7eb;
      font-size: 0.75rem;
      padding: 0.4rem 0.7rem;
      border-radius: 999px;
      display: inline-flex;
      align-items: center;
      gap: 0.35rem;
      box-shadow: 0 12px 26px rgba(15, 23, 42, 0.45);
      opacity: 0.97;
    }

    @keyframes heroGlow {
      0% {
        transform: translate3d(-4px, -6px, 0) scale(1);
      }
      100% {
        transform: translate3d(4px, 4px, 0) scale(1.02);
      }
    }

    /* Process section */

    .process-grid {
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: 1rem;
      margin-top: 1.6rem;
    }

    .step-card {
      background: #fff;
      border-radius: 16px;
      padding: 1rem;
      box-shadow: 0 12px 30px rgba(15, 23, 42, 0.08);
      font-size: 0.9rem;
      position: relative;
      overflow: hidden;
      transition: transform var(--transition-med), box-shadow var(--transition-med);
    }

    .step-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 18px 40px rgba(15, 23, 42, 0.15);
    }

    .step-number {
      width: 28px;
      height: 28px;
      border-radius: 999px;
      display: grid;
      place-items: center;
      background: rgba(37, 99, 235, 0.1);
      color: #1d4ed8;
      font-size: 0.8rem;
      font-weight: 600;
      margin-bottom: 0.3rem;
    }

    .step-title {
      font-weight: 600;
      margin-bottom: 0.25rem;
    }

    .step-meta {
      font-size: 0.8rem;
      color: var(--muted);
    }

    /* Demo videos */

    .demo-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.1fr) minmax(0, 1.1fr);
      gap: 1rem;
      margin-top: 1.7rem;
      align-items: stretch;
    }

    .demo-card {
      background: #0f172a;
      color: #e5e7eb;
      border-radius: 18px;
      padding: 0.85rem;
      box-shadow: 0 16px 36px rgba(15, 23, 42, 0.6);
      position: relative;
      overflow: hidden;
    }

    .demo-inner {
      border-radius: 14px;
      background: radial-gradient(circle at 10% 0, #1e293b, #020617);
      padding: 0.8rem;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .demo-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 0.5rem;
      font-size: 0.9rem;
      font-weight: 500;
    }

    .demo-chip {
      font-size: 0.7rem;
      padding: 0.12rem 0.5rem;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.8);
      border: 1px solid rgba(148, 163, 184, 0.6);
    }

    .demo-video-placeholder {
      flex: 1;
      border-radius: 12px;
      background: conic-gradient(from 190deg, #1d4ed8, #22c55e, #eab308, #1d4ed8);
      padding: 2px;
      margin-bottom: 0.5rem;
      position: relative;
    }

    .demo-video-inner {
      border-radius: 10px;
      background: radial-gradient(circle at 10% 0, #020617, #1f2937);
      height: 100%;
      min-height: 170px;
      display: grid;
      place-items: center;
      position: relative;
      overflow: hidden;
    }

    .play-button {
      width: 56px;
      height: 56px;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.9);
      border: 2px solid rgba(248, 250, 252, 0.8);
      display: grid;
      place-items: center;
      cursor: pointer;
      transition: transform var(--transition-med), background var(--transition-med),
        box-shadow var(--transition-med);
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.7);
    }

    .play-button:hover {
      transform: scale(1.04) translateY(-2px);
      background: rgba(30, 64, 175, 0.95);
      box-shadow: 0 24px 55px rgba(37, 99, 235, 0.8);
    }

    .play-button::before {
      content: "";
      border-style: solid;
      border-width: 7px 0 7px 12px;
      border-color: transparent transparent transparent #e5e7eb;
      margin-left: 2px;
    }

    .demo-caption {
      font-size: 0.78rem;
      color: #9ca3af;
    }

    /* Customer stories */

    .stories-strip {
      margin-top: 1.5rem;
      display: flex;
      gap: 1rem;
      overflow-x: auto;
      padding-bottom: 0.6rem;
      scroll-snap-type: x mandatory;
    }

    .story-card {
      min-width: 260px;
      max-width: 320px;
      background: #fff;
      border-radius: 18px;
      padding: 1rem;
      box-shadow: 0 18px 40px rgba(15, 23, 42, 0.14);
      scroll-snap-align: center;
      position: relative;
      overflow: hidden;
      transition: transform var(--transition-med), box-shadow var(--transition-med);
    }

    .story-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 24px 55px rgba(15, 23, 42, 0.22);
    }

    .story-industry {
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.14em;
      color: var(--accent);
      margin-bottom: 0.35rem;
      font-weight: 600;
    }

    .story-metric {
      font-size: 0.9rem;
      font-weight: 600;
      margin-bottom: 0.1rem;
    }

    .story-body {
      font-size: 0.85rem;
      color: var(--muted);
      margin-bottom: 0.5rem;
    }

    .story-footer {
      font-size: 0.78rem;
      color: #4b5563;
      font-style: italic;
    }

    .story-highlight {
      position: absolute;
      inset: 0;
      background: linear-gradient(
        135deg,
        rgba(37, 99, 235, 0.08),
        transparent 40%,
        rgba(234, 179, 8, 0.08)
      );
      pointer-events: none;
      mix-blend-mode: soft-light;
    }

    /* Catalogue */

    .catalogue-grid {
      margin-top: 1.5rem;
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1rem;
    }

    .cat-card {
      background: #fff;
      border-radius: 16px;
      padding: 1rem;
      box-shadow: 0 12px 30px rgba(15, 23, 42, 0.08);
      font-size: 0.86rem;
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
      transition: transform var(--transition-med), box-shadow var(--transition-med);
    }

    .cat-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 18px 40px rgba(15, 23, 42, 0.16);
    }

    .cat-title {
      font-weight: 600;
    }

    .cat-meta {
      font-size: 0.8rem;
      color: var(--muted);
    }

    .cat-tag-list {
      display: flex;
      flex-wrap: wrap;
      gap: 0.3rem;
      margin-top: 0.2rem;
    }

    .cat-tag {
      font-size: 0.72rem;
      padding: 0.12rem 0.55rem;
      border-radius: 999px;
      background: rgba(148, 163, 184, 0.16);
      color: #4b5563;
    }

    .catalogue-note {
      margin-top: 0.9rem;
      font-size: 0.78rem;
      color: var(--muted);
    }

    /* Contact */

    .contact-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.1fr) minmax(0, 1.1fr);
      gap: 1.5rem;
      margin-top: 1.6rem;
    }

    .contact-card {
      background: #fff;
      border-radius: 18px;
      padding: 1.1rem;
      box-shadow: 0 14px 34px rgba(15, 23, 42, 0.12);
      font-size: 0.9rem;
    }

    .contact-card h3 {
      margin-bottom: 0.4rem;
      font-size: 1.05rem;
    }

    .contact-card p {
      color: var(--muted);
      margin-bottom: 0.7rem;
      font-size: 0.86rem;
    }

    .contact-row {
      display: flex;
      gap: 0.9rem;
      margin-bottom: 0.6rem;
      font-size: 0.85rem;
    }

    .contact-row strong {
      min-width: 100px;
    }

    form label {
      display: block;
      font-size: 0.8rem;
      margin-bottom: 0.15rem;
    }

    form input,
    form select,
    form textarea {
      width: 100%;
      padding: 0.45rem 0.55rem;
      border-radius: 8px;
      border: 1px solid rgba(148, 163, 184, 0.6);
      font-size: 0.86rem;
      margin-bottom: 0.7rem;
      outline: none;
      transition: border var(--transition-fast), box-shadow var(--transition-fast);
      background: #f9fafb;
    }

    form input:focus,
    form select:focus,
    form textarea:focus {
      border-color: #2563eb;
      box-shadow: 0 0 0 1px rgba(37, 99, 235, 0.4);
      background: #fff;
    }

    textarea {
      min-height: 80px;
      resize: vertical;
    }

    footer {
      max-width: 1120px;
      margin: 0 auto;
      padding: 1.5rem 1.25rem 2.5rem;
      font-size: 0.8rem;
      color: var(--muted);
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 0.7rem;
    }

    /* Chatbot bubble */

    .chatbot-bubble {
      position: fixed;
      right: 1.2rem;
      bottom: 1.2rem;
      width: 58px;
      height: 58px;
      border-radius: 999px;
      background: radial-gradient(circle at 0 0, #38bdf8, #2563eb);
      display: grid;
      place-items: center;
      color: #fff;
      box-shadow: 0 20px 50px rgba(37, 99, 235, 0.6);
      cursor: pointer;
      z-index: 40;
      transition: transform var(--transition-med), box-shadow var(--transition-med);
    }

    .chatbot-bubble:hover {
      transform: translateY(-3px) scale(1.04);
      box-shadow: 0 26px 70px rgba(37, 99, 235, 0.9);
    }

    .chatbot-dot {
      width: 6px;
      height: 6px;
      border-radius: 999px;
      background: #e5e7eb;
      box-shadow: 0 0 0 4px rgba(248, 250, 252, 0.35);
    }

    /* Scroll animations */

    .fade-in {
      opacity: 0;
      transform: translateY(12px);
      transition: opacity 0.5s ease-out, transform 0.5s ease-out;
    }

    .fade-in.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* Responsive */

    @media (max-width: 900px) {
      .hero {
        grid-template-columns: minmax(0, 1fr);
      }
      .demo-grid,
      .contact-grid {
        grid-template-columns: minmax(0, 1fr);
      }
      .process-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
      .catalogue-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }
      .nav-links {
        display: none;
      }
    }

    @media (max-width: 640px) {
      .process-grid {
        grid-template-columns: minmax(0, 1fr);
      }
      .catalogue-grid {
        grid-template-columns: minmax(0, 1fr);
      }
      .hero {
        margin-top: 1.8rem;
      }
      .story-card {
        min-width: 240px;
      }
    }
  </style>
</head>
<body>
  <header>
    <nav class="nav">
      <div class="logo">
        <div class="logo-mark">L&L</div>
        <span>Links &amp; Labels</span>
      </div>
      <div class="nav-links">
        <a href="#how-it-works">How it works</a>
        <a href="#catalogue">RFID catalogue</a>
        <a href="#stories">Customer stories</a>
        <a href="#contact">Contact</a>
      </div>
      <div class="nav-cta">
        <button class="btn btn-outline" onclick="scrollToSection('catalogue')">
          View tags
        </button>
        <button class="btn btn-primary" onclick="scrollToSection('contact')">
          Book consultation
        </button>
      </div>
    </nav>
  </header>

  <main>
    <!-- Hero -->
    <section class="hero fade-in">
      <div>
        <div class="hero-badge">
          <span>RFID asset tagging, end‑to‑end</span>
        </div>
        <h1 class="hero-heading">
          Smart RFID tagging for assets that cannot go missing.
        </h1>
        <p class="hero-p">
          Design, deploy, and track RFID tags across plants, warehouses, hospitals, and
          offices with real‑time visibility and near‑zero manual counts.
        </p>
        <div class="hero-actions">
          <button class="btn btn-primary" onclick="scrollToSection('contact')">
            Book a free RFID call
          </button>
          <button class="btn btn-outline" onclick="scrollToSection('how-it-works')">
            Watch asset tagging demo
          </button>
        </div>
        <div class="hero-meta">
          <span>• 10,000+ assets tagged for clients</span>
          <span>• Ideal for IT, healthcare, logistics, and industrial plants</span>
        </div>
      </div>
      <div class="hero-visual">
        <div class="hero-orbit"></div>
        <div class="hero-grid">
          <div class="asset-card">
            <div class="asset-tag-pill">IT assets</div>
            <div class="asset-label">Laptops &amp; servers</div>
            <div class="asset-meta">UHF label tags · Medium range</div>
          </div>
          <div class="asset-card">
            <div class="asset-tag-pill">Warehouse</div>
            <div class="asset-label">Racks &amp; pallets</div>
            <div class="asset-meta">Industrial on‑metal · Long range</div>
          </div>
          <div class="asset-card">
            <div class="asset-tag-pill">Healthcare</div>
            <div class="asset-label">Infusion pumps</div>
            <div class="asset-meta">Rugged tags · Sterilizable</div>
          </div>
          <div class="asset-card">
            <div class="asset-tag-pill">Oil &amp; gas</div>
            <div class="asset-label">Field tools</div>
            <div class="asset-meta">High‑temp tags · Harsh env.</div>
          </div>
          <div class="asset-card">
            <div class="asset-tag-pill">Textiles</div>
            <div class="asset-label">Uniforms &amp; linens</div>
            <div class="asset-meta">Textile RFID · Laundry‑safe</div>
          </div>
          <div class="asset-card">
            <div class="asset-tag-pill">Brand protection</div>
            <div class="asset-label">High‑value items</div>
            <div class="asset-meta">Tamper‑evident labels</div>
          </div>
        </div>
        <div class="hero-badge-floating">
          <span>Live dashboards · Automated reads</span>
        </div>
      </div>
    </section>

    <!-- How it works -->
    <section id="how-it-works" class="fade-in">
      <div class="section-label">How it works</div>
      <h2 class="section-title">From plan to real‑time tracking in four steps.</h2>
      <p class="section-subtitle">
        A guided RFID rollout that covers tag selection, placement, encoding, readers, and
        software so you get reliable, accurate data from day one.
      </p>

      <div class="process-grid">
        <div class="step-card">
          <div class="step-number">01</div>
          <div class="step-title">Discover</div>
          <div class="step-meta">
            Map your assets, environments, and read zones. Define how often assets need to be
            read and which systems must receive the data.
          </div>
        </div>
        <div class="step-card">
          <div class="step-number">02</div>
          <div class="step-title">Design</div>
          <div class="step-meta">
            Choose the right RFID tag families, encoding schemes, and reader mix for metal,
            plastic, textiles, or harsh conditions.
          </div>
        </div>
        <div class="step-card">
          <div class="step-number">03</div>
          <div class="step-title">Deploy</div>
          <div class="step-meta">
            Apply tags, install readers, and test read ranges at doors, racks, and checkpoints
            to avoid blind spots and duplicate reads.
          </div>
        </div>
        <div class="step-card">
          <div class="step-number">04</div>
          <div class="step-title">Track</div>
          <div class="step-meta">
            See assets in real time with dashboards and alerts for movement, missing items,
            and upcoming audits.
          </div>
        </div>
      </div>

      <!-- Demo videos -->
      <div class="demo-grid">
        <div class="demo-card">
          <div class="demo-inner">
            <div class="demo-header">
              <span>Asset tagging on the floor</span>
              <span class="demo-chip">Demo video</span>
            </div>
            <div class="demo-video-placeholder">
              <div class="demo-video-inner">
                <!-- Replace this with your actual video embed (e.g., iframe) -->
                <div class="play-button" title="Play tagging process demo"></div>
              </div>
            </div>
            <div class="demo-caption">
              Show your team applying RFID tags to pallets, tools, and IT equipment, then
              scanning them with handheld readers.
            </div>
          </div>
        </div>

        <div class="demo-card">
          <div class="demo-inner">
            <div class="demo-header">
              <span>Live tracking dashboard</span>
              <span class="demo-chip">Demo video</span>
            </div>
            <div class="demo-video-placeholder">
              <div class="demo-video-inner">
                <!-- Replace this with your actual video embed (e.g., iframe) -->
                <div class="play-button" title="Play dashboard demo"></div>
              </div>
            </div>
            <div class="demo-caption">
              Visualize items moving through locations, with counts, exceptions, and audit
              trails updating in real time.
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Customer stories -->
    <section id="stories" class="fade-in">
      <div class="section-label">Customer stories</div>
      <h2 class="section-title">Real customers, measurable results.</h2>
      <p class="section-subtitle">
        RFID tagging can cut manual inventory work dramatically and reduce loss on assets
        that matter most.
      </p>

      <div class="stories-strip">
        <article class="story-card">
          <div class="story-highlight"></div>
          <div class="story-industry">Pharma distribution · 25,000+ assets</div>
          <div class="story-metric">70% faster stock counts.</div>
          <p class="story-body">
            Replaced barcode‑only audits with RFID tags on cages, racks, and cold‑chain
            containers, enabling monthly counts in a few hours instead of multiple days.
          </p>
          <div class="story-footer">
            “Inventory now fits into a single shift with no shutdown.”
          </div>
        </article>

        <article class="story-card">
          <div class="story-highlight"></div>
          <div class="story-industry">Hospital network · 8 sites</div>
          <div class="story-metric">35% fewer lost devices.</div>
          <p class="story-body">
            Tagged high‑value medical devices and pumps, giving real‑time location and
            maintenance status to biomedical teams across critical departments.
          </p>
          <div class="story-footer">
            “Nurses search less, and equipment is ready when needed.”
          </div>
        </article>

        <article class="story-card">
          <div class="story-highlight"></div>
          <div class="story-industry">Manufacturing plant · heavy tools</div>
          <div class="story-metric">40% fewer tool write‑offs.</div>
          <p class="story-body">
            Deployed rugged metal‑mount tags on critical tools and fixtures with gate readers
            at exits, reducing loss and simplifying compliance audits.
          </p>
          <div class="story-footer">
            “We finally know where our tools are and who used them last.”
          </div>
        </article>
      </div>
    </section>

    <!-- RFID catalogue -->
    <section id="catalogue" class="fade-in">
      <div class="section-label">RFID catalogue</div>
      <h2 class="section-title">Tag families for every asset type.</h2>
      <p class="section-subtitle">
        The catalogue below groups common RFID tag families to help you quickly narrow down
        the right fit. It is aligned with portfolios from leading vendors, including HID
        Global.
      </p>

      <div class="catalogue-grid">
        <div class="cat-card">
          <div class="cat-title">Industrial &amp; on‑metal tags</div>
          <div class="cat-meta">
            Tools, racks, frames, and containers in harsh industrial or outdoor conditions.
          </div>
          <div class="cat-tag-list">
            <span class="cat-tag">UHF / HF</span>
            <span class="cat-tag">On‑metal design</span>
            <span class="cat-tag">High‑temperature</span>
            <span class="cat-tag">Rugged housing</span>
          </div>
        </div>

        <div class="cat-card">
          <div class="cat-title">Logistics &amp; warehouse labels</div>
          <div class="cat-meta">
            Pallets, bins, cartons, and returnable packaging for inbound, outbound, and
            internal moves.
          </div>
          <div class="cat-tag-list">
            <span class="cat-tag">UHF labels</span>
            <span class="cat-tag">Long‑range</span>
            <span class="cat-tag">Peel &amp; stick</span>
          </div>
        </div>

        <div class="cat-card">
          <div class="cat-title">Healthcare &amp; medical</div>
          <div class="cat-meta">
            Medical devices, trays, and critical equipment that face sterilization and strict
            hygiene requirements.
          </div>
          <div class="cat-tag-list">
            <span class="cat-tag">Rugged tags</span>
            <span class="cat-tag">Chemical‑resistant</span>
            <span class="cat-tag">Autoclave‑ready</span>
          </div>
        </div>

        <div class="cat-card">
          <div class="cat-title">Textile &amp; laundry tags</div>
          <div class="cat-meta">
            Uniforms, linens, and workwear for hospitality, healthcare, and industrial
            laundries.
          </div>
          <div class="cat-tag-list">
            <span class="cat-tag">Sew‑in</span>
            <span class="cat-tag">Heat‑seal</span>
            <span class="cat-tag">High‑cycle wash</span>
          </div>
        </div>

        <div class="cat-card">
          <div class="cat-title">IT &amp; office assets</div>
          <div class="cat-meta">
            Laptops, servers, screens, and office equipment for audits and lifecycle
            tracking.
          </div>
          <div class="cat-tag-list">
            <span class="cat-tag">Slim labels</span>
            <span class="cat-tag">On‑metal option</span>
            <span class="cat-tag">Tamper‑evident</span>
          </div>
        </div>

        <div class="cat-card">
          <div class="cat-title">Brand protection &amp; high‑value</div>
          <div class="cat-meta">
            Products that need authentication and anti‑tamper tracking for anti‑counterfeit
            programs.
          </div>
          <div class="cat-tag-list">
            <span class="cat-tag">Secure encoding</span>
            <span class="cat-tag">Tamper‑evident</span>
            <span class="cat-tag">Visible or hidden</span>
          </div>
        </div>
      </div>

      <p class="catalogue-note">
        HID is a registered trademark of HID Global. This catalogue structure is inspired by
        publicly available RFID tag categories and is provided for educational and
        comparison purposes only.
      </p>
    </section>

    <!-- Contact / CTA -->
    <section id="contact" class="fade-in">
      <div class="section-label">Contact</div>
      <h2 class="section-title">Plan your RFID asset tagging rollout.</h2>
      <p class="section-subtitle">
        Share a few details and receive a tailored proposal covering tags, readers, software
        integration, and rollout timelines.
      </p>

      <div class="contact-grid">
        <div class="contact-card">
          <h3>Talk to an RFID specialist</h3>
          <p>
            Choose your industry, asset types, and current challenges. An RFID specialist
            will respond with recommended tag families and a rough project outline.
          </p>

          <form>
            <label for="name">Name</label>
            <input id="name" name="name" placeholder="Your full name" />

            <label for="email">Work email</label>
            <input id="email" name="email" type="email" placeholder="name@company.com" />

            <label for="industry">Industry</label>
            <select id="industry" name="industry">
              <option value="">Select your industry</option>
              <option>Logistics &amp; warehousing</option>
              <option>Manufacturing</option>
              <option>Healthcare</option>
              <option>IT &amp; data centers</option>
              <option>Oil &amp; gas / harsh environments</option>
              <option>Other</option>
            </select>

            <label for="assets">Approx. number of assets</label>
            <input
              id="assets"
              name="assets"
              placeholder="e.g., 5,000 IT assets, 800 tools, 1,200 pallets"
            />

            <label for="message">What are you trying to fix?</label>
            <textarea
              id="message"
              name="message"
              placeholder="Missing tools, slow audits, lack of real-time visibility..."
            ></textarea>

            <button type="submit" class="btn btn-primary" style="width: 100%; margin-top: 0.2rem;">
              Request consultation
            </button>
          </form>
        </div>

        <div class="contact-card">
          <h3>Project snapshot</h3>
          <p>
            A quick overview of what your RFID journey can look like once we understand your
            assets and environment.
          </p>

          <div class="contact-row">
            <strong>Discovery</strong>
            <span>Workshops to define assets, locations, and integration points.</span>
          </div>
          <div class="contact-row">
            <strong>Pilot</strong>
            <span>Tag a subset of assets and validate read rates and data quality.</span>
          </div>
          <div class="contact-row">
            <strong>Rollout</strong>
            <span>Scale tags, readers, and dashboards across all sites.</span>
          </div>
          <div class="contact-row">
            <strong>Ongoing</strong>
            <span>Monitoring, fine‑tuning, and adding new asset classes over time.</span>
          </div>
          <p style="margin-top: 0.5rem;">
            Prefer WhatsApp or phone first? Add your number in the message field and we will
            reach out with time options.
          </p>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <span>© <span id="year"></span> Links &amp; Labels. All rights reserved.</span>
    <span>Respecting intellectual property and trademarks of all vendors we partner with.</span>
  </footer>

  <!-- AI Chatbot placeholder -->
  <div class="chatbot-bubble" onclick="openChatbot()" title="Ask about RFID tagging">
    <div class="chatbot-dot"></div>
  </div>

  <script>
    // Smooth scroll helper
    function scrollToSection(id) {
      const el = document.getElementById(id);
      if (el) {
        el.scrollIntoView({ behavior: "smooth", block: "start" });
      }
    }

    // Chatbot placeholder – replace with real provider snippet (e.g., Intercom, custom widget)
    function openChatbot() {
      alert(
        "Chatbot placeholder: integrate your AI chat provider here (e.g., LLM API, Intercom, Drift)."
      );
    }

    // Year
    document.getElementById("year").textContent = new Date().getFullYear();

    // Intersection Observer for fade-in animation
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            entry.target.classList.add("visible");
            observer.unobserve(entry.target);
          }
        });
      },
      { threshold: 0.1 }
    );

    document.querySelectorAll(".fade-in").forEach((el) => observer.observe(el));
  </script>
</body>
</html>
