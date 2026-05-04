# Profile
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Natchapon Thiradechanun — AI Engineer</title>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Space+Mono:wght@400;700&family=Syne:wght@400;600;800&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --bg:        #0d0f14;
      --surface:   #13161e;
      --border:    #1e2230;
      --accent:    #00e5ff;
      --accent2:   #7b61ff;
      --accent3:   #ff6b6b;
      --gold:      #ffd700;
      --green:     #00ff88;
      --text:      #e0e6f0;
      --muted:     #6b7591;
      --mono:      'JetBrains Mono', monospace;
      --sans:      'Syne', sans-serif;
    }
 
    * { box-sizing: border-box; margin: 0; padding: 0; }
 
    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--mono);
      min-height: 100vh;
      position: relative;
      overflow-x: hidden;
    }
 
    /* Animated grid background */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
      background-size: 40px 40px;
      pointer-events: none;
      z-index: 0;
    }
 
    /* Glowing orbs */
    body::after {
      content: '';
      position: fixed;
      width: 600px;
      height: 600px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(0,229,255,0.06) 0%, transparent 70%);
      top: -200px;
      right: -200px;
      pointer-events: none;
      z-index: 0;
    }
 
    .container {
      max-width: 860px;
      margin: 0 auto;
      padding: 48px 24px 80px;
      position: relative;
      z-index: 1;
    }
 
    /* ── HEADER ── */
    .hero {
      border: 1px solid var(--border);
      border-radius: 16px;
      background: var(--surface);
      padding: 40px 40px 32px;
      margin-bottom: 24px;
      position: relative;
      overflow: hidden;
      animation: fadeUp 0.7s ease both;
    }
 
    .hero::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 2px;
      background: linear-gradient(90deg, var(--accent), var(--accent2), var(--accent));
      background-size: 200% 100%;
      animation: shimmer 3s linear infinite;
    }
 
    @keyframes shimmer {
      0% { background-position: -200% 0; }
      100% { background-position: 200% 0; }
    }
 
    .hero-inner {
      display: flex;
      align-items: flex-start;
      gap: 32px;
      flex-wrap: wrap;
    }
 
    .avatar-wrap {
      flex-shrink: 0;
    }
 
    .avatar {
      width: 96px;
      height: 96px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--accent2), var(--accent));
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: var(--sans);
      font-size: 36px;
      font-weight: 800;
      color: #fff;
      position: relative;
      box-shadow: 0 0 40px rgba(0,229,255,0.2);
    }
 
    .avatar::after {
      content: '';
      position: absolute;
      inset: -4px;
      border-radius: 50%;
      border: 2px solid transparent;
      background: linear-gradient(135deg, var(--accent), var(--accent2)) border-box;
      -webkit-mask: linear-gradient(#fff 0 0) padding-box, linear-gradient(#fff 0 0);
      -webkit-mask-composite: destination-out;
      mask-composite: exclude;
      animation: spin 6s linear infinite;
    }
 
    @keyframes spin {
      to { transform: rotate(360deg); }
    }
 
    .hero-info {
      flex: 1;
      min-width: 240px;
    }
 
    .name {
      font-family: var(--sans);
      font-size: 2rem;
      font-weight: 800;
      letter-spacing: -0.5px;
      background: linear-gradient(135deg, #fff 0%, var(--accent) 60%, var(--accent2) 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      line-height: 1.1;
      margin-bottom: 4px;
    }
 
    .handle {
      color: var(--muted);
      font-size: 0.8rem;
      margin-bottom: 14px;
      letter-spacing: 0.5px;
    }
 
    .tagline {
      font-family: var(--mono);
      font-size: 0.78rem;
      color: var(--accent);
      background: rgba(0,229,255,0.07);
      border: 1px solid rgba(0,229,255,0.15);
      border-radius: 6px;
      padding: 6px 12px;
      display: inline-block;
      margin-bottom: 18px;
      line-height: 1.5;
    }
 
    .tagline::before { content: '> '; color: var(--green); }
 
    .contact-row {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }
 
    .chip {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 4px 12px;
      font-size: 0.72rem;
      color: var(--text);
      text-decoration: none;
      transition: all 0.2s;
    }
 
    .chip:hover {
      border-color: var(--accent);
      color: var(--accent);
      background: rgba(0,229,255,0.06);
    }
 
    .chip-icon { font-size: 0.9rem; }
 
    /* ── SECTIONS ── */
    section {
      border: 1px solid var(--border);
      border-radius: 16px;
      background: var(--surface);
      padding: 32px;
      margin-bottom: 20px;
      animation: fadeUp 0.7s ease both;
    }
 
    section:nth-child(2)  { animation-delay: 0.1s; }
    section:nth-child(3)  { animation-delay: 0.15s; }
    section:nth-child(4)  { animation-delay: 0.2s; }
    section:nth-child(5)  { animation-delay: 0.25s; }
    section:nth-child(6)  { animation-delay: 0.3s; }
    section:nth-child(7)  { animation-delay: 0.35s; }
 
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(16px); }
      to   { opacity: 1; transform: translateY(0); }
    }
 
    .sec-title {
      font-family: var(--sans);
      font-size: 1rem;
      font-weight: 700;
      color: #fff;
      letter-spacing: 0.3px;
      margin-bottom: 20px;
      display: flex;
      align-items: center;
      gap: 10px;
    }
 
    .sec-title span { font-size: 1.1rem; }
 
    .sec-title::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
      margin-left: 8px;
    }
 
    /* ── ABOUT ── */
    .about-text {
      font-size: 0.82rem;
      line-height: 1.85;
      color: #b0bcd4;
    }
 
    .about-text strong { color: var(--accent); font-weight: 500; }
 
    .goal-box {
      margin-top: 16px;
      border-left: 3px solid var(--accent2);
      padding: 12px 16px;
      background: rgba(123,97,255,0.06);
      border-radius: 0 8px 8px 0;
      font-size: 0.8rem;
      color: #c0cce0;
      font-style: italic;
    }
 
    /* ── EXPERIENCE ── */
    .exp-item {
      padding: 20px;
      border: 1px solid var(--border);
      border-radius: 12px;
      margin-bottom: 14px;
      background: rgba(255,255,255,0.015);
      transition: border-color 0.2s;
      position: relative;
    }
 
    .exp-item:hover { border-color: rgba(0,229,255,0.3); }
    .exp-item:last-child { margin-bottom: 0; }
 
    .exp-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 8px;
    }
 
    .exp-title {
      font-family: var(--sans);
      font-size: 0.92rem;
      font-weight: 700;
      color: #fff;
    }
 
    .exp-role {
      font-size: 0.72rem;
      color: var(--accent);
      background: rgba(0,229,255,0.08);
      border: 1px solid rgba(0,229,255,0.15);
      border-radius: 4px;
      padding: 2px 8px;
    }
 
    .exp-date {
      font-size: 0.7rem;
      color: var(--muted);
      font-family: var(--mono);
    }
 
    .exp-bullets {
      list-style: none;
      margin-top: 10px;
    }
 
    .exp-bullets li {
      font-size: 0.78rem;
      color: #9aaabe;
      padding: 3px 0 3px 18px;
      position: relative;
      line-height: 1.6;
    }
 
    .exp-bullets li::before {
      content: '▸';
      position: absolute;
      left: 0;
      color: var(--accent2);
    }
 
    /* ── PROJECTS ── */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
      gap: 14px;
    }
 
    .project-card {
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 20px;
      background: rgba(255,255,255,0.02);
      transition: all 0.25s;
      position: relative;
      overflow: hidden;
    }
 
    .project-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--accent2), transparent);
      opacity: 0;
      transition: opacity 0.25s;
    }
 
    .project-card:hover { border-color: rgba(123,97,255,0.4); transform: translateY(-2px); }
    .project-card:hover::before { opacity: 1; }
 
    .proj-name {
      font-family: var(--sans);
      font-size: 0.88rem;
      font-weight: 700;
      color: #fff;
      margin-bottom: 8px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
 
    .proj-name a {
      color: var(--accent);
      text-decoration: none;
      font-size: 0.75rem;
      font-weight: 400;
      font-family: var(--mono);
    }
 
    .proj-name a:hover { text-decoration: underline; }
 
    .proj-desc {
      font-size: 0.76rem;
      color: #8a98b4;
      line-height: 1.65;
    }
 
    .proj-tag {
      display: inline-block;
      margin-top: 10px;
      font-size: 0.65rem;
      color: var(--accent2);
      background: rgba(123,97,255,0.1);
      border: 1px solid rgba(123,97,255,0.2);
      border-radius: 4px;
      padding: 2px 7px;
      margin-right: 4px;
    }
 
    /* ── SKILLS ── */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
      gap: 10px;
    }
 
    .skill-badge {
      display: flex;
      align-items: center;
      gap: 10px;
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 10px 14px;
      font-size: 0.76rem;
      color: var(--text);
      background: rgba(255,255,255,0.02);
      transition: all 0.2s;
    }
 
    .skill-badge:hover {
      border-color: var(--accent);
      color: var(--accent);
      background: rgba(0,229,255,0.05);
    }
 
    .skill-icon { font-size: 1.1rem; }
 
    /* ── EDUCATION ── */
    .edu-item {
      display: flex;
      align-items: center;
      gap: 20px;
      padding: 20px;
      border: 1px solid var(--border);
      border-radius: 12px;
      background: rgba(255,255,255,0.015);
    }
 
    .edu-logo {
      width: 52px;
      height: 52px;
      border-radius: 10px;
      background: linear-gradient(135deg, #1a2040, #0d1535);
      border: 1px solid var(--border);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.4rem;
      flex-shrink: 0;
    }
 
    .edu-name {
      font-family: var(--sans);
      font-size: 0.9rem;
      font-weight: 700;
      color: #fff;
    }
 
    .edu-degree {
      font-size: 0.76rem;
      color: var(--muted);
      margin-top: 3px;
    }
 
    .edu-year {
      margin-left: auto;
      font-size: 0.7rem;
      color: var(--accent);
      font-family: var(--mono);
      flex-shrink: 0;
    }
 
    /* ── CERTIFICATES / HACKATHONS ── */
    .hack-list {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }
 
    .hack-group {
      border: 1px solid var(--border);
      border-radius: 12px;
      overflow: hidden;
    }
 
    .hack-group-title {
      background: rgba(255,255,255,0.03);
      padding: 10px 16px;
      font-size: 0.78rem;
      font-weight: 700;
      color: var(--gold);
      display: flex;
      align-items: center;
      gap: 8px;
      border-bottom: 1px solid var(--border);
      font-family: var(--sans);
    }
 
    .hack-items {
      padding: 10px 16px;
      display: flex;
      flex-direction: column;
      gap: 6px;
    }
 
    .hack-item {
      font-size: 0.75rem;
      color: #8a9ab8;
      display: flex;
      align-items: flex-start;
      gap: 8px;
      line-height: 1.5;
    }
 
    .hack-item::before {
      content: '◈';
      color: var(--accent2);
      flex-shrink: 0;
      margin-top: 1px;
    }
 
    .hack-item.winner::before { content: '🏆'; }
    .hack-item.silver::before  { content: '🥈'; }
    .hack-item.placed::before  { content: '🎖️'; }
 
    /* ── STATS ROW ── */
    .stats-row {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
      gap: 12px;
      margin-bottom: 20px;
    }
 
    .stat-box {
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 16px;
      text-align: center;
      background: rgba(255,255,255,0.02);
    }
 
    .stat-num {
      font-family: var(--sans);
      font-size: 1.8rem;
      font-weight: 800;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      line-height: 1;
    }
 
    .stat-label {
      font-size: 0.65rem;
      color: var(--muted);
      margin-top: 4px;
      text-transform: uppercase;
      letter-spacing: 0.8px;
    }
 
    /* ── GITHUB STATS BADGES (external images) ── */
    .github-stats {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      justify-content: center;
    }
 
    .github-stats img {
      border-radius: 8px;
      max-width: 100%;
    }
 
    /* ── SOCIAL BADGES ── */
    .social-row {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }
 
    .social-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 16px;
      border-radius: 8px;
      font-size: 0.75rem;
      font-weight: 600;
      text-decoration: none;
      transition: all 0.2s;
      border: 1px solid transparent;
    }
 
    .social-badge:hover { transform: translateY(-2px); filter: brightness(1.15); }
 
    .badge-github   { background: #21262d; color: #e6edf3; border-color: #30363d; }
    .badge-linkedin { background: #0a66c2; color: #fff; }
    .badge-email    { background: #1a1a2e; color: var(--accent); border-color: var(--accent); }
    .badge-instagram{ background: linear-gradient(135deg,#833ab4,#fd1d1d,#fcb045); color:#fff; }
 
    /* ── TECH STACK ── */
    .tech-row {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }
 
    .tech-pill {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 5px 12px;
      border-radius: 20px;
      font-size: 0.72rem;
      border: 1px solid rgba(255,255,255,0.08);
      background: rgba(255,255,255,0.03);
      color: #b0c0d8;
      transition: all 0.2s;
    }
 
    .tech-pill:hover {
      border-color: var(--accent);
      color: var(--accent);
      background: rgba(0,229,255,0.05);
    }
 
    /* ── FOOTER ── */
    .footer {
      text-align: center;
      font-size: 0.7rem;
      color: var(--muted);
      margin-top: 40px;
      padding-top: 24px;
      border-top: 1px solid var(--border);
    }
 
    .footer span { color: var(--accent); }
 
    /* scrollbar */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: var(--bg); }
    ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 3px; }
 
    /* responsive */
    @media (max-width: 600px) {
      .hero { padding: 24px 20px; }
      section { padding: 22px 18px; }
      .name { font-size: 1.5rem; }
      .projects-grid { grid-template-columns: 1fr; }
      .skills-grid { grid-template-columns: repeat(2, 1fr); }
    }
  </style>
</head>
<body>
<div class="container">
 
  <!-- ══════ HERO ══════ -->
  <div class="hero">
    <div class="hero-inner">
      <div class="avatar-wrap">
        <div class="avatar">NT</div>
      </div>
      <div class="hero-info">
        <div class="name">Natchapon Thiradechanun</div>
        <div class="handle">@nathirad · aie_noctenn_kim</div>
        <div class="tagline">
          Dedicated to engineering end-to-end AI solutions,<br>
          bridging the gap between cutting-edge research and real-world social impact.
        </div>
        <div class="contact-row">
          <a class="chip" href="tel:0819356154">
            <span class="chip-icon">📞</span> 081-935-6154
          </a>
          <a class="chip" href="mailto:codingaiaie@gmail.com">
            <span class="chip-icon">✉️</span> codingaiaie@gmail.com
          </a>
          <a class="chip" href="https://linkedin.com/in/natchapon-thiradechanun" target="_blank">
            <span class="chip-icon">🔗</span> LinkedIn
          </a>
          <a class="chip" href="https://github.com/nathirad" target="_blank">
            <span class="chip-icon">🐙</span> GitHub
          </a>
          <span class="chip">
            <span class="chip-icon">📍</span> Bangkok, Thailand
          </span>
        </div>
      </div>
    </div>
  </div>
 
  <!-- ══════ ABOUT ══════ -->
  <section>
    <div class="sec-title"><span>💫</span> About Me</div>
    <div class="about-text">
      Hi! I'm <strong>Natchapon</strong> — a first-year (incoming second-year) 
      <strong>Computer Science</strong> student at 
      <strong>King Mongkut's Institute of Technology Ladkrabang (KMITL)</strong>, 
      driven by a deep passion for <strong>Artificial Intelligence</strong>, innovation, and business.<br><br>
      I participated in the <strong>Super AI Engineer Season 6</strong> program, 
      completing three weeks of intensive training covering Data, AI Models, and LLM &amp; RAG. 
      I also took part in the <strong>5 Domains Hackathon</strong>, applying technical skills 
      to solve diverse real-world problems and accelerating my progress toward Level 2.
    </div>
    <div class="goal-box">
      🎯 Career Goal: Become an AI Engineer — engineering end-to-end AI solutions that 
      bridge cutting-edge research and real-world social impact.
    </div>
  </section>
 
  <!-- ══════ QUICK STATS ══════ -->
  <section>
    <div class="sec-title"><span>📊</span> At a Glance</div>
    <div class="stats-row">
      <div class="stat-box">
        <div class="stat-num">10+</div>
        <div class="stat-label">Hackathons</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">2</div>
        <div class="stat-label">Top Placements</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">6+</div>
        <div class="stat-label">AI Domains</div>
      </div>
      <div class="stat-box">
        <div class="stat-num">10</div>
        <div class="stat-label">Weeks TA</div>
      </div>
    </div>
  </section>
 
  <!-- ══════ EXPERIENCE ══════ -->
  <section>
    <div class="sec-title"><span>💼</span> Experience</div>
 
    <div class="exp-item">
      <div class="exp-header">
        <div>
          <div class="exp-title">Super AI Engineer Season 6</div>
          <div class="exp-role">Participant</div>
        </div>
        <div class="exp-date">Mar 2026 – Apr 2026</div>
      </div>
      <ul class="exp-bullets">
        <li>Completed three weeks of intensive training in Data, AI Models, and LLM &amp; RAG.</li>
        <li>Participated in the 5 Domains Hackathon, applying technical skills to solve diverse real-world problems and accelerate progress toward Level 2.</li>
      </ul>
    </div>
 
    <div class="exp-item">
      <div class="exp-header">
        <div>
          <div class="exp-title">โครงการหนูน้อยวิศวกรอัจฉริยะสร้างได้ตั้งแต่เด็ก</div>
          <div class="exp-role">Teaching Assistant Intern</div>
        </div>
        <div class="exp-date">Nov 2023 – Feb 2024</div>
      </div>
      <ul class="exp-bullets">
        <li>Served 10 weeks as a Teaching Assistant, guiding students in building robots using 3D-printed bodies, hardware components, Python, and C+ Programming.</li>
        <li>Instructed participants on integrating AI technologies — Computer Vision and Machine Learning — to enhance robotic capabilities.</li>
      </ul>
    </div>
  </section>
 
  <!-- ══════ PROJECTS ══════ -->
  <section>
    <div class="sec-title"><span>🚀</span> Projects</div>
    <div class="projects-grid">
 
      <div class="project-card">
        <div class="proj-name">
          Mood to Menu
          <a href="https://prompt-guardian-pal.lovable.app" target="_blank">↗ live demo</a>
        </div>
        <div class="proj-desc">
          An AI-powered app that transforms emotional vents into food suggestions 
          through an orchestrated workflow and prompt filtering. Built with 
          Gemini 2.5 Flash-Lite and Vibe Coding.
        </div>
        <div>
          <span class="proj-tag">Gemini 2.5</span>
          <span class="proj-tag">Vibe Coding</span>
          <span class="proj-tag">Prompt Engineering</span>
          <span class="proj-tag">LLM</span>
        </div>
      </div>
 
      <div class="project-card">
        <div class="proj-name">Portfolio Website — 42 Bangkok</div>
        <div class="proj-desc">
          A portfolio website created during the 42 Bangkok camp as a final project, 
          showcasing work and technical achievements from the program.
        </div>
        <div>
          <span class="proj-tag">HTML/CSS</span>
          <span class="proj-tag">Web Dev</span>
          <span class="proj-tag">42 Bangkok</span>
        </div>
      </div>
 
    </div>
  </section>
 
  <!-- ══════ SKILLS ══════ -->
  <section>
    <div class="sec-title"><span>🧠</span> Tech Stack &amp; Skills</div>
    <div class="skills-grid">
      <div class="skill-badge"><span class="skill-icon">🐍</span> Python</div>
      <div class="skill-badge"><span class="skill-icon">🤖</span> Machine Learning</div>
      <div class="skill-badge"><span class="skill-icon">🔍</span> RAG</div>
      <div class="skill-badge"><span class="skill-icon">🗣️</span> Large Language Models</div>
      <div class="skill-badge"><span class="skill-icon">👁️</span> Image Processing</div>
      <div class="skill-badge"><span class="skill-icon">🧹</span> Data Preprocessing</div>
      <div class="skill-badge"><span class="skill-icon">💻</span> C Programming</div>
      <div class="skill-badge"><span class="skill-icon">🤖</span> Computer Vision</div>
      <div class="skill-badge"><span class="skill-icon">⚙️</span> Prompt Engineering</div>
      <div class="skill-badge"><span class="skill-icon">🌐</span> Web Development</div>
    </div>
    <br/>
    <div class="tech-row">
      <span class="tech-pill">🟦 Python</span>
      <span class="tech-pill">🟨 Gemini API</span>
      <span class="tech-pill">🟩 LangChain</span>
      <span class="tech-pill">⬛ OpenCV</span>
      <span class="tech-pill">🟦 scikit-learn</span>
      <span class="tech-pill">🟧 PyTorch</span>
      <span class="tech-pill">⬜ HTML/CSS</span>
      <span class="tech-pill">🟨 JavaScript</span>
    </div>
  </section>
 
  <!-- ══════ EDUCATION ══════ -->
  <section>
    <div class="sec-title"><span>🎓</span> Education</div>
    <div class="edu-item">
      <div class="edu-logo">🏫</div>
      <div>
        <div class="edu-name">King Mongkut's Institute of Technology Ladkrabang (KMITL)</div>
        <div class="edu-degree">Bachelor of Science — Computer Science</div>
      </div>
      <div class="edu-year">2025 – 2028</div>
    </div>
  </section>
 
  <!-- ══════ CERTIFICATES & HACKATHONS ══════ -->
  <section>
    <div class="sec-title"><span>🏆</span> Certificates &amp; Competitions</div>
    <div class="hack-list">
 
      <div class="hack-group">
        <div class="hack-group-title">⚡ Super AI Engineer Season 6 — Mini Hackathon (3 Weeks)</div>
        <div class="hack-items">
          <div class="hack-item">AI Online Hackathon (Practice) — Open Thai Data: Data Storytelling</div>
          <div class="hack-item">AI Online Hackathon (Practice) — OCR ผลเอกสารเลือกตั้ง สส. 2569</div>
          <div class="hack-item">AI Online Hackathon (Practice) — Fahmai RAG Challenge</div>
        </div>
      </div>
 
      <div class="hack-group">
        <div class="hack-group-title">⚡ Super AI Engineer Season 6 — 5 Domains Mini Hackathon</div>
        <div class="hack-items">
          <div class="hack-item">AI Online Hackathon (Practice) — Word Segmentation (NLP)</div>
          <div class="hack-item">AI Online Hackathon (Practice) — Heart Disease Prediction (ML)</div>
          <div class="hack-item">AI Online Hackathon (Practice) — Sleep Stage Classification (ML)</div>
          <div class="hack-item">AI Online Hackathon (Practice) — House Recognition (Image Processing)</div>
        </div>
      </div>
 
      <div class="hack-group">
        <div class="hack-group-title">🚀 External Competitions &amp; Programs</div>
        <div class="hack-items">
          <div class="hack-item placed">The 4th Kibo Robot Programming Challenge — 19th Place</div>
          <div class="hack-item placed">CARC Drone Competition 2025 — 4th Place</div>
          <div class="hack-item">Gen AI Hackathon by MITR PHOL GROUP — 38th Kaggle Place · Technical Interview</div>
          <div class="hack-item">KBTG x Samsung Hackathon — Participated · Project Proposal</div>
          <div class="hack-item">Cyber Warrior Hackathon KMUTT — Participated · Project Proposal</div>
          <div class="hack-item">AI Thailand Hackathon CHULA — Participated</div>
          <div class="hack-item">AMI Hackthon KMITL #3 — Participated</div>
          <div class="hack-item">Bangmod Hackathon — Participated</div>
          <div class="hack-item">Cira Core Camp #3 2024 — Participated</div>
          <div class="hack-item">การสร้าง LLM แบบ Continued Pretraining และ Finetuning — NECTEC</div>
          <div class="hack-item">AI Engineering Skills &amp; Hackathon for Employment 2026 — AIAT x Microsoft (In Progress)</div>
        </div>
      </div>
 
    </div>
  </section>
 
  <!-- ══════ GITHUB STATS ══════ -->
  <section>
    <div class="sec-title"><span>📈</span> GitHub Stats</div>
    <div class="github-stats">
      <img
        src="https://github-readme-stats.vercel.app/api?username=nathirad&theme=dark&hide_border=false&include_all_commits=false&count_private=false"
        alt="GitHub Stats"
        onerror="this.style.display='none'"
      />
      <img
        src="https://github-readme-streak-stats.herokuapp.com/?user=nathirad&theme=dark&hide_border=false"
        alt="GitHub Streak"
        onerror="this.style.display='none'"
      />
      <img
        src="https://github-readme-stats.vercel.app/api/top-langs/?username=nathirad&theme=dark&hide_border=false&include_all_commits=false&count_private=false&layout=compact"
        alt="Top Languages"
        onerror="this.style.display='none'"
      />
    </div>
  </section>
 
  <!-- ══════ SOCIALS ══════ -->
  <section>
    <div class="sec-title"><span>🌐</span> Connect With Me</div>
    <div class="social-row">
      <a class="social-badge badge-github" href="https://github.com/nathirad" target="_blank">
        🐙 GitHub / nathirad
      </a>
      <a class="social-badge badge-linkedin" href="https://linkedin.com/in/natchapon-thiradechanun" target="_blank">
        🔗 LinkedIn
      </a>
      <a class="social-badge badge-email" href="mailto:codingaiaie@gmail.com">
        ✉️ codingaiaie@gmail.com
      </a>
      <a class="social-badge badge-instagram" href="https://instagram.com/aie_noctenn_kim" target="_blank">
        📸 @aie_noctenn_kim
      </a>
    </div>
  </section>
 
  <div class="footer">
    <p>Built with ♥ · <span>Natchapon Thiradechanun</span> · KMITL Computer Science · 2025–2028</p>
    <p style="margin-top:6px">🎯 Aspiring AI Engineer · Super AI Engineer SS6 Participant · Bangkok, Thailand</p>
  </div>
 
</div>
</body>
</html>
