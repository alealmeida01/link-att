<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Alexandre Júnior | Links</title>
  <meta name="description" content="Links de Alexandre Júnior: Instagram, GitHub, LinkedIn e TikTok.">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #000000;
      --text: #f5f5f5;
      --muted: rgba(255, 255, 255, 0.55);
      --faint: rgba(255, 255, 255, 0.28);
      --card: rgba(255, 255, 255, 0.03);
      --card-hover: rgba(255, 255, 255, 0.06);
      --card-border: rgba(255, 255, 255, 0.12);
      --surface: rgba(10, 10, 10, 0.92);
      --glow: rgba(255, 255, 255, 0.55);
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { -webkit-text-size-adjust: 100%; }

    body {
      min-height: 100vh;
      min-height: 100dvh;
      font-family: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
      background: var(--bg);
      color: var(--text);
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding: 72px 16px 40px;
      overflow-x: hidden;
    }

    button { font: inherit; color: inherit; cursor: pointer; }

    /* ---------- Fundo ---------- */
    .bg {
      position: fixed;
      inset: 0;
      z-index: -2;
      background:
        radial-gradient(ellipse at 50% 0%, rgba(255,255,255,0.06), transparent 60%),
        linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px) 0 0 / 44px 44px,
        linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px) 0 0 / 44px 44px,
        var(--bg);
      -webkit-mask-image: radial-gradient(ellipse at 50% 40%, #000 30%, transparent 85%);
      mask-image: radial-gradient(ellipse at 50% 40%, #000 30%, transparent 85%);
    }
    .grain {
      position: fixed;
      inset: 0;
      z-index: -1;
      pointer-events: none;
      background-image: radial-gradient(rgba(255,255,255,0.07) 1px, transparent 1px);
      background-size: 3px 3px;
      opacity: 0.2;
    }
    .spotlight {
      position: fixed;
      inset: 0;
      z-index: -1;
      pointer-events: none;
      background: radial-gradient(420px circle at var(--mx, 50%) var(--my, 30%), rgba(255, 255, 255, 0.06), transparent 60%);
    }

    /* ---------- Criatura ---------- */
    #creature {
      position: fixed;
      inset: 0;
      z-index: 30;
      pointer-events: none;
      mix-blend-mode: difference;
    }

    /* ---------- Barra de ferramentas ---------- */
    .toolbar {
      position: fixed;
      top: 14px;
      right: 14px;
      display: flex;
      gap: 8px;
      z-index: 20;
      opacity: 0;
      animation: fadeUp 0.6s ease 1s forwards;
    }
    .tool {
      height: 42px;
      min-width: 42px;
      padding: 0 10px;
      border-radius: 12px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      background: rgba(0, 0, 0, 0.6);
      border: 1px solid var(--card-border);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      font-size: 0.8rem;
      font-weight: 500;
      transition: transform 0.25s, border-color 0.25s, box-shadow 0.25s;
    }
    .tool:hover, .tool:focus-visible {
      transform: translateY(-2px);
      border-color: rgba(255, 255, 255, 0.6);
      box-shadow: 0 0 20px -6px var(--glow);
      outline: none;
    }
    .tool svg { width: 20px; height: 20px; stroke: currentColor; fill: none; stroke-width: 2; stroke-linecap: round; stroke-linejoin: round; }
    .tool .emoji { filter: grayscale(1) brightness(1.4); font-size: 1rem; }

    /* ---------- Container ---------- */
    .container {
      width: 100%;
      max-width: 480px;
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
    }

    /* ---------- Avatar ---------- */
    .avatar-wrap {
      position: relative;
      width: 112px;
      height: 112px;
      margin-bottom: 22px;
      opacity: 0;
      animation: popIn 0.8s cubic-bezier(.2,.9,.3,1.3) 0.1s forwards;
      cursor: pointer;
      -webkit-tap-highlight-color: transparent;
    }
    .avatar-wrap:active .avatar { transform: scale(0.94); }
    .avatar-ring {
      position: absolute;
      inset: -3px;
      border-radius: 50%;
      background: conic-gradient(from 0deg, #fff, #222 25%, #888 50%, #111 75%, #fff);
      animation: spin 5s linear infinite;
    }
    .avatar-ring::after {
      content: "";
      position: absolute;
      inset: -6px;
      border-radius: 50%;
      background: inherit;
      filter: blur(16px);
      opacity: 0.35;
      z-index: -1;
    }
    .avatar {
      position: absolute;
      inset: 0;
      border-radius: 50%;
      background: radial-gradient(circle at 30% 25%, #1c1c1c, #050505 70%);
      border: 3px solid var(--bg);
      display: grid;
      place-items: center;
      font-size: 2.4rem;
      font-weight: 800;
      letter-spacing: -0.02em;
      color: #fff;
      animation: breathe 4s ease-in-out infinite;
      user-select: none;
      transition: transform 0.15s;
    }
    .status-dot {
      position: absolute;
      right: 6px;
      bottom: 8px;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      background: #fff;
      border: 3px solid var(--bg);
      animation: pulse 2.2s infinite;
    }

    @keyframes spin    { to { transform: rotate(360deg); } }
    @keyframes breathe { 0%,100% { scale: 1; } 50% { scale: 1.03; } }
    @keyframes pulse {
      0%   { box-shadow: 0 0 0 0 rgba(255, 255, 255, 0.5); }
      70%  { box-shadow: 0 0 0 10px rgba(255, 255, 255, 0); }
      100% { box-shadow: 0 0 0 0 rgba(255, 255, 255, 0); }
    }
    @keyframes popIn {
      from { opacity: 0; transform: scale(0.6) translateY(10px); }
      to   { opacity: 1; transform: scale(1) translateY(0); }
    }

    /* ---------- Textos ---------- */
    h1 {
      font-size: clamp(1.5rem, 5vw, 1.9rem);
      font-weight: 800;
      letter-spacing: -0.02em;
      margin-bottom: 8px;
    }
    .handle {
      font-family: "JetBrains Mono", ui-monospace, monospace;
      font-size: 0.85rem;
      color: var(--muted);
      margin-bottom: 24px;
      min-height: 1.4em;
    }
    .handle::before { content: "> "; color: var(--faint); }
    .handle .cursor {
      display: inline-block;
      width: 8px;
      height: 1em;
      background: #fff;
      margin-left: 3px;
      vertical-align: -2px;
      animation: blink 1s steps(1) infinite;
    }
    @keyframes blink { 50% { opacity: 0; } }

    .fade-up {
      opacity: 0;
      transform: translateY(16px);
      animation: fadeUp 0.7s cubic-bezier(.2,.8,.2,1) forwards;
      animation-delay: var(--d, 0s);
    }
    @keyframes fadeUp { to { opacity: 1; transform: translateY(0); } }

    /* ---------- Sobre mim ---------- */
    .about {
      width: 100%;
      margin-bottom: 18px;
      border-radius: 14px;
      background: var(--card);
      border: 1px solid var(--card-border);
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
      text-align: left;
      overflow: hidden;
    }
    .about-toggle {
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
      padding: 12px 16px;
      background: none;
      border: 0;
      font-weight: 600;
      font-size: 0.92rem;
    }
    .about-toggle:focus-visible { outline: 2px solid #fff; outline-offset: -2px; border-radius: 14px; }
    .about-toggle .chev {
      width: 18px; height: 18px;
      stroke: var(--muted); fill: none; stroke-width: 2; stroke-linecap: round; stroke-linejoin: round;
      transition: transform 0.35s;
    }
    .about.open .chev { transform: rotate(180deg); }
    .about-body {
      display: grid;
      grid-template-rows: 0fr;
      transition: grid-template-rows 0.4s cubic-bezier(.2,.8,.2,1);
    }
    .about.open .about-body { grid-template-rows: 1fr; }
    .about-inner { overflow: hidden; }
    .about-content { padding: 0 16px 16px; }
    .about-content p { font-size: 0.9rem; line-height: 1.55; color: var(--muted); margin-bottom: 12px; }
    .meta { display: flex; flex-wrap: wrap; gap: 6px 14px; font-size: 0.8rem; color: var(--muted); margin-bottom: 12px; }
    .chips { display: flex; flex-wrap: wrap; gap: 6px; }
    .chip {
      padding: 5px 10px;
      font-family: "JetBrains Mono", ui-monospace, monospace;
      font-size: 0.74rem;
      border-radius: 6px;
      border: 1px solid var(--card-border);
      color: rgba(255,255,255,0.8);
      transition: background 0.2s, color 0.2s, transform 0.2s;
    }
    .chip:hover { background: #fff; color: #000; transform: translateY(-2px); }

    /* ---------- Links ---------- */
    .links {
      list-style: none;
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 12px;
    }
    .link {
      --rx: 0deg;
      --ry: 0deg;
      position: relative;
      display: flex;
      align-items: center;
      gap: 14px;
      width: 100%;
      padding: 14px 16px;
      border-radius: 14px;
      text-decoration: none;
      color: var(--text);
      background: var(--card);
      border: 1px solid var(--card-border);
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
      overflow: hidden;
      transform: perspective(700px) rotateX(var(--rx)) rotateY(var(--ry));
      transition: transform 0.35s cubic-bezier(.2,.8,.2,1), box-shadow 0.35s, border-color 0.35s, background 0.35s;
      -webkit-tap-highlight-color: transparent;
      will-change: transform;
    }
    .link.tilting { transition: transform 0.08s linear, box-shadow 0.35s, border-color 0.35s, background 0.35s; }

    .link::before {
      content: "";
      position: absolute;
      inset: 0;
      background: radial-gradient(220px circle at var(--x, 50%) var(--y, 50%), rgba(255,255,255,0.12), transparent 70%);
      opacity: 0;
      transition: opacity 0.3s;
      pointer-events: none;
    }
    .link::after {
      content: "";
      position: absolute;
      top: 0;
      left: -120%;
      width: 60%;
      height: 100%;
      background: linear-gradient(110deg, transparent, rgba(255,255,255,0.10), transparent);
      transform: skewX(-20deg);
      transition: left 0.7s ease;
      pointer-events: none;
    }

    .link:hover,
    .link:focus-visible {
      transform: perspective(700px) rotateX(var(--rx)) rotateY(var(--ry)) translateY(-4px) scale(1.015);
      border-color: rgba(255, 255, 255, 0.7);
      background: var(--card-hover);
      box-shadow: 0 10px 30px -10px rgba(255,255,255,0.25), 0 0 30px -10px var(--glow);
      outline: none;
    }
    .link:hover::before, .link:focus-visible::before { opacity: 1; }
    .link:hover::after, .link:focus-visible::after { left: 140%; }
    .link:active { transform: perspective(700px) translateY(-2px) scale(0.99); }

    .icon {
      flex-shrink: 0;
      width: 44px;
      height: 44px;
      border-radius: 10px;
      display: grid;
      place-items: center;
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--card-border);
      transition: background 0.3s, transform 0.4s cubic-bezier(.2,.8,.2,1.4);
      position: relative;
      z-index: 1;
    }
    .icon svg { width: 22px; height: 22px; fill: #fff; transition: fill 0.3s; }
    .link:hover .icon { background: #fff; transform: rotate(-8deg) scale(1.06); }
    .link:hover .icon svg { fill: #000; }

    .label {
      flex: 1;
      text-align: left;
      display: flex;
      flex-direction: column;
      gap: 2px;
      min-width: 0;
      position: relative;
      z-index: 1;
    }
    .label strong { font-size: 1rem; font-weight: 600; }
    .label small {
      font-family: "JetBrains Mono", ui-monospace, monospace;
      font-size: 0.74rem;
      color: var(--muted);
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }

    .arrow {
      flex-shrink: 0;
      width: 20px; height: 20px;
      stroke: var(--faint); fill: none; stroke-width: 2; stroke-linecap: round; stroke-linejoin: round;
      transition: transform 0.35s, stroke 0.35s;
      position: relative;
      z-index: 1;
    }
    .link:hover .arrow { transform: translateX(4px); stroke: #fff; }

    .links li {
      opacity: 0;
      transform: translateY(24px) scale(0.97);
      animation: cascade 0.65s cubic-bezier(.2,.8,.2,1) forwards;
      animation-delay: calc(0.65s + var(--i) * 0.12s);
    }
    @keyframes cascade { to { opacity: 1; transform: translateY(0) scale(1); } }

    .ripple {
      position: absolute;
      border-radius: 50%;
      transform: scale(0);
      background: rgba(255,255,255,0.25);
      animation: ripple 0.6s ease-out forwards;
      pointer-events: none;
      z-index: 0;
    }
    @keyframes ripple { to { transform: scale(4); opacity: 0; } }

    footer {
      margin-top: 40px;
      font-size: 0.76rem;
      color: var(--faint);
    }
    footer .hint { display: block; margin-top: 6px; font-family: "JetBrains Mono", ui-monospace, monospace; font-size: 0.7rem; opacity: 0.6; }

    /* ---------- Modal QR ---------- */
    .modal {
      position: fixed;
      inset: 0;
      z-index: 50;
      display: grid;
      place-items: center;
      padding: 16px;
      background: rgba(0, 0, 0, 0.75);
      backdrop-filter: blur(6px);
      -webkit-backdrop-filter: blur(6px);
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.25s;
    }
    .modal.open { opacity: 1; pointer-events: auto; }
    .modal-card {
      width: 100%;
      max-width: 320px;
      padding: 24px;
      border-radius: 18px;
      background: var(--surface);
      border: 1px solid var(--card-border);
      text-align: center;
      transform: scale(0.92) translateY(10px);
      transition: transform 0.3s cubic-bezier(.2,.9,.3,1.3);
      box-shadow: 0 0 60px -20px var(--glow);
    }
    .modal.open .modal-card { transform: none; }
    .modal-card h2 { font-size: 1.1rem; margin-bottom: 4px; }
    .modal-card p { font-size: 0.85rem; color: var(--muted); margin-bottom: 16px; }
    #qr {
      width: 216px;
      height: 216px;
      margin: 0 auto 16px;
      padding: 8px;
      background: #fff;
      border-radius: 12px;
      display: grid;
      place-items: center;
      color: #333;
      font-size: 0.8rem;
    }
    #qr img, #qr canvas { width: 200px !important; height: 200px !important; }
    .modal-actions { display: flex; gap: 8px; }
    .btn {
      flex: 1;
      padding: 10px 12px;
      border-radius: 10px;
      font-size: 0.88rem;
      font-weight: 600;
      border: 1px solid var(--card-border);
      background: transparent;
      transition: transform 0.2s, background 0.2s;
    }
    .btn:hover { transform: translateY(-2px); background: rgba(255,255,255,0.06); }
    .btn.primary { border-color: #fff; background: #fff; color: #000; }
    .btn.primary:hover { background: #ddd; }

    /* ---------- Toast ---------- */
    .toast {
      position: fixed;
      left: 50%;
      bottom: 24px;
      z-index: 60;
      padding: 10px 18px;
      border-radius: 999px;
      font-size: 0.86rem;
      font-weight: 500;
      background: #fff;
      color: #000;
      transform: translate(-50%, 30px);
      opacity: 0;
      transition: transform 0.35s cubic-bezier(.2,.9,.3,1.3), opacity 0.35s;
      pointer-events: none;
      white-space: nowrap;
    }
    .toast.show { transform: translate(-50%, 0); opacity: 1; }

    #confetti { position: fixed; inset: 0; z-index: 40; pointer-events: none; }

    .shake { animation: shake 0.5s; }
    @keyframes shake {
      10%, 90% { transform: translateX(-2px); }
      20%, 80% { transform: translateX(4px); }
      30%, 50%, 70% { transform: translateX(-6px); }
      40%, 60% { transform: translateX(6px); }
    }

    /* ---------- Responsivo ---------- */
    @media (min-width: 600px) {
      body { padding-top: 88px; }
      .avatar-wrap { width: 128px; height: 128px; }
      .avatar { font-size: 2.8rem; }
      .link { padding: 16px 20px; }
      .links { gap: 14px; }
    }
    @media (max-width: 420px) {
      .tool .tool-label { display: none; }
    }
    @media (hover: none) {
      .link:hover { transform: none; }
    }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
      }
    }
  </style>
</head>
<body>
  <div class="bg" aria-hidden="true"></div>
  <div class="grain" aria-hidden="true"></div>
  <div class="spotlight" aria-hidden="true"></div>
  <canvas id="creature" aria-hidden="true"></canvas>
  <canvas id="confetti" aria-hidden="true"></canvas>

  <!-- Barra de ferramentas -->
  <div class="toolbar">
    <button class="tool" id="creatureBtn" aria-label="Trocar criatura" title="Trocar criatura">
      <span class="emoji" id="creatureIcon">🐉</span><span class="tool-label" id="creatureLabel">Dragão</span>
    </button>
    <button class="tool" id="qrBtn" aria-label="Mostrar QR Code" title="QR Code">
      <svg viewBox="0 0 24 24"><rect x="3" y="3" width="7" height="7" rx="1"/><rect x="14" y="3" width="7" height="7" rx="1"/><rect x="3" y="14" width="7" height="7" rx="1"/><path d="M14 14h3v3h-3zM20 14v.01M14 20h.01M17 17h4v4h-4"/></svg>
    </button>
    <button class="tool" id="shareBtn" aria-label="Compartilhar" title="Compartilhar">
      <svg viewBox="0 0 24 24"><circle cx="18" cy="5" r="3"/><circle cx="6" cy="12" r="3"/><circle cx="18" cy="19" r="3"/><path d="M8.6 13.5l6.8 4M15.4 6.5l-6.8 4"/></svg>
    </button>
  </div>

  <main class="container">
    <div class="avatar-wrap" id="avatar" title="Psiu... tente clicar 5 vezes 👀">
      <div class="avatar-ring"></div>
      <div class="avatar">AJ</div>
      <div class="status-dot" title="Online"></div>
    </div>

    <h1 class="fade-up" style="--d: .3s">Alexandre Júnior</h1>
    <p class="handle fade-up" style="--d: .42s"><span id="typed"></span><span class="cursor"></span></p>

    <!-- Sobre mim (edite os textos abaixo) -->
    <section class="about fade-up" id="about" style="--d: .55s">
      <button class="about-toggle" id="aboutToggle" aria-expanded="false" aria-controls="aboutBody">
        <span>Sobre mim</span>
        <svg class="chev" viewBox="0 0 24 24" aria-hidden="true"><path d="M6 9l6 6 6-6"/></svg>
      </button>
      <div class="about-body" id="aboutBody">
        <div class="about-inner">
          <div class="about-content">
            <p>Profissional de tecnologia apaixonado por desenvolvimento, criando projetos e compartilhando o que aprendo no caminho.</p>
            <div class="meta">
              <span>📍 Brasil</span>
              <span>💼 Tecnologia da Informação</span>
            </div>
            <div class="chips">
              <span class="chip">HTML</span>
              <span class="chip">CSS</span>
              <span class="chip">JavaScript</span>
              <span class="chip">Python</span>
              <span class="chip">Git</span>
              <span class="chip">GitHub</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <ul class="links">
      <li style="--i: 0">
        <a class="link" href="https://instagram.com/SEU_USUARIO" target="_blank" rel="noopener noreferrer">
          <span class="icon">
            <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 2.16c3.2 0 3.58.01 4.85.07 1.17.05 1.8.25 2.23.41.56.22.96.48 1.38.9.42.42.68.82.9 1.38.16.42.36 1.06.41 2.23.06 1.27.07 1.65.07 4.85s-.01 3.58-.07 4.85c-.05 1.17-.25 1.8-.41 2.23-.22.56-.48.96-.9 1.38-.42.42-.82.68-1.38.9-.42.16-1.06.36-2.23.41-1.27.06-1.65.07-4.85.07s-3.58-.01-4.85-.07c-1.17-.05-1.8-.25-2.23-.41a3.72 3.72 0 0 1-1.38-.9 3.72 3.72 0 0 1-.9-1.38c-.16-.42-.36-1.06-.41-2.23C2.17 15.58 2.16 15.2 2.16 12s.01-3.58.07-4.85c.05-1.17.25-1.8.41-2.23.22-.56.48-.96.9-1.38.42-.42.82-.68 1.38-.9.42-.16 1.06-.36 2.23-.41C8.42 2.17 8.8 2.16 12 2.16M12 0C8.74 0 8.33.01 7.05.07 5.78.13 4.9.33 4.14.63c-.79.3-1.46.72-2.13 1.38A5.88 5.88 0 0 0 .63 4.14C.33 4.9.13 5.78.07 7.05.01 8.33 0 8.74 0 12s.01 3.67.07 4.95c.06 1.27.26 2.15.56 2.91.3.79.72 1.46 1.38 2.13a5.88 5.88 0 0 0 2.13 1.38c.76.3 1.64.5 2.91.56C8.33 23.99 8.74 24 12 24s3.67-.01 4.95-.07c1.27-.06 2.15-.26 2.91-.56a5.88 5.88 0 0 0 2.130-1.38 5.88 5.88 0 0 0 1.38-2.13c.3-.76.5-1.64.56-2.91.06-1.28.07-1.69.07-4.95s-.01-3.67-.07-4.95c-.06-1.27-.26-2.15-.56-2.91a5.88 5.88 0 0 0-1.38-2.13A5.88 5.88 0 0 0 19.86.63C19.1.33 18.22.13 16.95.07 15.67.01 15.26 0 12 0zm0 5.84a6.16 6.16 0 1 0 0 12.32 6.16 6.16 0 0 0 0-12.32zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.4-11.85a1.44 1.44 0 1 0 0 2.88 1.44 1.44 0 0 0 0-2.88z"/></svg>
          </span>
          <span class="label"><strong>Instagram</strong><small>@SEU_USUARIO</small></span>
          <svg class="arrow" viewBox="0 0 24 24" aria-hidden="true"><path d="M5 12h14M13 6l6 6-6 6"/></svg>
        </a>
      </li>

      <li style="--i: 1">
        <a class="link" href="https://github.com/SEU_USUARIO" target="_blank" rel="noopener noreferrer">
          <span class="icon">
            <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 .3a12 12 0 0 0-3.8 23.38c.6.12.83-.26.83-.57L9 21.07c-3.34.72-4.04-1.61-4.04-1.61-.55-1.39-1.34-1.76-1.34-1.76-1.08-.74.09-.73.09-.73 1.2.09 1.83 1.24 1.83 1.24 1.07 1.83 2.81 1.3 3.5 1 .1-.78.42-1.31.76-1.61-2.67-.3-5.47-1.33-5.47-5.93 0-1.31.47-2.38 1.24-3.22-.14-.3-.54-1.52.1-3.18 0 0 1-.32 3.3 1.23a11.5 11.5 0 0 1 6 0c2.28-1.55 3.29-1.23 3.29-1.23.64 1.66.24 2.88.12 3.18a4.65 4.65 0 0 1 1.23 3.22c0 4.61-2.8 5.63-5.48 5.92.42.36.81 1.1.81 2.22l-.01 3.29c0 .31.2.69.82.57A12 12 0 0 0 12 .3"/></svg>
          </span>
          <span class="label"><strong>GitHub</strong><small>github.com/SEU_USUARIO</small></span>
          <svg class="arrow" viewBox="0 0 24 24" aria-hidden="true"><path d="M5 12h14M13 6l6 6-6 6"/></svg>
        </a>
      </li>

      <li style="--i: 2">
        <a class="link" href="https://linkedin.com/in/SEU_USUARIO" target="_blank" rel="noopener noreferrer">
          <span class="icon">
            <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M20.45 20.45h-3.56v-5.57c0-1.33-.02-3.04-1.85-3.04-1.85 0-2.14 1.45-2.14 2.94v5.67H9.35V9h3.41v1.56h.05c.48-.9 1.64-1.85 3.37-1.85 3.6 0 4.27 2.37 4.27 5.46v6.28zM5.34 7.43a2.06 2.06 0 1 1 0-4.13 2.06 2.06 0 0 1 0 4.13zM7.12 20.45H3.56V9h3.56v11.45zM22.22 0H1.77C.79 0 0 .77 0 1.73v20.54C0 23.23.79 24 1.77 24h20.45c.98 0 1.78-.77 1.78-1.73V1.73C24 .77 23.2 0 22.22 0z"/></svg>
          </span>
          <span class="label"><strong>LinkedIn</strong><small>in/SEU_USUARIO</small></span>
          <svg class="arrow" viewBox="0 0 24 24" aria-hidden="true"><path d="M5 12h14M13 6l6 6-6 6"/></svg>
        </a>
      </li>

      <li style="--i: 3">
        <a class="link" href="https://tiktok.com/@SEU_USUARIO" target="_blank" rel="noopener noreferrer">
          <span class="icon">
            <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12.53.02C13.84 0 15.14.01 16.44 0c.08 1.53.63 3.09 1.75 4.17 1.12 1.11 2.7 1.62 4.24 1.79v4.03c-1.44-.05-2.89-.35-4.2-.97-.57-.26-1.1-.59-1.62-.93-.01 2.92.01 5.84-.02 8.75-.08 1.4-.54 2.79-1.35 3.94-1.31 1.92-3.58 3.17-5.91 3.21-1.43.08-2.86-.31-4.08-1.03-2.02-1.19-3.44-3.37-3.65-5.71-.02-.5-.03-1-.01-1.49.18-1.9 1.12-3.72 2.58-4.96 1.66-1.44 3.98-2.13 6.15-1.72.02 1.48-.04 2.96-.04 4.44-.99-.32-2.15-.23-3.02.37-.63.41-1.11 1.04-1.36 1.75-.21.51-.15 1.07-.14 1.61.24 1.64 1.82 3.02 3.5 2.87 1.12-.01 2.19-.66 2.77-1.61.19-.33.4-.67.41-1.06.1-1.79.06-3.57.07-5.36.01-4.03-.01-8.05.02-12.07z"/></svg>
          </span>
          <span class="label"><strong>TikTok</strong><small>@SEU_USUARIO</small></span>
          <svg class="arrow" viewBox="0 0 24 24" aria-hidden="true"><path d="M5 12h14M13 6l6 6-6 6"/></svg>
        </a>
      </li>
    </ul>

    <footer class="fade-up" style="--d: 1.2s">
      © <span id="year"></span> Alexandre Júnior
      <span class="hint">↑↑↓↓←→←→BA</span>
    </footer>
  </main>

  <!-- Modal QR Code -->
  <div class="modal" id="qrModal" role="dialog" aria-modal="true" aria-labelledby="qrTitle">
    <div class="modal-card">
      <h2 id="qrTitle">Escaneie para abrir</h2>
      <p>Aponte a câmera do celular</p>
      <div id="qr">Gerando QR…</div>
      <div class="modal-actions">
        <button class="btn" id="copyBtn">Copiar link</button>
        <button class="btn primary" id="closeQr">Fechar</button>
      </div>
    </div>
  </div>

  <div class="toast" id="toast" role="status" aria-live="polite"></div>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
  <script>
    (function () {
      var root = document.documentElement;
      var pageUrl = location.href.split("#")[0];
      var dpr = window.devicePixelRatio || 1;
      document.getElementById("year").textContent = new Date().getFullYear();

      // ---------- Toast ----------
      var toastEl = document.getElementById("toast");
      var toastTimer;
      function toast(msg) {
        toastEl.textContent = msg;
        toastEl.classList.add("show");
        clearTimeout(toastTimer);
        toastTimer = setTimeout(function () { toastEl.classList.remove("show"); }, 2200);
      }

      // ---------- Digitação no subtítulo ----------
      var phrases = ["desenvolvedor", "criador de conteúdo", "sempre aprendendo"];
      var el = document.getElementById("typed");
      var p = 0, c = 0, deleting = false;
      function type() {
        var word = phrases[p];
        el.textContent = word.slice(0, c);
        if (!deleting && c < word.length) { c++; setTimeout(type, 75); }
        else if (!deleting) { deleting = true; setTimeout(type, 1600); }
        else if (c > 0) { c--; setTimeout(type, 35); }
        else { deleting = false; p = (p + 1) % phrases.length; setTimeout(type, 300); }
      }
      setTimeout(type, 700);

      // ---------- Sobre mim ----------
      var about = document.getElementById("about");
      var aboutToggle = document.getElementById("aboutToggle");
      aboutToggle.addEventListener("click", function () {
        var open = about.classList.toggle("open");
        aboutToggle.setAttribute("aria-expanded", open);
      });

      // ---------- QR Code ----------
      var modal = document.getElementById("qrModal");
      var qrBox = document.getElementById("qr");
      var qrMade = false;
      function openQr() {
        if (!qrMade) {
          if (window.QRCode) {
            qrBox.textContent = "";
            new QRCode(qrBox, { text: pageUrl, width: 200, height: 200, colorDark: "#000000", colorLight: "#ffffff" });
            qrMade = true;
          } else {
            qrBox.textContent = "Não foi possível gerar o QR agora.";
          }
        }
        modal.classList.add("open");
      }
      function closeQr() { modal.classList.remove("open"); }
      document.getElementById("qrBtn").addEventListener("click", openQr);
      document.getElementById("closeQr").addEventListener("click", closeQr);
      modal.addEventListener("click", function (e) { if (e.target === modal) closeQr(); });

      // ---------- Copiar / compartilhar ----------
      function copyLink() {
        if (navigator.clipboard) {
          navigator.clipboard.writeText(pageUrl).then(
            function () { toast("Link copiado!"); },
            function () { toast(pageUrl); }
          );
        } else {
          toast(pageUrl);
        }
      }
      document.getElementById("copyBtn").addEventListener("click", copyLink);
      document.getElementById("shareBtn").addEventListener("click", function () {
        if (navigator.share) {
          navigator.share({ title: "Alexandre Júnior", text: "Meus links 👇", url: pageUrl }).catch(function () {});
        } else {
          copyLink();
        }
      });

      // ---------- Mouse ----------
      var mouse = { x: innerWidth / 2, y: innerHeight * 0.7, last: -1e9 };
      window.addEventListener("pointermove", function (e) {
        mouse.x = e.clientX;
        mouse.y = e.clientY;
        mouse.last = performance.now();
        root.style.setProperty("--mx", e.clientX + "px");
        root.style.setProperty("--my", e.clientY + "px");
      }, { passive: true });
      document.addEventListener("mouseleave", function () { mouse.last = -1e9; });

      // ---------- Cards: inclinação 3D, brilho e ripple ----------
      var canHover = window.matchMedia("(hover: hover)").matches;
      document.querySelectorAll(".link").forEach(function (card) {
        card.addEventListener("pointermove", function (e) {
          var r = card.getBoundingClientRect();
          var x = e.clientX - r.left;
          var y = e.clientY - r.top;
          card.style.setProperty("--x", x + "px");
          card.style.setProperty("--y", y + "px");
          if (canHover) {
            card.classList.add("tilting");
            card.style.setProperty("--ry", ((x / r.width) - 0.5) * 10 + "deg");
            card.style.setProperty("--rx", (0.5 - (y / r.height)) * 14 + "deg");
          }
        });
        card.addEventListener("pointerleave", function () {
          card.classList.remove("tilting");
          card.style.setProperty("--rx", "0deg");
          card.style.setProperty("--ry", "0deg");
        });
        card.addEventListener("pointerdown", function (e) {
          var r = card.getBoundingClientRect();
          var size = Math.max(r.width, r.height);
          var span = document.createElement("span");
          span.className = "ripple";
          span.style.width = span.style.height = size + "px";
          span.style.left = (e.clientX - r.left - size / 2) + "px";
          span.style.top = (e.clientY - r.top - size / 2) + "px";
          card.appendChild(span);
          setTimeout(function () { span.remove(); }, 650);
        });
      });

      // =====================================================
      //  CRIATURA QUE SEGUE O MOUSE (dragão / aranha)
      // =====================================================
      var cv = document.getElementById("creature");
      var cx = cv.getContext("2d");
      var W, H;
      function sizeCreature() {
        W = innerWidth; H = innerHeight;
        cv.width = W * dpr; cv.height = H * dpr;
        cx.setTransform(dpr, 0, 0, dpr, 0, 0);
      }
      sizeCreature();
      window.addEventListener("resize", sizeCreature);

      var baseScale = function () { return W < 600 ? 0.72 : 1; };
      var k = baseScale(), kTarget = k;

      function angDiff(a, b) { return Math.atan2(Math.sin(b - a), Math.cos(b - a)); }

      // Sem mouse por 3s (ou no celular sem toque): passeia sozinho
      function target(t) {
        if (t - mouse.last < 3000) return mouse;
        return {
          x: W / 2 + Math.cos(t / 2300) * W * 0.36,
          y: H / 2 + Math.sin(t / 1400) * H * 0.32
        };
      }

      // ---------- Dragão ----------
      var DN = 46;
      var dragon = { pts: [], a: -Math.PI / 2, t: 0, speed: 0 };
      function initDragon() {
        dragon.pts = [];
        for (var i = 0; i < DN; i++) dragon.pts.push({ x: W / 2, y: H * 0.85 + i * 6 });
        dragon.a = -Math.PI / 2;
      }
      function dWidth(i) {
        var u = i / (DN - 1);
        if (u < 0.07) return k * (6 + (u / 0.07) * 5);
        if (u < 0.3) return k * 11;
        return k * (11 * (1 - (u - 0.3) / 0.7) + 0.8);
      }
      function updateDragon(tg) {
        var h = dragon.pts[0];
        var dx = tg.x - h.x, dy = tg.y - h.y, d = Math.hypot(dx, dy);
        if (d > 12) dragon.a += angDiff(dragon.a, Math.atan2(dy, dx)) * 0.09;
        var sp = Math.min(d * 0.06, 8 * k);
        dragon.speed = sp;
        dragon.t += 0.04 + sp * 0.025;
        var wig = Math.sin(dragon.t * 1.4) * sp * 0.18;
        h.x += Math.cos(dragon.a) * sp - Math.sin(dragon.a) * wig;
        h.y += Math.sin(dragon.a) * sp + Math.cos(dragon.a) * wig;
        var gap = 6.5 * k;
        for (var i = 1; i < DN; i++) {
          var a = dragon.pts[i - 1], b = dragon.pts[i];
          var ang = Math.atan2(a.y - b.y, a.x - b.x);
          b.x = a.x - Math.cos(ang) * gap;
          b.y = a.y - Math.sin(ang) * gap;
        }
      }
      function drawDragon() {
        var P = dragon.pts, L = [], R = [], A = [];
        for (var i = 0; i < DN; i++) {
          var ang = i === 0 ? dragon.a : Math.atan2(P[i - 1].y - P[i].y, P[i - 1].x - P[i].x);
          var w = dWidth(i), nx = -Math.sin(ang), ny = Math.cos(ang);
          A.push(ang);
          L.push({ x: P[i].x + nx * w, y: P[i].y + ny * w });
          R.push({ x: P[i].x - nx * w, y: P[i].y - ny * w });
        }
        cx.lineCap = "round";
        cx.lineJoin = "round";
        cx.strokeStyle = "#fff";
        cx.shadowColor = "rgba(255,255,255,0.45)";
        cx.shadowBlur = 8;

        // Asas (batendo)
        var flap = 0.55 + 0.45 * Math.sin(dragon.t * 1.7);
        [-1, 1].forEach(function (s) {
          var wi = 8, ang = A[wi];
          var fx = Math.cos(ang), fy = Math.sin(ang), sx = -Math.sin(ang) * s, sy = Math.cos(ang) * s;
          var S = s > 0 ? L[wi] : R[wi];
          function pt(x, y) { return { x: S.x + (fx * x + sx * y) * k, y: S.y + (fy * x + sy * y) * k }; }
          var E = pt(8, 10 + 26 * flap);
          var tips = [pt(-2, 14 + 58 * flap), pt(-24, 12 + 52 * flap), pt(-42, 8 + 38 * flap), pt(-52, 5 + 20 * flap)];
          var back = s > 0 ? L[15] : R[15];
          cx.beginPath();
          cx.moveTo(S.x, S.y);
          cx.lineTo(E.x, E.y);
          cx.lineTo(tips[0].x, tips[0].y);
          for (var j = 1; j < tips.length; j++) {
            var mx = (tips[j - 1].x + tips[j].x) / 2, my = (tips[j - 1].y + tips[j].y) / 2;
            cx.quadraticCurveTo(mx + (E.x - mx) * 0.28, my + (E.y - my) * 0.28, tips[j].x, tips[j].y);
          }
          var mx2 = (tips[3].x + back.x) / 2, my2 = (tips[3].y + back.y) / 2;
          cx.quadraticCurveTo(mx2 + (E.x - mx2) * 0.25, my2 + (E.y - my2) * 0.25, back.x, back.y);
          cx.closePath();
          cx.fillStyle = "rgba(255,255,255,0.08)";
          cx.fill();
          cx.lineWidth = 1.2 * k;
          cx.stroke();
          cx.lineWidth = 2.2 * k;
          cx.beginPath();
          cx.moveTo(S.x, S.y);
          cx.lineTo(E.x, E.y);
          tips.forEach(function (tp) { cx.moveTo(E.x, E.y); cx.lineTo(tp.x, tp.y); });
          cx.stroke();
        });

        // Patas
        [5, 19].forEach(function (li, n) {
          [-1, 1].forEach(function (s) {
            var ang = A[li], H0 = s > 0 ? L[li] : R[li];
            var swing = Math.sin(dragon.t * 2.2 + (s > 0 ? 0 : Math.PI) + n * 1.7) * Math.min(1, dragon.speed / 3);
            var a1 = ang + s * (Math.PI / 2 + 0.5) + swing * 0.5;
            var K = { x: H0.x + Math.cos(a1) * 13 * k, y: H0.y + Math.sin(a1) * 13 * k };
            var a2 = ang + s * 0.5 + swing * 0.5;
            var F = { x: K.x + Math.cos(a2) * 11 * k, y: K.y + Math.sin(a2) * 11 * k };
            cx.lineWidth = 2.4 * k;
            cx.beginPath();
            cx.moveTo(H0.x, H0.y); cx.lineTo(K.x, K.y); cx.lineTo(F.x, F.y);
            cx.stroke();
            cx.lineWidth = 1.3 * k;
            cx.beginPath();
            [-0.6, 0, 0.6].forEach(function (o) {
              cx.moveTo(F.x, F.y);
              cx.lineTo(F.x + Math.cos(a2 + o) * 5 * k, F.y + Math.sin(a2 + o) * 5 * k);
            });
            cx.stroke();
          });
        });

        // Corpo
        cx.beginPath();
        cx.moveTo(L[0].x, L[0].y);
        for (i = 1; i < DN; i++) cx.lineTo(L[i].x, L[i].y);
        for (i = DN - 1; i >= 0; i--) cx.lineTo(R[i].x, R[i].y);
        cx.closePath();
        cx.fillStyle = "#000";
        cx.fill();
        cx.lineWidth = 1.6 * k;
        cx.stroke();

        // Escamas / costelas e espinhos
        cx.shadowBlur = 0;
        cx.lineWidth = 1 * k;
        cx.strokeStyle = "rgba(255,255,255,0.4)";
        cx.beginPath();
        for (i = 3; i < DN - 2; i += 2) {
          cx.moveTo(L[i].x, L[i].y);
          cx.quadraticCurveTo(P[i].x - Math.cos(A[i]) * 3 * k, P[i].y - Math.sin(A[i]) * 3 * k, R[i].x, R[i].y);
        }
        cx.stroke();
        cx.strokeStyle = "#fff";
        cx.lineWidth = 1.3 * k;
        cx.beginPath();
        for (i = 2; i < DN * 0.9; i += 2) {
          var ca = Math.cos(A[i]), sa = Math.sin(A[i]), sz = Math.max(1.5, dWidth(i) * 0.3);
          cx.moveTo(P[i].x - sa * sz - ca * sz * 1.4, P[i].y + ca * sz - sa * sz * 1.4);
          cx.lineTo(P[i].x, P[i].y);
          cx.lineTo(P[i].x + sa * sz - ca * sz * 1.4, P[i].y - ca * sz - sa * sz * 1.4);
        }
        cx.stroke();

        // Ponta da cauda
        var T = P[DN - 1], ta = A[DN - 1];
        cx.save();
        cx.translate(T.x, T.y);
        cx.rotate(ta);
        cx.scale(k, k);
        cx.beginPath();
        cx.moveTo(2, 0); cx.lineTo(-6, -5); cx.lineTo(-14, 0); cx.lineTo(-6, 5); cx.closePath();
        cx.fillStyle = "#fff";
        cx.fill();
        cx.restore();

        // Cabeça
        var Hd = P[0];
        cx.save();
        cx.translate(Hd.x, Hd.y);
        cx.rotate(dragon.a);
        cx.scale(k, k);
        cx.shadowColor = "rgba(255,255,255,0.5)";
        cx.shadowBlur = 10;
        cx.strokeStyle = "#fff";
        cx.lineWidth = 1.6;
        // chifres
        cx.beginPath();
        cx.moveTo(-2, -7); cx.quadraticCurveTo(-14, -16, -28, -13);
        cx.moveTo(4, -8);  cx.quadraticCurveTo(-4, -20, -16, -22);
        cx.moveTo(-2, 7);  cx.quadraticCurveTo(-14, 16, -28, 13);
        cx.moveTo(4, 8);   cx.quadraticCurveTo(-4, 20, -16, 22);
        cx.stroke();
        // bigodes
        var wv = Math.sin(dragon.t * 2) * 5;
        cx.lineWidth = 1;
        cx.beginPath();
        cx.moveTo(24, -3); cx.quadraticCurveTo(30, -18 + wv, 8, -26 - wv);
        cx.moveTo(24, 3);  cx.quadraticCurveTo(30, 18 - wv, 8, 26 + wv);
        cx.stroke();
        // crânio
        cx.beginPath();
        cx.moveTo(-6, -9);
        cx.quadraticCurveTo(6, -12, 16, -6);
        cx.lineTo(27, -3); cx.lineTo(29, 0); cx.lineTo(27, 3);
        cx.lineTo(16, 6);
        cx.quadraticCurveTo(6, 12, -6, 9);
        cx.closePath();
        cx.fillStyle = "#000";
        cx.fill();
        cx.lineWidth = 1.8;
        cx.stroke();
        // olhos e narinas
        cx.shadowBlur = 12;
        cx.fillStyle = "#fff";
        cx.beginPath();
        cx.ellipse(10, -5, 3, 1.6, 0.3, 0, Math.PI * 2);
        cx.ellipse(10, 5, 3, 1.6, -0.3, 0, Math.PI * 2);
        cx.fill();
        cx.beginPath();
        cx.arc(25, -1.6, 0.9, 0, Math.PI * 2);
        cx.arc(25, 1.6, 0.9, 0, Math.PI * 2);
        cx.fill();
        cx.restore();
        cx.shadowBlur = 0;
      }

      // ---------- Aranha articulada ----------
      var LEG_ANG = [0.5, 1.1, 1.85, 2.55];
      var HIP_OFF = [5, 2, -1, -4];
      var spider = { x: 0, y: 0, a: -Math.PI / 2, vx: 0, vy: 0, legs: [] };
      function legHome(s, i) {
        var R = 56 * k, ang = spider.a + s * LEG_ANG[i];
        return { x: spider.x + Math.cos(ang) * R, y: spider.y + Math.sin(ang) * R };
      }
      function legHip(s, i) {
        var f = HIP_OFF[i] * k, side = 4 * k, c = Math.cos(spider.a), sn = Math.sin(spider.a);
        return { x: spider.x + c * f - sn * side * s, y: spider.y + sn * f + c * side * s };
      }
      function initSpider(x, y) {
        spider.x = x; spider.y = y; spider.legs = [];
        for (var s = -1; s <= 1; s += 2) {
          for (var i = 0; i < 4; i++) {
            var h = legHome(s, i);
            spider.legs.push({ s: s, i: i, x: h.x, y: h.y, fx: h.x, fy: h.y, tx: h.x, ty: h.y, t: 1 });
          }
        }
      }
      function updateSpider(tg) {
        var dx = tg.x - spider.x, dy = tg.y - spider.y, d = Math.hypot(dx, dy);
        if (d > 25 * k) spider.a += angDiff(spider.a, Math.atan2(dy, dx)) * 0.12;
        var sp = Math.min(d * 0.06, 5.5 * k);
        if (d > 18 * k) { spider.vx = dx / d * sp; spider.vy = dy / d * sp; }
        else { spider.vx *= 0.8; spider.vy *= 0.8; }
        spider.x += spider.vx;
        spider.y += spider.vy;

        spider.legs.forEach(function (l) {
          if (l.t < 1) {
            l.t = Math.min(1, l.t + 0.17);
            var e = l.t < 0.5 ? 2 * l.t * l.t : 1 - Math.pow(-2 * l.t + 2, 2) / 2;
            l.x = l.fx + (l.tx - l.fx) * e;
            l.y = l.fy + (l.ty - l.fy) * e;
            return;
          }
          var h = legHome(l.s, l.i);
          var dist = Math.hypot(h.x - l.x, h.y - l.y);
          if (dist > 100 * k) { l.x = h.x; l.y = h.y; return; }
          if (dist > 18 * k) {
            // passo alternado: espera os vizinhos apoiarem antes de levantar
            var busy = spider.legs.some(function (o) {
              return o.t < 1 && ((o.s === l.s && Math.abs(o.i - l.i) === 1) || (o.s !== l.s && o.i === l.i));
            });
            if (!busy) {
              l.fx = l.x; l.fy = l.y;
              l.tx = h.x + spider.vx * 5; l.ty = h.y + spider.vy * 5;
              l.t = 0;
            }
          }
        });
      }
      function drawSpider() {
        var seg = 36 * k;
        cx.strokeStyle = "#fff";
        cx.fillStyle = "#fff";
        cx.lineCap = "round";
        cx.lineJoin = "round";
        cx.shadowColor = "rgba(255,255,255,0.4)";
        cx.shadowBlur = 6;

        spider.legs.forEach(function (l) {
          var hip = legHip(l.s, l.i);
          var dx = l.x - hip.x, dy = l.y - hip.y;
          var d = Math.min(Math.hypot(dx, dy), seg * 1.96);
          var base = Math.atan2(dy, dx);
          var a1 = Math.acos(Math.max(-1, Math.min(1, d / (2 * seg))));
          var k1 = { x: hip.x + Math.cos(base + a1) * seg, y: hip.y + Math.sin(base + a1) * seg };
          var k2 = { x: hip.x + Math.cos(base - a1) * seg, y: hip.y + Math.sin(base - a1) * seg };
          // joelho sempre para fora do corpo
          var knee = Math.hypot(k1.x - spider.x, k1.y - spider.y) > Math.hypot(k2.x - spider.x, k2.y - spider.y) ? k1 : k2;
          var lift = l.t < 1 ? Math.sin(l.t * Math.PI) : 0;
          var mx = (hip.x + l.x) / 2, my = (hip.y + l.y) / 2;
          knee = { x: knee.x + (knee.x - mx) * lift * 0.35, y: knee.y + (knee.y - my) * lift * 0.35 };
          var foot = { x: hip.x + Math.cos(base) * d, y: hip.y + Math.sin(base) * d };

          cx.lineWidth = 2.6 * k;
          cx.beginPath(); cx.moveTo(hip.x, hip.y); cx.lineTo(knee.x, knee.y); cx.stroke();
          cx.lineWidth = 1.5 * k;
          cx.beginPath(); cx.moveTo(knee.x, knee.y); cx.lineTo(foot.x, foot.y); cx.stroke();
          cx.beginPath(); cx.arc(knee.x, knee.y, 1.8 * k, 0, Math.PI * 2); cx.fill();
        });

        cx.save();
        cx.translate(spider.x, spider.y);
        cx.rotate(spider.a);
        cx.scale(k, k);
        var breath = 1 + Math.sin(performance.now() / 400) * 0.03;
        // abdômen
        cx.beginPath();
        cx.ellipse(-17, 0, 14 * breath, 11 * breath, 0, 0, Math.PI * 2);
        cx.fill();
        // desenho no abdômen
        cx.shadowBlur = 0;
        cx.fillStyle = "#000";
        cx.beginPath();
        cx.moveTo(-8, 0); cx.lineTo(-14, -3); cx.lineTo(-20, 0); cx.lineTo(-26, -3); cx.lineTo(-24, 0);
        cx.lineTo(-26, 3); cx.lineTo(-20, 0); cx.lineTo(-14, 3); cx.closePath();
        cx.fill();
        // cefalotórax
        cx.fillStyle = "#fff";
        cx.shadowBlur = 6;
        cx.beginPath();
        cx.ellipse(0, 0, 8.5, 7, 0, 0, Math.PI * 2);
        cx.fill();
        // quelíceras
        cx.lineWidth = 2;
        cx.beginPath();
        cx.moveTo(7, -2.5); cx.quadraticCurveTo(12, -3, 13, -0.5);
        cx.moveTo(7, 2.5);  cx.quadraticCurveTo(12, 3, 13, 0.5);
        cx.stroke();
        // olhos
        cx.shadowBlur = 0;
        cx.fillStyle = "#000";
        cx.beginPath();
        cx.arc(5, -2, 1.3, 0, Math.PI * 2);
        cx.arc(5, 2, 1.3, 0, Math.PI * 2);
        cx.arc(6.6, -0.8, 0.8, 0, Math.PI * 2);
        cx.arc(6.6, 0.8, 0.8, 0, Math.PI * 2);
        cx.fill();
        cx.restore();
        cx.shadowBlur = 0;
      }

      // ---------- Troca de criatura ----------
      var modes = [
        { id: "dragao", icon: "🐉", label: "Dragão" },
        { id: "aranha", icon: "🕷️", label: "Aranha" },
        { id: "off", icon: "🚫", label: "Nenhum" }
      ];
      var reduced = window.matchMedia("(prefers-reduced-motion: reduce)").matches;
      var modeIdx = reduced ? 2 : 0;
      try {
        var savedMode = localStorage.getItem("aj-creature");
        modes.forEach(function (m, i) { if (m.id === savedMode) modeIdx = i; });
      } catch (e) {}

      function applyMode(announce) {
        var m = modes[modeIdx];
        document.getElementById("creatureIcon").textContent = m.icon;
        document.getElementById("creatureLabel").textContent = m.label;
        if (m.id === "dragao") initDragon();
        if (m.id === "aranha") initSpider(W / 2, H * 0.85);
        if (m.id === "off") cx.clearRect(0, 0, W, H);
        try { localStorage.setItem("aj-creature", m.id); } catch (e) {}
        if (announce) toast(m.id === "off" ? "Criatura escondida" : m.icon + " " + m.label + " ativado");
      }
      document.getElementById("creatureBtn").addEventListener("click", function () {
        modeIdx = (modeIdx + 1) % modes.length;
        applyMode(true);
      });
      applyMode(false);

      function loop(t) {
        k += (kTarget - k) * 0.05;
        var id = modes[modeIdx].id;
        if (id !== "off") {
          cx.clearRect(0, 0, W, H);
          var tg = target(t);
          if (id === "dragao") { updateDragon(tg); drawDragon(); }
          else { updateSpider(tg); drawSpider(); }
        }
        requestAnimationFrame(loop);
      }
      requestAnimationFrame(loop);

      // ---------- Confete (preto e branco) ----------
      var canvas = document.getElementById("confetti");
      var ctx = canvas.getContext("2d");
      var pieces = [];
      var running = false;
      function resize() {
        canvas.width = innerWidth * dpr;
        canvas.height = innerHeight * dpr;
        ctx.setTransform(dpr, 0, 0, dpr, 0, 0);
      }
      resize();
      window.addEventListener("resize", resize);

      function confetti() {
        var colors = ["#ffffff", "#d4d4d4", "#a3a3a3", "#737373"];
        for (var i = 0; i < 180; i++) {
          pieces.push({
            x: innerWidth / 2 + (Math.random() - 0.5) * 120,
            y: innerHeight * 0.35,
            vx: (Math.random() - 0.5) * 16,
            vy: -Math.random() * 14 - 4,
            w: 5 + Math.random() * 6,
            h: 7 + Math.random() * 8,
            r: Math.random() * Math.PI,
            vr: (Math.random() - 0.5) * 0.3,
            color: colors[(Math.random() * colors.length) | 0]
          });
        }
        if (!running) { running = true; requestAnimationFrame(tick); }
      }
      function tick() {
        ctx.clearRect(0, 0, innerWidth, innerHeight);
        pieces = pieces.filter(function (q) { return q.y < innerHeight + 40; });
        pieces.forEach(function (q) {
          q.vy += 0.35;
          q.vx *= 0.99;
          q.x += q.vx;
          q.y += q.vy;
          q.r += q.vr;
          ctx.save();
          ctx.translate(q.x, q.y);
          ctx.rotate(q.r);
          ctx.fillStyle = q.color;
          ctx.fillRect(-q.w / 2, -q.h / 2, q.w, q.h * Math.abs(Math.cos(q.r * 2)));
          ctx.restore();
        });
        if (pieces.length) requestAnimationFrame(tick);
        else { running = false; ctx.clearRect(0, 0, innerWidth, innerHeight); }
      }

      // ---------- Easter eggs: confete + criatura gigante ----------
      var furyTimer;
      function easterEgg() {
        confetti();
        document.body.classList.remove("shake");
        void document.body.offsetWidth;
        document.body.classList.add("shake");
        kTarget = baseScale() * 1.9;
        clearTimeout(furyTimer);
        furyTimer = setTimeout(function () { kTarget = baseScale(); }, 6000);
        toast("Você achou o easter egg! Modo fúria 🔥");
      }
      window.addEventListener("resize", function () { kTarget = baseScale(); });

      // 5 cliques no avatar
      var clicks = 0, clickTimer;
      document.getElementById("avatar").addEventListener("click", function () {
        clicks++;
        clearTimeout(clickTimer);
        clickTimer = setTimeout(function () { clicks = 0; }, 1500);
        if (clicks >= 5) { clicks = 0; easterEgg(); }
      });

      // Código Konami
      var konami = ["ArrowUp","ArrowUp","ArrowDown","ArrowDown","ArrowLeft","ArrowRight","ArrowLeft","ArrowRight","b","a"];
      var pos = 0;
      document.addEventListener("keydown", function (e) {
        if (e.key === "Escape") { closeQr(); return; }
        var key = e.key.length === 1 ? e.key.toLowerCase() : e.key;
        pos = key === konami[pos] ? pos + 1 : (key === konami[0] ? 1 : 0);
        if (pos === konami.length) { pos = 0; easterEgg(); }
      });
    })();
  </script>
</body>
</html>
