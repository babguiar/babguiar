<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Bárbara Guedes Aguiar | AI & Data Science Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@400;600;700;800&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg-dark: #0D1220;
      --card-bg: #151C2F;
      --card-border: rgba(244, 114, 182, 0.22);
      --pink-neon: #F43F8E;
      --pink-soft: #F9A8D4;
      --purple-neon: #9333EA;
      --text-main: #F8FAFC;
      --text-muted: #94A3B8;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    body {
      background-color: var(--bg-dark);
      /* Fundo quadriculado sutil + brilhos rosa e roxo */
      background-image:
        radial-gradient(circle at 80% 12%, rgba(244, 63, 142, 0.22) 0%, transparent 38%),
        radial-gradient(circle at 50% 42%, rgba(236, 72, 153, 0.16) 0%, transparent 35%),
        radial-gradient(circle at 18% 82%, rgba(147, 51, 234, 0.22) 0%, transparent 40%),
        linear-gradient(rgba(244, 114, 182, 0.05) 1px, transparent 1px),
        linear-gradient(90deg, rgba(244, 114, 182, 0.05) 1px, transparent 1px);
      background-size: 100% 100%, 100% 100%, 100% 100%, 32px 32px, 32px 32px;
      color: var(--text-main);
      font-family: 'Fira Code', monospace;
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* NAVBAR SUPERIOR ARREDONDADA ROSA CLARO (IGUAL À REFERÊNCIA) */
    .navbar-wrapper {
      display: flex;
      justify-content: center;
      padding: 24px 20px 10px;
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .navbar {
      background: #FBCFE8;
      color: #1E1B4B;
      width: 100%;
      max-width: 820px;
      border-radius: 16px;
      padding: 10px 24px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      box-shadow: 0 8px 30px rgba(244, 63, 142, 0.25);
    }

    .nav-logo {
      font-family: 'Plus Jakarta Sans', sans-serif;
      font-weight: 800;
      font-size: 1.1rem;
      letter-spacing: 1px;
      color: #111827;
    }

    .nav-links {
      display: flex;
      gap: 18px;
      list-style: none;
      font-size: 0.78rem;
      font-weight: 600;
    }

    .nav-links a {
      text-decoration: none;
      color: #374151;
      transition: color 0.2s;
    }

    .nav-links a:hover, .nav-links a.active {
      color: #DB2777;
      border-bottom: 2px solid #DB2777;
      padding-bottom: 2px;
    }

    .btn-hire {
      background: linear-gradient(90deg, #EC4899, #DB2777);
      color: #fff;
      padding: 7px 18px;
      border-radius: 10px;
      font-size: 0.78rem;
      font-weight: 700;
      text-decoration: none;
      box-shadow: 0 4px 14px rgba(219, 39, 119, 0.45);
    }

    /* CONTAINER PRINCIPAL */
    .container {
      max-width: 1050px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* HERO SECTION */
    .hero {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      align-items: center;
      gap: 40px;
      padding: 60px 0 50px;
    }

    .hero-tag {
      font-size: 0.75rem;
      letter-spacing: 2.5px;
      color: var(--pink-soft);
      text-transform: uppercase;
      margin-bottom: 10px;
    }

    .hero h1 {
      font-family: 'Plus Jakarta Sans', sans-serif;
      font-size: 2.7rem;
      font-weight: 800;
      line-height: 1.2;
    }

    .hero h2 {
      font-size: 1.65rem;
      color: var(--pink-neon);
      margin-bottom: 18px;
      font-weight: 700;
    }

    .hero p {
      color: var(--text-muted);
      font-size: 0.86rem;
      max-width: 490px;
      margin-bottom: 28px;
    }

    .hero-actions {
      display: flex;
      align-items: center;
      gap: 14px;
    }

    .btn-primary {
      background: linear-gradient(90deg, #F43F8E, #C026D3);
      color: white;
      padding: 11px 22px;
      border-radius: 999px;
      font-size: 0.82rem;
      font-weight: 700;
      text-decoration: none;
      box-shadow: 0 0 22px rgba(244, 63, 142, 0.55);
      transition: transform 0.2s;
    }

    .btn-primary:hover {
      transform: translateY(-2px);
    }

    .social-circle {
      width: 36px;
      height: 36px;
      border-radius: 50%;
      background: rgba(244, 114, 182, 0.15);
      border: 1px solid rgba(244, 114, 182, 0.4);
      display: inline-flex;
      align-items: center;
      justify-content: center;
      color: #FBCFE8;
      text-decoration: none;
      font-size: 0.8rem;
      font-weight: bold;
    }

    /* SÍMBOLO FLOR DE CEREJEIRA NEON NO HERO */
    .hero-visual {
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
    }

    .sakura-orb {
      width: 280px;
      height: 280px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(244,63,142,0.32) 0%, rgba(147,51,234,0.18) 55%, transparent 75%);
      display: flex;
      align-items: center;
      justify-content: center;
      filter: drop-shadow(0 0 28px rgba(244, 63, 142, 0.65));
    }

    /* FAIXA HORIZONTAL DE FERRAMENTAS (IGUAL À BARRA DEGRADÊ DA IMAGEM) */
    .tech-ribbon {
      background: linear-gradient(90deg, #1E1B4B 0%, #BE185D 35%, #DB2777 65%, #3B0764 100%);
      padding: 18px 24px;
      margin: 20px 0 70px;
      border-top: 1px solid rgba(251, 207, 232, 0.35);
      border-bottom: 1px solid rgba(251, 207, 232, 0.35);
      box-shadow: 0 0 35px rgba(219, 39, 119, 0.35);
    }

    .tech-ribbon-inner {
      max-width: 1050px;
      margin: 0 auto;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-around;
      align-items: center;
      gap: 20px;
    }

    .tech-item {
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 0.88rem;
      font-weight: 600;
      color: #FDF2F8;
    }

    .tech-item img {
      width: 26px;
      height: 26px;
    }

    /* ABOUT ME (3 COLUNAS COM FLOR CENTRAL NEON) */
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      align-items: center;
      gap: 32px;
      padding: 30px 0 80px;
    }

    .section-eyebrow {
      font-size: 0.72rem;
      letter-spacing: 2px;
      color: var(--pink-soft);
      text-transform: uppercase;
    }

    .section-title {
      font-family: 'Plus Jakarta Sans', sans-serif;
      font-size: 2rem;
      font-weight: 800;
      margin: 6px 0 16px;
    }

    .section-title span {
      color: var(--pink-neon);
    }

    .stats-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 18px;
      margin-top: 24px;
    }

    .stat-box h4 {
      font-family: 'Plus Jakarta Sans', sans-serif;
      font-size: 1.5rem;
      color: var(--pink-neon);
      font-weight: 800;
    }

    .stat-box span {
      font-size: 0.75rem;
      color: var(--text-muted);
    }

    .glass-card {
      background: rgba(21, 28, 47, 0.85);
      border: 1px solid var(--card-border);
      border-radius: 14px;
      padding: 20px;
      margin-bottom: 18px;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
    }

    .glass-card h4 {
      color: var(--pink-soft);
      font-size: 0.95rem;
      margin-bottom: 8px;
    }

    .glass-card p {
      color: var(--text-muted);
      font-size: 0.8rem;
    }

    /* CERTIFICATES & PROJECTS (3 CARDS LADO A LADO) */
    .center-header {
      text-align: center;
      margin-bottom: 40px;
    }

    .cards-3 {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 22px;
      margin-bottom: 85px;
    }

    .cert-card {
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      border-radius: 16px;
      padding: 24px;
      transition: border-color 0.25s, transform 0.25s;
    }

    .cert-card:hover {
      border-color: var(--pink-neon);
      transform: translateY(-4px);
    }

    .cert-top {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      gap: 10px;
      margin-bottom: 8px;
    }

    .cert-top h4 {
      font-family: 'Plus Jakarta Sans', sans-serif;
      font-size: 1.05rem;
      font-weight: 700;
    }

    .cert-year {
      color: var(--pink-neon);
      font-weight: 700;
      font-size: 0.85rem;
    }

    .cert-org {
      font-size: 0.78rem;
      color: var(--text-muted);
      margin-bottom: 16px;
    }

    .pill-group {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 16px;
    }

    .pill {
      background: rgba(244, 63, 142, 0.14);
      color: var(--pink-soft);
      border: 1px solid rgba(244, 63, 142, 0.3);
      padding: 3px 10px;
      border-radius: 999px;
      font-size: 0.7rem;
    }

    /* EDUCATION SECTION */
    .edu-grid {
      display: grid;
      grid-template-columns: 0.8fr 1.2fr;
      align-items: center;
      gap: 40px;
      padding-bottom: 80px;
    }

    .edu-item {
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      border-radius: 14px;
      padding: 18px 22px;
      margin-bottom: 14px;
    }

    .edu-item h4 {
      font-family: 'Plus Jakarta Sans', sans-serif;
      font-size: 1rem;
      margin-bottom: 4px;
    }

    .edu-item p {
      font-size: 0.8rem;
      color: var(--pink-soft);
    }

    .edu-item span {
      font-size: 0.75rem;
      color: var(--text-muted);
    }

    @media (max-width: 860px) {
      .hero, .about-grid, .cards-3, .edu-grid {
        grid-template-columns: 1fr;
      }
      .nav-links { display: none; }
    }
  </style>
</head>
<body>

  <!-- BARRA DE NAVEGAÇÃO SUPERIOR -->
  <div class="navbar-wrapper">
    <nav class="navbar">
      <div class="nav-logo">BÁRBARA</div>
      <ul class="nav-links">
        <li><a href="#home" class="active">HOME</a></li>
        <li><a href="#about">ABOUT</a></li>
        <li><a href="#projects">PROJECTS</a></li>
        <li><a href="#skills">SKILLS</a></li>
        <li><a href="#education">EDUCATION</a></li>
      </ul>
      <a href="#education" class="btn-hire">Portfolio</a>
    </nav>
  </div>

  <!-- HERO SECTION -->
  <section id="home" class="container hero">
    <div>
      <div class="hero-tag">BÁRBARA GUEDES AGUIAR</div>
      <h1>🌸 Hi, I'm BÁRBARA 🌸</h1>
      <h2>AI &amp; Data Scientist|</h2>
      <p>
        Engenheira de Produção e pesquisadora em Inteligência Artificial Aplicada à Engenharia. Especialista em Ciência de Dados, séries temporais multivariadas, IA explicável (XAI) e modelagem geoespacial.
      </p>
      <div class="hero-actions">
        <a href="#projects" class="btn-primary">🌸 Ver Experimentos</a>
        <a href="https://github.com" target="_blank" class="social-circle">GH</a>
        <a href="https://linkedin.com" target="_blank" class="social-circle">IN</a>
      </div>
    </div>

    <div class="hero-visual">
      <div class="sakura-orb">
        <!-- FLOR DE CEREJEIRA NEON SVG -->
        <svg width="210" height="210" viewBox="0 0 200 200" fill="none" xmlns="http://www.w3.org/2000/svg">
          <g transform="translate(100,100)">
            <path d="M0,-14 C22,-68 54,-68 24,-10 C8,-2 -8,-2 0,-14 Z" fill="#F43F8E" stroke="#FBCFE8" stroke-width="1.5" transform="rotate(0)"/>
            <path d="M0,-14 C22,-68 54,-68 24,-10 C8,-2 -8,-2 0,-14 Z" fill="#EC4899" stroke="#FBCFE8" stroke-width="1.5" transform="rotate(72)"/>
            <path d="M0,-14 C22,-68 54,-68 24,-10 C8,-2 -8,-2 0,-14 Z" fill="#DB2777" stroke="#FBCFE8" stroke-width="1.5" transform="rotate(144)"/>
            <path d="M0,-14 C22,-68 54,-68 24,-10 C8,-2 -8,-2 0,-14 Z" fill="#C026D3" stroke="#FBCFE8" stroke-width="1.5" transform="rotate(216)"/>
            <path d="M0,-14 C22,-68 54,-68 24,-10 C8,-2 -8,-2 0,-14 Z" fill="#E879F9" stroke="#FBCFE8" stroke-width="1.5" transform="rotate(288)"/>
            <circle cx="0" cy="0" r="11" fill="#FDF2F8"/>
            <circle cx="0" cy="0" r="5" fill="#9333EA"/>
          </g>
        </svg>
      </div>
    </div>
  </section>

  <!-- FAIXA HORIZONTAL NEON COM AS LOGOS DAS FERRAMENTAS -->
  <div id="skills" class="tech-ribbon">
    <div class="tech-ribbon-inner">
      <div class="tech-item"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python"> Python</div>
      <div class="tech-item"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/r/r-original.svg" alt="R"> RStudio</div>
      <div class="tech-item"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="SQL"> SQL</div>
      <div class="tech-item"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/scikitlearn/scikitlearn-original.svg" alt="Scikit-learn"> Scikit-Learn</div>
      <div class="tech-item"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tensorflow/tensorflow-original.svg" alt="TensorFlow"> TensorFlow</div>
      <div class="tech-item"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git"> Git &amp; MLflow</div>
    </div>
  </div>

  <!-- ABOUT ME -->
  <section id="about" class="container about-grid">
    <div>
      <div class="section-eyebrow">GET TO KNOW ME</div>
      <h2 class="section-title">🌸 About <span>Me</span> 🌸</h2>
      <p style="font-size: 0.83rem; color: var(--text-muted);">
        Unindo Engenharia de Produção, Ciência de Dados e Inteligência Artificial para transformar dados complexos em decisões estratégicas e modelos explicáveis.
      </p>
      <div class="stats-grid">
        <div class="stat-box">
          <h4>MSc</h4>
          <span>Applied AI (UFVJM)</span>
        </div>
        <div class="stat-box">
          <h4>MBA</h4>
