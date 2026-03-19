<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Thisara Chathuranga</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:ital,wght@0,400;0,500;1,400&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0d0d0f;
    --surface: #141417;
    --surface2: #1b1b20;
    --border: #2a2a30;
    --text: #e8e8ec;
    --muted: #6b6b78;
    --accent: #6ee7b7;
    --accent2: #818cf8;
    --accent3: #f472b6;
    --accent-glow: rgba(110, 231, 183, 0.12);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 2rem;
  }

  /* subtle grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(var(--border) 1px, transparent 1px),
      linear-gradient(90deg, var(--border) 1px, transparent 1px);
    background-size: 48px 48px;
    opacity: 0.35;
    pointer-events: none;
  }

  .card {
    position: relative;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 20px;
    max-width: 640px;
    width: 100%;
    padding: 2.5rem;
    overflow: hidden;
    animation: fadeUp 0.7s ease both;
  }

  /* top-right orb glow */
  .card::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 220px; height: 220px;
    background: radial-gradient(circle, rgba(110,231,183,0.18) 0%, transparent 70%);
    pointer-events: none;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ── Header ── */
  .header {
    display: flex;
    align-items: flex-start;
    gap: 1.25rem;
    margin-bottom: 1.75rem;
    animation: fadeUp 0.7s 0.1s ease both;
  }

  .avatar {
    width: 52px; height: 52px;
    border-radius: 14px;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    flex-shrink: 0;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.4rem;
    font-weight: 800;
    color: #0d0d0f;
    letter-spacing: -1px;
  }

  .name-block h1 {
    font-size: 1.4rem;
    font-weight: 800;
    letter-spacing: -0.5px;
    line-height: 1.1;
  }

  .name-block h1 span {
    color: var(--accent);
  }

  .tagline {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--muted);
    margin-top: 0.3rem;
    letter-spacing: 0.04em;
  }

  .tagline em {
    font-style: italic;
    color: var(--accent3);
  }

  /* ── Divider ── */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, var(--accent), transparent);
    margin-bottom: 1.75rem;
    opacity: 0.4;
    animation: fadeUp 0.7s 0.2s ease both;
  }

  /* ── Buttons ── */
  .links {
    display: flex;
    gap: 0.75rem;
    margin-bottom: 2rem;
    flex-wrap: wrap;
    animation: fadeUp 0.7s 0.25s ease both;
  }

  .btn {
    display: inline-flex;
    align-items: center;
    gap: 0.45rem;
    padding: 0.5rem 1rem;
    border-radius: 8px;
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    font-weight: 500;
    letter-spacing: 0.03em;
    text-decoration: none;
    border: 1px solid var(--border);
    background: var(--surface2);
    color: var(--text);
    transition: all 0.2s;
    cursor: pointer;
  }

  .btn:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: var(--accent-glow);
  }

  .btn svg { width: 14px; height: 14px; }

  /* ── Tech Stack ── */
  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 0.75rem;
  }

  .stack-group {
    margin-bottom: 1.25rem;
    animation: fadeUp 0.7s ease both;
  }

  .stack-group:nth-child(2) { animation-delay: 0.3s; }
  .stack-group:nth-child(3) { animation-delay: 0.35s; }
  .stack-group:nth-child(4) { animation-delay: 0.4s; }
  .stack-group:nth-child(5) { animation-delay: 0.45s; }
  .stack-group:nth-child(6) { animation-delay: 0.5s; }
  .stack-group:nth-child(7) { animation-delay: 0.55s; }

  .pills {
    display: flex;
    flex-wrap: wrap;
    gap: 0.45rem;
  }

  .pill {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    padding: 0.28rem 0.7rem;
    border-radius: 6px;
    border: 1px solid transparent;
    transition: all 0.2s;
    cursor: default;
  }

  /* color variants */
  .pill.lang {
    background: rgba(129, 140, 248, 0.1);
    border-color: rgba(129, 140, 248, 0.25);
    color: var(--accent2);
  }
  .pill.lang:hover {
    background: rgba(129, 140, 248, 0.2);
    border-color: var(--accent2);
  }

  .pill.fw {
    background: rgba(110, 231, 183, 0.08);
    border-color: rgba(110, 231, 183, 0.2);
    color: var(--accent);
  }
  .pill.fw:hover {
    background: rgba(110, 231, 183, 0.16);
    border-color: var(--accent);
  }

  .pill.db {
    background: rgba(251, 191, 36, 0.08);
    border-color: rgba(251, 191, 36, 0.2);
    color: #fbbf24;
  }
  .pill.db:hover {
    background: rgba(251, 191, 36, 0.16);
    border-color: #fbbf24;
  }

  .pill.qa {
    background: rgba(244, 114, 182, 0.08);
    border-color: rgba(244, 114, 182, 0.2);
    color: var(--accent3);
  }
  .pill.qa:hover {
    background: rgba(244, 114, 182, 0.16);
    border-color: var(--accent3);
  }

  .pill.cloud {
    background: rgba(56, 189, 248, 0.08);
    border-color: rgba(56, 189, 248, 0.2);
    color: #38bdf8;
  }
  .pill.cloud:hover {
    background: rgba(56, 189, 248, 0.16);
    border-color: #38bdf8;
  }

  .pill.devops {
    background: rgba(167, 139, 250, 0.08);
    border-color: rgba(167, 139, 250, 0.2);
    color: #a78bfa;
  }
  .pill.devops:hover {
    background: rgba(167, 139, 250, 0.16);
    border-color: #a78bfa;
  }
</style>
</head>
<body>

<div class="card">

  <div class="header">
    <div class="avatar">TC</div>
    <div class="name-block">
      <h1>Thisara <span>Chathuranga</span></h1>
      <p class="tagline">Software Engineer &nbsp;·&nbsp; <em>I engineer solutions that scale, survive, and ship.</em></p>
    </div>
  </div>

  <div class="divider"></div>

  <div class="links">
    <a class="btn" href="mailto:tchathuranga.dev@gmail.com">
      <!-- gmail icon -->
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20 4H4C2.9 4 2 4.9 2 6v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4-8 5-8-5V6l8 5 8-5v2z"/></svg>
      Email Me
    </a>
    <a class="btn" href="https://linkedin.com" target="_blank">
      <!-- linkedin icon -->
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M19 3H5C3.895 3 3 3.895 3 5v14c0 1.105.895 2 2 2h14c1.105 0 2-.895 2-2V5c0-1.105-.895-2-2-2zM9 17H6.477v-7H9V17zM7.694 8.717c-.771 0-1.286-.514-1.286-1.2s.514-1.2 1.371-1.2c.771 0 1.286.514 1.286 1.2s-.514 1.2-1.371 1.2zM18 17h-2.442v-3.826c0-1.058-.651-1.302-.895-1.302s-1.058.163-1.058 1.302V17h-2.523v-7h2.523v.977C13.93 10.407 14.581 10 15.802 10 17.023 10 18 10.977 18 13.174V17z"/></svg>
      Connect
    </a>
  </div>

  <!-- Tech Stack -->
  <div id="stack">

    <div class="stack-group">
      <div class="section-label">Languages</div>
      <div class="pills">
        <span class="pill lang">JavaScript</span>
        <span class="pill lang">TypeScript</span>
        <span class="pill lang">Java</span>
        <span class="pill lang">Perl</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="section-label">Frameworks & Libraries</div>
      <div class="pills">
        <span class="pill fw">React</span>
        <span class="pill fw">Next.js</span>
        <span class="pill fw">Spring Boot</span>
        <span class="pill fw">NestJS</span>
        <span class="pill fw">Node.js</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="section-label">Databases</div>
      <div class="pills">
        <span class="pill db">MySQL</span>
        <span class="pill db">MongoDB</span>
        <span class="pill db">Oracle</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="section-label">Testing & QA</div>
      <div class="pills">
        <span class="pill qa">Selenium WebDriver</span>
        <span class="pill qa">Jest</span>
        <span class="pill qa">JUnit</span>
        <span class="pill qa">React Testing Library</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="section-label">Cloud & Infrastructure</div>
      <div class="pills">
        <span class="pill cloud">AWS</span>
        <span class="pill cloud">Linux</span>
      </div>
    </div>

    <div class="stack-group">
      <div class="section-label">DevOps & Monitoring</div>
      <div class="pills">
        <span class="pill devops">Docker</span>
        <span class="pill devops">GitHub Actions</span>
        <span class="pill devops">Prometheus</span>
        <span class="pill devops">Grafana</span>
        <span class="pill devops">Apache Kafka</span>
      </div>
    </div>

  </div>
</div>

</body>
</html>
