<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="Software Developer portfolio of Jerywin Bayawan, building secure and scalable web and mobile applications." />
  <meta name="theme-color" content="#080c14" />
  <title>Jerywin Bayawan | Software Developer</title>

  <style>
    :root {
      --bg: #080c14;
      --bg-soft: #0d1421;
      --card: rgba(17, 25, 40, 0.72);
      --card-solid: #111927;
      --text: #f5f7fb;
      --muted: #9ca8ba;
      --primary: #6ee7f9;
      --primary-strong: #22d3ee;
      --secondary: #8b5cf6;
      --border: rgba(255, 255, 255, 0.09);
      --shadow: 0 24px 80px rgba(0, 0, 0, 0.32);
      --radius: 22px;
      --max-width: 1180px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
      scroll-padding-top: 90px;
    }

    body {
      min-height: 100vh;
      overflow-x: hidden;
      color: var(--text);
      background:
        radial-gradient(circle at 12% 12%, rgba(34, 211, 238, 0.12), transparent 24%),
        radial-gradient(circle at 88% 18%, rgba(139, 92, 246, 0.14), transparent 28%),
        var(--bg);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      line-height: 1.65;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      z-index: -2;
      pointer-events: none;
      background-image:
        linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px);
      background-size: 42px 42px;
      mask-image: linear-gradient(to bottom, black, transparent 92%);
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    button,
    input,
    textarea {
      font: inherit;
    }

    img {
      display: block;
      max-width: 100%;
    }

    .container {
      width: min(calc(100% - 32px), var(--max-width));
      margin-inline: auto;
    }

    .section {
      padding: 104px 0;
    }

    .section-header {
      max-width: 720px;
      margin-bottom: 42px;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 14px;
      color: var(--primary);
      font-size: 0.78rem;
      font-weight: 800;
      letter-spacing: 0.16em;
      text-transform: uppercase;
    }

    .eyebrow::before {
      content: "";
      width: 26px;
      height: 2px;
      border-radius: 999px;
      background: currentColor;
    }

    h1,
    h2,
    h3 {
      line-height: 1.14;
    }

    h2 {
      font-size: clamp(2rem, 5vw, 3.25rem);
      letter-spacing: -0.04em;
    }

    .section-header p {
      margin-top: 14px;
      color: var(--muted);
      font-size: 1.02rem;
    }

    .nav {
      position: fixed;
      top: 0;
      left: 0;
      z-index: 1000;
      width: 100%;
      transition: background 0.25s ease, border-color 0.25s ease, backdrop-filter 0.25s ease;
    }

    .nav.scrolled {
      border-bottom: 1px solid var(--border);
      background: rgba(8, 12, 20, 0.78);
      backdrop-filter: blur(18px);
    }

    .nav-inner {
      min-height: 74px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 11px;
      font-weight: 900;
      letter-spacing: -0.03em;
    }

    .brand-mark {
      display: grid;
      width: 38px;
      height: 38px;
      place-items: center;
      border-radius: 12px;
      color: #071016;
      background: linear-gradient(135deg, var(--primary), #ffffff);
      box-shadow: 0 8px 30px rgba(34, 211, 238, 0.28);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 28px;
      list-style: none;
    }

    .nav-links a {
      position: relative;
      color: var(--muted);
      font-size: 0.92rem;
      font-weight: 700;
      transition: color 0.2s ease;
    }

    .nav-links a:hover,
    .nav-links a.active {
      color: var(--text);
    }

    .nav-links a::after {
      content: "";
      position: absolute;
      right: 0;
      bottom: -9px;
      left: 0;
      height: 2px;
      border-radius: 999px;
      background: var(--primary);
      transform: scaleX(0);
      transition: transform 0.2s ease;
    }

    .nav-links a.active::after {
      transform: scaleX(1);
    }

    .menu-button {
      display: none;
      width: 42px;
      height: 42px;
      border: 1px solid var(--border);
      border-radius: 12px;
      color: var(--text);
      background: var(--card);
      cursor: pointer;
    }

    .hero {
      position: relative;
      min-height: 100vh;
      display: grid;
      align-items: center;
      padding: 120px 0 70px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      align-items: center;
      gap: 72px;
    }

    .status {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      width: fit-content;
      margin-bottom: 26px;
      padding: 8px 13px;
      border: 1px solid rgba(110, 231, 249, 0.18);
      border-radius: 999px;
      color: #c8f8ff;
      background: rgba(34, 211, 238, 0.07);
      font-size: 0.82rem;
      font-weight: 700;
    }

    .status-dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: #34d399;
      box-shadow: 0 0 0 6px rgba(52, 211, 153, 0.12);
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      50% { box-shadow: 0 0 0 10px rgba(52, 211, 153, 0); }
    }

    .hero h1 {
      max-width: 760px;
      font-size: clamp(3rem, 8vw, 6.5rem);
      letter-spacing: -0.07em;
    }

    .gradient-text {
      color: transparent;
      background: linear-gradient(110deg, #ffffff 4%, var(--primary) 45%, #a78bfa 92%);
      -webkit-background-clip: text;
      background-clip: text;
    }

    .hero-description {
      max-width: 680px;
      margin-top: 24px;
      color: var(--muted);
      font-size: clamp(1rem, 2vw, 1.18rem);
    }

    .hero-description strong {
      color: var(--text);
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      margin-top: 34px;
    }

    .button {
      display: inline-flex;
      min-height: 50px;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 0 20px;
      border: 1px solid transparent;
      border-radius: 14px;
      font-size: 0.94rem;
      font-weight: 800;
      cursor: pointer;
      transition: transform 0.2s ease, border-color 0.2s ease, background 0.2s ease;
    }

    .button:hover {
      transform: translateY(-3px);
    }

    .button-primary {
      color: #061017;
      background: linear-gradient(135deg, var(--primary), #ffffff);
      box-shadow: 0 12px 36px rgba(34, 211, 238, 0.2);
    }

    .button-secondary {
      border-color: var(--border);
      color: var(--text);
      background: rgba(255, 255, 255, 0.035);
    }

    .hero-metrics {
      display: flex;
      flex-wrap: wrap;
      gap: 28px;
      margin-top: 44px;
    }

    .metric strong {
      display: block;
      font-size: 1.5rem;
      letter-spacing: -0.04em;
    }

    .metric span {
      color: var(--muted);
      font-size: 0.82rem;
    }

    .terminal-wrap {
      position: relative;
    }

    .terminal-wrap::before {
      content: "";
      position: absolute;
      inset: 14% -10% -10% 15%;
      z-index: -1;
      border-radius: 50%;
      background: rgba(34, 211, 238, 0.16);
      filter: blur(70px);
    }

    .terminal {
      overflow: hidden;
      border: 1px solid var(--border);
      border-radius: 24px;
      background: rgba(9, 14, 24, 0.9);
      box-shadow: var(--shadow);
      transform: perspective(1200px) rotateY(-4deg) rotateX(2deg);
      transition: transform 0.4s ease;
    }

    .terminal:hover {
      transform: perspective(1200px) rotateY(0) rotateX(0) translateY(-6px);
    }

    .terminal-top {
      display: flex;
      align-items: center;
      gap: 8px;
      padding: 16px 18px;
      border-bottom: 1px solid var(--border);
      background: rgba(255,255,255,0.025);
    }

    .terminal-dot {
      width: 11px;
      height: 11px;
      border-radius: 50%;
    }

    .terminal-dot:nth-child(1) { background: #fb7185; }
    .terminal-dot:nth-child(2) { background: #fbbf24; }
    .terminal-dot:nth-child(3) { background: #34d399; }

    .terminal-title {
      margin-left: 8px;
      color: #7e8da4;
      font-size: 0.76rem;
    }

    pre {
      min-height: 380px;
      padding: 28px;
      overflow-x: auto;
      color: #d9e2ef;
      font: 500 0.9rem/1.8 "SFMono-Regular", Consolas, "Liberation Mono", monospace;
      white-space: pre-wrap;
    }

    .code-purple { color: #c4a7ff; }
    .code-blue { color: #7dd3fc; }
    .code-green { color: #86efac; }
    .code-yellow { color: #fde68a; }
    .code-muted { color: #6b7a91; }

    .about-grid {
      display: grid;
      grid-template-columns: 0.85fr 1.15fr;
      align-items: stretch;
      gap: 32px;
    }

    .profile-card,
    .about-content,
    .service-card,
    .project-card,
    .contact-card {
      border: 1px solid var(--border);
      background: var(--card);
      box-shadow: 0 18px 70px rgba(0,0,0,0.16);
      backdrop-filter: blur(16px);
    }

    .profile-card {
      position: relative;
      min-height: 440px;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      overflow: hidden;
      padding: 30px;
      border-radius: var(--radius);
      background:
        radial-gradient(circle at 50% 32%, rgba(110, 231, 249, 0.26), transparent 27%),
        linear-gradient(150deg, #111a2a, #0a101b);
    }

    .avatar {
      position: absolute;
      top: 56px;
      left: 50%;
      display: grid;
      width: 184px;
      height: 184px;
      place-items: center;
      border: 1px solid rgba(255,255,255,0.12);
      border-radius: 44px;
      color: #071016;
      background: linear-gradient(135deg, var(--primary), #d8b4fe);
      box-shadow: 0 28px 70px rgba(34,211,238,0.18);
      font-size: 4rem;
      font-weight: 950;
      transform: translateX(-50%) rotate(-3deg);
    }

    .profile-card h3 {
      font-size: 1.6rem;
    }

    .profile-card p {
      margin-top: 7px;
      color: var(--muted);
    }

    .profile-links {
      display: flex;
      gap: 10px;
      margin-top: 20px;
    }

    .icon-link {
      display: grid;
      width: 42px;
      height: 42px;
      place-items: center;
      border: 1px solid var(--border);
      border-radius: 12px;
      color: var(--muted);
      background: rgba(255,255,255,0.035);
      transition: color 0.2s, border-color 0.2s, transform 0.2s;
    }

    .icon-link:hover {
      color: var(--primary);
      border-color: rgba(110,231,249,0.32);
      transform: translateY(-3px);
    }

    .about-content {
      padding: clamp(28px, 5vw, 52px);
      border-radius: var(--radius);
    }

    .about-content h3 {
      font-size: clamp(1.6rem, 4vw, 2.35rem);
      letter-spacing: -0.04em;
    }

    .about-content > p {
      margin-top: 18px;
      color: var(--muted);
    }

    .about-list {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 14px;
      margin-top: 28px;
    }

    .about-item {
      padding: 17px;
      border: 1px solid var(--border);
      border-radius: 15px;
      background: rgba(255,255,255,0.025);
    }

    .about-item span {
      display: block;
      color: var(--muted);
      font-size: 0.76rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.08em;
    }

    .about-item strong {
      display: block;
      margin-top: 4px;
      font-size: 0.96rem;
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 16px;
    }

    .skill-group {
      padding: 24px;
      border: 1px solid var(--border);
      border-radius: 19px;
      background: rgba(255,255,255,0.025);
    }

    .skill-icon {
      display: grid;
      width: 46px;
      height: 46px;
      place-items: center;
      margin-bottom: 20px;
      border-radius: 14px;
      color: var(--primary);
      background: rgba(34,211,238,0.08);
      font-weight: 900;
    }

    .skill-group h3 {
      margin-bottom: 14px;
      font-size: 1rem;
    }

    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .tag {
      padding: 7px 10px;
      border: 1px solid var(--border);
      border-radius: 999px;
      color: var(--muted);
      background: rgba(255,255,255,0.025);
      font-size: 0.75rem;
      font-weight: 700;
    }

    .services-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 18px;
    }

    .service-card {
      padding: 28px;
      border-radius: var(--radius);
      transition: transform 0.25s ease, border-color 0.25s ease;
    }

    .service-card:hover {
      border-color: rgba(110,231,249,0.24);
      transform: translateY(-7px);
    }

    .service-number {
      color: var(--primary);
      font: 800 0.8rem "SFMono-Regular", Consolas, monospace;
    }

    .service-card h3 {
      margin-top: 22px;
      font-size: 1.22rem;
    }

    .service-card p {
      margin-top: 11px;
      color: var(--muted);
      font-size: 0.93rem;
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 22px;
    }

    .project-card {
      overflow: hidden;
      border-radius: var(--radius);
      transition: transform 0.25s ease, border-color 0.25s ease;
    }

    .project-card:hover {
      border-color: rgba(110,231,249,0.26);
      transform: translateY(-7px);
    }

    .project-visual {
      position: relative;
      min-height: 230px;
      display: grid;
      place-items: center;
      overflow: hidden;
      background:
        linear-gradient(145deg, rgba(34,211,238,0.11), rgba(139,92,246,0.12)),
        #0b1220;
    }

    .project-visual::before {
      content: "";
      position: absolute;
      width: 220px;
      height: 220px;
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 50%;
      box-shadow:
        0 0 0 40px rgba(255,255,255,0.025),
        0 0 0 80px rgba(255,255,255,0.018);
    }

    .project-logo {
      position: relative;
      z-index: 1;
      display: grid;
      width: 94px;
      height: 94px;
      place-items: center;
      border: 1px solid rgba(255,255,255,0.12);
      border-radius: 28px;
      background: rgba(7,13,23,0.86);
      box-shadow: 0 20px 50px rgba(0,0,0,0.26);
      font-size: 1.45rem;
      font-weight: 950;
      letter-spacing: -0.07em;
    }

    .project-body {
      padding: 26px;
    }

    .project-meta {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
    }

    .project-meta h3 {
      font-size: 1.28rem;
    }

    .project-type {
      color: var(--primary);
      font-size: 0.76rem;
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: 0.08em;
    }

    .project-body p {
      margin-top: 12px;
      color: var(--muted);
      font-size: 0.94rem;
    }

    .project-stack {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 20px;
    }

    .timeline {
      position: relative;
      max-width: 850px;
    }

    .timeline::before {
      content: "";
      position: absolute;
      top: 10px;
      bottom: 10px;
      left: 7px;
      width: 1px;
      background: linear-gradient(var(--primary), rgba(255,255,255,0.08));
    }

    .timeline-item {
      position: relative;
      padding: 0 0 42px 42px;
    }

    .timeline-dot {
      position: absolute;
      top: 7px;
      left: 0;
      width: 15px;
      height: 15px;
      border: 3px solid var(--bg);
      border-radius: 50%;
      background: var(--primary);
      box-shadow: 0 0 0 4px rgba(34,211,238,0.12);
    }

    .timeline-date {
      color: var(--primary);
      font-size: 0.78rem;
      font-weight: 800;
      letter-spacing: 0.06em;
      text-transform: uppercase;
    }

    .timeline-item h3 {
      margin-top: 5px;
      font-size: 1.25rem;
    }

    .timeline-item p {
      max-width: 690px;
      margin-top: 8px;
      color: var(--muted);
    }

    .contact-card {
      display: grid;
      grid-template-columns: 1fr auto;
      align-items: center;
      gap: 40px;
      padding: clamp(30px, 6vw, 64px);
      border-radius: 28px;
      background:
        radial-gradient(circle at 95% 5%, rgba(139,92,246,0.18), transparent 30%),
        radial-gradient(circle at 5% 95%, rgba(34,211,238,0.15), transparent 32%),
        var(--card);
    }

    .contact-card h2 {
      max-width: 740px;
    }

    .contact-card p {
      max-width: 650px;
      margin-top: 16px;
      color: var(--muted);
    }

    footer {
      padding: 30px 0;
      border-top: 1px solid var(--border);
    }

    .footer-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      color: var(--muted);
      font-size: 0.84rem;
    }

    .reveal {
      opacity: 0;
      transform: translateY(24px);
      transition: opacity 0.65s ease, transform 0.65s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    @media (max-width: 960px) {
      .hero-grid,
      .about-grid,
      .contact-card {
        grid-template-columns: 1fr;
      }

      .hero-grid {
        gap: 54px;
      }

      .terminal {
        max-width: 680px;
        transform: none;
      }

      .skills-grid {
        grid-template-columns: repeat(2, 1fr);
      }

      .services-grid {
        grid-template-columns: repeat(2, 1fr);
      }

      .contact-card {
        align-items: start;
      }
    }

    @media (max-width: 720px) {
      .section {
        padding: 76px 0;
      }

      .menu-button {
        display: grid;
        place-items: center;
      }

      .nav-links {
        position: absolute;
        top: 66px;
        right: 16px;
        left: 16px;
        display: none;
        flex-direction: column;
        align-items: stretch;
        gap: 0;
        overflow: hidden;
        padding: 8px;
        border: 1px solid var(--border);
        border-radius: 16px;
        background: rgba(8,12,20,0.96);
        box-shadow: var(--shadow);
        backdrop-filter: blur(18px);
      }

      .nav-links.open {
        display: flex;
      }

      .nav-links a {
        display: block;
        padding: 12px 14px;
        border-radius: 10px;
      }

      .nav-links a:hover {
        background: rgba(255,255,255,0.04);
      }

      .nav-links a::after {
        display: none;
      }

      .hero {
        min-height: auto;
        padding-top: 125px;
      }

      .hero h1 {
        font-size: clamp(3.2rem, 17vw, 5rem);
      }

      pre {
        min-height: 330px;
        padding: 20px;
        font-size: 0.78rem;
      }

      .projects-grid,
      .services-grid {
        grid-template-columns: 1fr;
      }

      .about-list {
        grid-template-columns: 1fr;
      }

      .footer-inner {
        flex-direction: column;
        align-items: flex-start;
      }
    }

    @media (max-width: 520px) {
      .container {
        width: min(calc(100% - 22px), var(--max-width));
      }

      .skills-grid {
        grid-template-columns: 1fr;
      }

      .hero-actions .button {
        width: 100%;
      }

      .hero-metrics {
        gap: 20px;
      }

      .profile-card {
        min-height: 410px;
      }

      .avatar {
        top: 48px;
        width: 160px;
        height: 160px;
        border-radius: 38px;
      }
    }

    @media (prefers-reduced-motion: reduce) {
      *,
      *::before,
      *::after {
        scroll-behavior: auto !important;
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
      }
    }
  </style>
</head>
<body>
  <nav class="nav" id="navbar" aria-label="Primary navigation">
    <div class="container nav-inner">
      <a class="brand" href="#home" aria-label="Go to homepage">
        <span class="brand-mark">&lt;/&gt;</span>
        <span>Zeribytecare</span>
      </a>

      <button class="menu-button" id="menuButton" type="button" aria-label="Open navigation menu" aria-expanded="false">
        <span id="menuIcon">☰</span>
      </button>

      <ul class="nav-links" id="navLinks">
        <li><a href="#home" class="active">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Stack</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#experience">Experience</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
  </nav>

  <main>
    <section class="hero" id="home">
      <div class="container hero-grid">
        <div>
          <div class="status">
            <span class="status-dot"></span>
            Available for software projects
          </div>

          <h1>
            I build <span class="gradient-text">secure digital products.</span>
          </h1>

          <p class="hero-description">
            I’m <strong>Jerywin Bayawan</strong>, a Software Developer specializing in scalable web applications, mobile platforms, backend systems, APIs, and business software.
          </p>

          <div class="hero-actions">
            <a class="button button-primary" href="#projects">
              Explore my work
              <span aria-hidden="true">↗</span>
            </a>
            <a class="button button-secondary" href="mailto:your@email.com">
              Contact me
            </a>
          </div>

          <div class="hero-metrics" aria-label="Professional highlights">
            <div class="metric">
              <strong>Full-Stack</strong>
              <span>Web development</span>
            </div>
            <div class="metric">
              <strong>API-First</strong>
              <span>Scalable architecture</span>
            </div>
            <div class="metric">
              <strong>Secure</strong>
              <span>Production-minded</span>
            </div>
          </div>
        </div>

        <div class="terminal-wrap" aria-label="Developer profile code preview">
          <div class="terminal">
            <div class="terminal-top">
              <span class="terminal-dot"></span>
              <span class="terminal-dot"></span>
              <span class="terminal-dot"></span>
              <span class="terminal-title">developer-profile.ts</span>
            </div>
            <pre><code><span class="code-purple">const</span> <span class="code-blue">developer</span> = {
  name: <span class="code-green">"Jerywin Bayawan"</span>,
  role: <span class="code-green">"Software Developer"</span>,
  brand: <span class="code-green">"Zeribytecare"</span>,

  focus: [
    <span class="code-green">"Web Applications"</span>,
    <span class="code-green">"Mobile Systems"</span>,
    <span class="code-green">"REST APIs"</span>,
    <span class="code-green">"Business Platforms"</span>
  ],

  stack: {
    frontend: [<span class="code-green">"React"</span>, <span class="code-green">"TypeScript"</span>],
    backend: [<span class="code-green">"Node.js"</span>, <span class="code-green">"PHP"</span>],
    database: [<span class="code-green">"PostgreSQL"</span>, <span class="code-green">"Redis"</span>]
  },

  mindset: <span class="code-green">"Build. Secure. Scale."</span>
};

<span class="code-muted">// Turning complex ideas into reliable software.</span>
<span class="code-yellow">developer</span>.ship();</code></pre>
          </div>
        </div>
      </div>
    </section>

    <section class="section" id="about">
      <div class="container">
        <div class="section-header reveal">
          <span class="eyebrow">About me</span>
          <h2>Engineering software that solves real operational problems.</h2>
          <p>
            My work combines product thinking, user-focused interfaces, secure backend development, and reliable infrastructure.
          </p>
        </div>

        <div class="about-grid">
          <article class="profile-card reveal">
            <div class="avatar" aria-label="JB initials">JB</div>
            <h3>Jerywin Bayawan</h3>
            <p>Software Developer · Davao, Philippines</p>
            <div class="profile-links">
              <a class="icon-link" href="https://github.com/" target="_blank" rel="noopener noreferrer" aria-label="GitHub">GH</a>
              <a class="icon-link" href="https://linkedin.com/" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn">in</a>
              <a class="icon-link" href="mailto:your@email.com" aria-label="Email">@</a>
            </div>
          </article>

          <article class="about-content reveal">
            <h3>From product concept to production deployment.</h3>
            <p>
              I design and develop modern applications for payments, human resources, fleet operations, inventory, subscriptions, reporting, and business process automation. I focus on maintainable architecture, responsive experiences, data protection, and dependable delivery.
            </p>
            <p>
              My development approach prioritizes secure authentication, strict authorization, input validation, database integrity, API reliability, and clear user experiences across desktop and mobile devices.
            </p>

            <div class="about-list">
              <div class="about-item">
                <span>Primary role</span>
                <strong>Full-Stack Developer</strong>
              </div>
              <div class="about-item">
                <span>Core specialty</span>
                <strong>Business Applications</strong>
              </div>
              <div class="about-item">
                <span>Development style</span>
                <strong>Secure & Scalable</strong>
              </div>
              <div class="about-item">
                <span>Delivery</span>
                <strong>Web, Android & API</strong>
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section class="section" id="skills">
      <div class="container">
        <div class="section-header reveal">
          <span class="eyebrow">Technology stack</span>
          <h2>Tools I use to deliver complete systems.</h2>
        </div>

        <div class="skills-grid">
          <article class="skill-group reveal">
            <div class="skill-icon">FE</div>
            <h3>Frontend</h3>
            <div class="tags">
              <span class="tag">React</span>
              <span class="tag">TypeScript</span>
              <span class="tag">JavaScript</span>
              <span class="tag">Tailwind CSS</span>
              <span class="tag">Shadcn UI</span>
              <span class="tag">Vite</span>
            </div>
          </article>

          <article class="skill-group reveal">
            <div class="skill-icon">BE</div>
            <h3>Backend</h3>
            <div class="tags">
              <span class="tag">Node.js</span>
              <span class="tag">Express</span>
              <span class="tag">PHP</span>
              <span class="tag">Laravel</span>
              <span class="tag">REST API</span>
              <span class="tag">Socket.io</span>
            </div>
          </article>

          <article class="skill-group reveal">
            <div class="skill-icon">DB</div>
            <h3>Data</h3>
            <div class="tags">
              <span class="tag">PostgreSQL</span>
              <span class="tag">MySQL</span>
              <span class="tag">Redis</span>
              <span class="tag">SQLite</span>
              <span class="tag">Sequelize</span>
              <span class="tag">Data Modeling</span>
            </div>
          </article>

          <article class="skill-group reveal">
            <div class="skill-icon">OP</div>
            <h3>Infrastructure</h3>
            <div class="tags">
              <span class="tag">Docker</span>
              <span class="tag">Linux</span>
              <span class="tag">Caddy</span>
              <span class="tag">GitHub</span>
              <span class="tag">Cloudflare</span>
              <span class="tag">Capacitor</span>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="container">
        <div class="section-header reveal">
          <span class="eyebrow">What I do</span>
          <h2>Full-cycle software development.</h2>
        </div>

        <div class="services-grid">
          <article class="service-card reveal">
            <span class="service-number">01 / WEB</span>
            <h3>Web Application Development</h3>
            <p>Responsive dashboards, administration systems, customer portals, analytics, and modern business platforms.</p>
          </article>

          <article class="service-card reveal">
            <span class="service-number">02 / API</span>
            <h3>Backend & API Engineering</h3>
            <p>Secure REST APIs, authentication, role-based permissions, queues, real-time events, and database architecture.</p>
          </article>

          <article class="service-card reveal">
            <span class="service-number">03 / MOBILE</span>
            <h3>Mobile & Offline Systems</h3>
            <p>Capacitor-powered Android applications, offline-first data handling, synchronization, and device-aware workflows.</p>
          </article>

          <article class="service-card reveal">
            <span class="service-number">04 / SECURITY</span>
            <h3>Application Security</h3>
            <p>Secure sessions, authorization policies, validation, rate limiting, CSRF defenses, security headers, and auditability.</p>
          </article>

          <article class="service-card reveal">
            <span class="service-number">05 / DATA</span>
            <h3>Business Data Systems</h3>
            <p>Payment records, inventory, payroll, reporting, subscription history, transaction processing, and operational insights.</p>
          </article>

          <article class="service-card reveal">
            <span class="service-number">06 / DEPLOY</span>
            <h3>Deployment & Maintenance</h3>
            <p>Containerized deployments, Linux servers, reverse proxies, SSL, backups, environment management, and monitoring.</p>
          </article>
        </div>
      </div>
    </section>

    <section class="section" id="projects">
      <div class="container">
        <div class="section-header reveal">
          <span class="eyebrow">Selected projects</span>
          <h2>Software built for real business operations.</h2>
          <p>Replace the demo links and descriptions below with your final production details.</p>
        </div>

        <div class="projects-grid">
          <article class="project-card reveal">
            <div class="project-visual">
              <div class="project-logo">ZPay</div>
            </div>
            <div class="project-body">
              <div class="project-meta">
                <h3>ZPay</h3>
                <span class="project-type">Fintech SaaS</span>
              </div>
              <p>A multi-tenant payment collection and billing platform supporting recurring, installment, partial, and one-time payments.</p>
              <div class="project-stack">
                <span class="tag">React</span>
                <span class="tag">Node.js</span>
                <span class="tag">PostgreSQL</span>
                <span class="tag">Capacitor</span>
              </div>
            </div>
          </article>

          <article class="project-card reveal">
            <div class="project-visual">
              <div class="project-logo">HRIS</div>
            </div>
            <div class="project-body">
              <div class="project-meta">
                <h3>HR Management System</h3>
                <span class="project-type">Enterprise</span>
              </div>
              <p>An integrated platform for employee records, attendance, payroll, approvals, leave, recruitment, assets, and reporting.</p>
              <div class="project-stack">
                <span class="tag">React</span>
                <span class="tag">Express</span>
                <span class="tag">Redis</span>
                <span class="tag">Docker</span>
              </div>
            </div>
          </article>

          <article class="project-card reveal">
            <div class="project-visual">
              <div class="project-logo">ERP</div>
            </div>
            <div class="project-body">
              <div class="project-meta">
                <h3>Fleet & Hauling ERP</h3>
                <span class="project-type">Operations</span>
              </div>
              <p>A centralized system for equipment, hauling trips, fuel, maintenance, payroll, billing, inventory, expenses, and approvals.</p>
              <div class="project-stack">
                <span class="tag">TypeScript</span>
                <span class="tag">PostgreSQL</span>
                <span class="tag">Docker</span>
                <span class="tag">Caddy</span>
              </div>
            </div>
          </article>

          <article class="project-card reveal">
            <div class="project-visual">
              <div class="project-logo">ZPOS</div>
            </div>
            <div class="project-body">
              <div class="project-meta">
                <h3>ZPOS</h3>
                <span class="project-type">Point of Sale</span>
              </div>
              <p>A restaurant POS platform supporting dine-in, takeout, delivery, kitchen workflows, real-time updates, analytics, and inventory.</p>
              <div class="project-stack">
                <span class="tag">React</span>
                <span class="tag">Zustand</span>
                <span class="tag">Socket.io</span>
                <span class="tag">Sequelize</span>
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section class="section" id="experience">
      <div class="container">
        <div class="section-header reveal">
          <span class="eyebrow">Development experience</span>
          <h2>Focused on systems, reliability, and measurable value.</h2>
        </div>

        <div class="timeline">
          <article class="timeline-item reveal">
            <span class="timeline-dot"></span>
            <span class="timeline-date">Current</span>
            <h3>Software Developer · Zeribytecare</h3>
            <p>Designing and delivering web, mobile, and backend solutions for payments, operations, human resources, inventory, reporting, and automation.</p>
          </article>

          <article class="timeline-item reveal">
            <span class="timeline-dot"></span>
            <span class="timeline-date">Architecture</span>
            <h3>Secure Full-Stack Systems</h3>
            <p>Building tenant-aware APIs, authentication and authorization, database models, responsive interfaces, background jobs, and real-time features.</p>
          </article>

          <article class="timeline-item reveal">
            <span class="timeline-dot"></span>
            <span class="timeline-date">Delivery</span>
            <h3>Production Deployment</h3>
            <p>Managing containerized applications, Linux environments, HTTPS, reverse proxy configuration, secrets, backups, and operational troubleshooting.</p>
          </article>
        </div>
      </div>
    </section>

    <section class="section" id="contact">
      <div class="container">
        <div class="contact-card reveal">
          <div>
            <span class="eyebrow">Start a project</span>
            <h2>Need a secure, scalable application?</h2>
            <p>
              Let’s discuss your product, internal platform, mobile application, API, automation workflow, or custom business system.
            </p>
          </div>
          <a class="button button-primary" href="mailto:your@email.com">
            Send an email
            <span aria-hidden="true">↗</span>
          </a>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container footer-inner">
      <p>© <span id="currentYear"></span> Jerywin Bayawan. All rights reserved.</p>
      <p>Designed and developed by Zeribytecare.</p>
    </div>
  </footer>

  <script>
    "use strict";

    const navbar = document.getElementById("navbar");
    const menuButton = document.getElementById("menuButton");
    const menuIcon = document.getElementById("menuIcon");
    const navLinks = document.getElementById("navLinks");
    const navAnchors = [...document.querySelectorAll(".nav-links a")];
    const sections = [...document.querySelectorAll("main section[id]")];
    const revealItems = document.querySelectorAll(".reveal");

    document.getElementById("currentYear").textContent = new Date().getFullYear();

    const setMenuState = (isOpen) => {
      navLinks.classList.toggle("open", isOpen);
      menuButton.setAttribute("aria-expanded", String(isOpen));
      menuIcon.textContent = isOpen ? "✕" : "☰";
    };

    menuButton.addEventListener("click", () => {
      setMenuState(!navLinks.classList.contains("open"));
    });

    navAnchors.forEach((link) => {
      link.addEventListener("click", () => setMenuState(false));
    });

    document.addEventListener("click", (event) => {
      if (!navLinks.contains(event.target) && !menuButton.contains(event.target)) {
        setMenuState(false);
      }
    });

    const updateNavigation = () => {
      navbar.classList.toggle("scrolled", window.scrollY > 20);

      const currentPosition = window.scrollY + 150;
      let currentSection = "home";

      sections.forEach((section) => {
        if (currentPosition >= section.offsetTop) {
          currentSection = section.id;
        }
      });

      navAnchors.forEach((link) => {
        link.classList.toggle(
          "active",
          link.getAttribute("href") === `#${currentSection}`
        );
      });
    };

    window.addEventListener("scroll", updateNavigation, { passive: true });
    updateNavigation();

    if ("IntersectionObserver" in window) {
      const revealObserver = new IntersectionObserver(
        (entries, observer) => {
          entries.forEach((entry) => {
            if (!entry.isIntersecting) return;
            entry.target.classList.add("visible");
            observer.unobserve(entry.target);
          });
        },
        { threshold: 0.12 }
      );

      revealItems.forEach((item) => revealObserver.observe(item));
    } else {
      revealItems.forEach((item) => item.classList.add("visible"));
    }
  </script>
</body>
</html>
