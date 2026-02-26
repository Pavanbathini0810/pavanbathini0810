<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pavan Kumar · Full Stack Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0e1a;
    --bg2: #0f1422;
    --card: #141828;
    --card2: #1a1f30;
    --border: #232840;
    --accent: #4f8ef7;
    --accent2: #7c5cfc;
    --accent3: #38d9a9;
    --text: #e8ecf5;
    --muted: #7a82a0;
    --tag: #1e2540;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-size: 15px;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* ── GRID NOISE BACKGROUND ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      radial-gradient(ellipse 80% 60% at 70% 10%, rgba(79,142,247,0.07) 0%, transparent 60%),
      radial-gradient(ellipse 60% 40% at 10% 80%, rgba(124,92,252,0.06) 0%, transparent 60%);
    pointer-events: none;
    z-index: 0;
  }

  .wrap { max-width: 860px; margin: 0 auto; padding: 0 24px; position: relative; z-index: 1; }

  /* ── NAV ── */
  nav {
    border-bottom: 1px solid var(--border);
    padding: 18px 0;
    position: sticky;
    top: 0;
    background: rgba(10,14,26,0.92);
    backdrop-filter: blur(12px);
    z-index: 100;
  }
  nav .wrap { display: flex; align-items: center; justify-content: space-between; }
  .nav-logo {
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    color: var(--accent);
    letter-spacing: 0.05em;
  }
  .nav-links { display: flex; gap: 28px; }
  .nav-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.03em;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--text); }

  /* ── HERO ── */
  .hero {
    padding: 80px 0 60px;
    border-bottom: 1px solid var(--border);
  }
  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    background: rgba(79,142,247,0.1);
    border: 1px solid rgba(79,142,247,0.25);
    border-radius: 100px;
    padding: 5px 14px;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    margin-bottom: 24px;
    letter-spacing: 0.04em;
  }
  .hero-badge span { width: 6px; height: 6px; background: var(--accent3); border-radius: 50%; animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.5;transform:scale(1.3)} }

  .hero h1 {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(38px, 6vw, 58px);
    line-height: 1.1;
    letter-spacing: -0.02em;
    margin-bottom: 10px;
  }
  .hero h1 em {
    font-style: italic;
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .hero-sub {
    font-size: 16px;
    color: var(--muted);
    margin-bottom: 32px;
    font-weight: 300;
    max-width: 520px;
  }
  .hero-pills { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 36px; }
  .pill {
    background: var(--tag);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 5px 12px;
    font-size: 12px;
    color: var(--muted);
    font-family: 'DM Mono', monospace;
  }
  .pill.hot { color: var(--accent); border-color: rgba(79,142,247,0.3); background: rgba(79,142,247,0.06); }
  .pill.green { color: var(--accent3); border-color: rgba(56,217,169,0.3); background: rgba(56,217,169,0.06); }

  .hero-cta { display: flex; gap: 12px; flex-wrap: wrap; }
  .btn {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 10px 20px;
    border-radius: 8px;
    font-size: 13px;
    font-weight: 500;
    text-decoration: none;
    transition: all 0.2s;
    cursor: pointer;
    border: none;
  }
  .btn-primary {
    background: var(--accent);
    color: #fff;
  }
  .btn-primary:hover { background: #6aa0ff; transform: translateY(-1px); }
  .btn-ghost {
    background: transparent;
    color: var(--muted);
    border: 1px solid var(--border);
  }
  .btn-ghost:hover { color: var(--text); border-color: var(--muted); }

  /* ── SECTIONS ── */
  section { padding: 56px 0; border-bottom: 1px solid var(--border); }
  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 8px;
  }
  .section-title {
    font-family: 'DM Serif Display', serif;
    font-size: 28px;
    margin-bottom: 32px;
    letter-spacing: -0.01em;
  }

  /* ── ABOUT GRID ── */
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .about-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 18px;
    display: flex;
    align-items: flex-start;
    gap: 12px;
    transition: border-color 0.2s;
  }
  .about-item:hover { border-color: rgba(79,142,247,0.4); }
  .about-icon { font-size: 18px; margin-top: 1px; flex-shrink: 0; }
  .about-text { font-size: 13px; color: var(--muted); line-height: 1.5; }
  .about-text strong { color: var(--text); display: block; margin-bottom: 2px; font-size: 13px; }

  /* ── PROJECTS ── */
  .projects-grid { display: grid; gap: 16px; }
  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 22px 24px;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 16px;
    align-items: start;
    transition: border-color 0.2s, transform 0.2s;
    text-decoration: none;
    color: inherit;
  }
  .project-card:hover { border-color: rgba(79,142,247,0.4); transform: translateY(-2px); }
  .project-emoji { font-size: 22px; margin-bottom: 10px; display: block; }
  .project-name {
    font-family: 'DM Serif Display', serif;
    font-size: 18px;
    margin-bottom: 6px;
    letter-spacing: -0.01em;
  }
  .project-desc { font-size: 13px; color: var(--muted); line-height: 1.5; margin-bottom: 14px; }
  .project-tags { display: flex; flex-wrap: wrap; gap: 6px; }
  .tag {
    background: var(--tag);
    border: 1px solid var(--border);
    padding: 3px 9px;
    border-radius: 4px;
    font-size: 11px;
    color: var(--muted);
    font-family: 'DM Mono', monospace;
  }
  .project-stat {
    background: var(--card2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 14px;
    text-align: center;
    min-width: 110px;
  }
  .stat-num {
    font-family: 'DM Mono', monospace;
    font-size: 20px;
    font-weight: 500;
    color: var(--accent);
    display: block;
  }
  .stat-label { font-size: 11px; color: var(--muted); margin-top: 2px; }

  /* ── EXPERIENCE ── */
  .exp-list { display: grid; gap: 20px; }
  .exp-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 22px 24px;
  }
  .exp-header { display: flex; align-items: flex-start; justify-content: space-between; margin-bottom: 14px; gap: 16px; }
  .exp-title { font-family: 'DM Serif Display', serif; font-size: 18px; letter-spacing: -0.01em; }
  .exp-company { font-size: 13px; color: var(--accent); margin-top: 3px; font-weight: 500; }
  .exp-date {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    background: var(--tag);
    border: 1px solid var(--border);
    padding: 4px 10px;
    border-radius: 4px;
    white-space: nowrap;
    flex-shrink: 0;
  }
  .exp-bullets { list-style: none; display: grid; gap: 6px; }
  .exp-bullets li {
    font-size: 13px;
    color: var(--muted);
    padding-left: 16px;
    position: relative;
    line-height: 1.5;
  }
  .exp-bullets li::before {
    content: '→';
    position: absolute;
    left: 0;
    color: var(--accent);
    font-size: 11px;
    top: 2px;
  }

  /* ── SKILLS ── */
  .skills-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .skill-group {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 18px;
  }
  .skill-group-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    color: var(--accent);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 6px; }

  /* ── CERT BADGE ── */
  .cert-badge {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    background: linear-gradient(135deg, rgba(255,153,0,0.08), rgba(255,153,0,0.03));
    border: 1px solid rgba(255,153,0,0.25);
    border-radius: 10px;
    padding: 14px 20px;
    margin-top: 20px;
  }
  .cert-icon { font-size: 24px; }
  .cert-text { font-size: 13px; color: var(--text); font-weight: 500; }
  .cert-sub { font-size: 11px; color: var(--muted); margin-top: 2px; font-family: 'DM Mono', monospace; }

  /* ── FOOTER ── */
  footer {
    padding: 40px 0;
    text-align: center;
  }
  footer p { font-size: 12px; color: var(--muted); font-family: 'DM Mono', monospace; }

  /* ── ANIMATIONS ── */
  .fade-in {
    opacity: 0;
    transform: translateY(18px);
    animation: fadeUp 0.55s ease forwards;
  }
  @keyframes fadeUp { to { opacity: 1; transform: translateY(0); } }
  .delay-1 { animation-delay: 0.1s; }
  .delay-2 { animation-delay: 0.2s; }
  .delay-3 { animation-delay: 0.3s; }
  .delay-4 { animation-delay: 0.4s; }

  @media (max-width: 600px) {
    .about-grid, .skills-grid { grid-template-columns: 1fr; }
    .project-card { grid-template-columns: 1fr; }
    .hero h1 { font-size: 34px; }
    .nav-links { display: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="wrap">
    <span class="nav-logo">pavan.dev</span>
    <div class="nav-links">
      <a href="#about">About</a>
      <a href="#projects">Projects</a>
      <a href="#experience">Experience</a>
      <a href="#skills">Skills</a>
    </div>
  </div>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="wrap">
    <div class="hero-badge fade-in"><span></span> Open to new opportunities</div>
    <h1 class="fade-in delay-1">Hi, I'm <em>Pavan Kumar</em></h1>
    <p class="hero-sub fade-in delay-2">Full Stack Software Engineer · AWS Certified Solutions Architect · 4+ Years building cloud-native platforms at scale</p>
    <div class="hero-pills fade-in delay-3">
      <span class="pill hot">☁️ AWS Certified</span>
      <span class="pill hot">⚛️ React · Spring Boot</span>
      <span class="pill green">✅ McKinsey & Company</span>
      <span class="pill">🔧 Kubernetes · Terraform</span>
      <span class="pill">🤖 AI/ML Integrations</span>
    </div>
    <div class="hero-cta fade-in delay-4">
      <a href="mailto:pavanbathini329@gmail.com" class="btn btn-primary">✉ Get in Touch</a>
      <a href="https://linkedin.com/in/pavan-kumar-bathini-35a615213/" target="_blank" class="btn btn-ghost">🔗 LinkedIn</a>
      <a href="#projects" class="btn btn-ghost">🚀 View Projects</a>
    </div>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="wrap">
    <div class="section-label">// about</div>
    <div class="section-title">What I Bring</div>
    <div class="about-grid">
      <div class="about-item">
        <span class="about-icon">🏢</span>
        <div class="about-text"><strong>McKinsey & Company</strong>Software Engineer 2 — cloud-native analytics platforms at enterprise scale</div>
      </div>
      <div class="about-item">
        <span class="about-icon">☁️</span>
        <div class="about-text"><strong>AWS Certified Solutions Architect</strong>Lambda · Step Functions · DynamoDB · Elasticsearch · S3</div>
      </div>
      <div class="about-item">
        <span class="about-icon">⚛️</span>
        <div class="about-text"><strong>Full Stack</strong>React · Angular · Vue.js · Spring Boot · Node.js · FastAPI · Flask</div>
      </div>
      <div class="about-item">
        <span class="about-icon">🔧</span>
        <div class="about-text"><strong>DevOps & IaC</strong>Terraform · Docker · Kubernetes · GitHub Actions · Jenkins</div>
      </div>
      <div class="about-item">
        <span class="about-icon">🧪</span>
        <div class="about-text"><strong>Testing — 87% Coverage</strong>Jest · Jasmine · Mocha · JUnit on production systems</div>
      </div>
      <div class="about-item">
        <span class="about-icon">🤖</span>
        <div class="about-text"><strong>AI/ML</strong>Integrating machine learning and AI data solutions into production apps via AWS Bedrock</div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="wrap">
    <div class="section-label">// projects</div>
    <div class="section-title">Featured Projects</div>
    <div class="projects-grid">

      <div class="project-card">
        <div>
          <span class="project-emoji">🛍️</span>
          <div class="project-name">Product Catalog API</div>
          <div class="project-desc">Serverless REST API built with Spring Boot on AWS Lambda, provisioned entirely with Terraform IaC — enabling zero-downtime deploys and auto-scaling with no server management.</div>
          <div class="project-tags">
            <span class="tag">Spring Boot</span><span class="tag">AWS Lambda</span><span class="tag">DynamoDB</span><span class="tag">Terraform</span>
          </div>
        </div>
        <div class="project-stat">
          <span class="stat-num">0</span>
          <div class="stat-label">Downtime deploys</div>
        </div>
      </div>

      <div class="project-card">
        <div>
          <span class="project-emoji">⚛️</span>
          <div class="project-name">React Product Dashboard</div>
          <div class="project-desc">High-performance product search dashboard powered by Elasticsearch. Achieved sub-50ms search latency with 87% test coverage using Jest and Redux state management.</div>
          <div class="project-tags">
            <span class="tag">React</span><span class="tag">Redux</span><span class="tag">Elasticsearch</span><span class="tag">Jest</span>
          </div>
        </div>
        <div class="project-stat">
          <span class="stat-num">&lt;50ms</span>
          <div class="stat-label">Search latency</div>
        </div>
      </div>

      <div class="project-card">
        <div>
          <span class="project-emoji">🔄</span>
          <div class="project-name">Microservices Order System</div>
          <div class="project-desc">Domain-Driven Design decomposition into event-driven microservices using Node.js and AWS Step Functions, orchestrated with Docker/Kubernetes — cut feature delivery time by 50%.</div>
          <div class="project-tags">
            <span class="tag">Node.js</span><span class="tag">Step Functions</span><span class="tag">Mocha</span><span class="tag">Docker</span>
          </div>
        </div>
        <div class="project-stat">
          <span class="stat-num">50%</span>
          <div class="stat-label">Faster delivery</div>
        </div>
      </div>

      <div class="project-card">
        <div>
          <span class="project-emoji">🤖</span>
          <div class="project-name">AI Product Recommender</div>
          <div class="project-desc">ML-powered product recommendation engine using AWS Bedrock with real-time inference. Angular frontend with Jasmine tests and Python backend for model serving.</div>
          <div class="project-tags">
            <span class="tag">Angular</span><span class="tag">AWS Bedrock</span><span class="tag">Python</span><span class="tag">Jasmine</span>
          </div>
        </div>
        <div class="project-stat">
          <span class="stat-num">Real-time</span>
          <div class="stat-label">ML inference</div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="wrap">
    <div class="section-label">// experience</div>
    <div class="section-title">Work History</div>
    <div class="exp-list">

      <div class="exp-card">
        <div class="exp-header">
          <div>
            <div class="exp-title">Software Engineer 2</div>
            <div class="exp-company">McKinsey & Company · United States (Remote)</div>
          </div>
          <span class="exp-date">Feb 2025 – Present</span>
        </div>
        <ul class="exp-bullets">
          <li>Migrated legacy C#/.NET monolith to Dockerized Spring Boot microservices on Kubernetes (EKS), reducing cloud infrastructure costs by 30% and improving fault tolerance.</li>
          <li>Reduced API response time by 45% with Spring Boot, Redis caching, and Kafka async processing — sustaining 50,000+ daily requests under peak traffic.</li>
          <li>Re-engineered cloud data pipelines with AWS Glue, Redshift, and Python ETL for near real-time analytics, increasing marketing effectiveness by 22%.</li>
          <li>Increased deployment success rate by 40% automating CI/CD with Terraform, Jenkins, and GitHub Actions.</li>
          <li>Mentored engineers and led code reviews, reducing post-release incidents by 25%.</li>
        </ul>
      </div>

      <div class="exp-card">
        <div class="exp-header">
          <div>
            <div class="exp-title">Full Stack Developer</div>
            <div class="exp-company">CueTech Systems · India (Remote)</div>
          </div>
          <span class="exp-date">Apr 2020 – Jun 2023</span>
        </div>
        <ul class="exp-bullets">
          <li>Decomposed monolith into 6 microservices using domain-driven design + REST, cutting API response times by 45% with Spring Boot and DynamoDB optimization.</li>
          <li>Reduced unauthorized access vulnerabilities by 35% implementing OAuth2, JWT, and AWS Cognito; cut fraud incidents by 40% via Kafka event streams.</li>
          <li>Set up Prometheus, Grafana, and ELK Stack observability, reducing incident resolution time by 45% and achieving 99.5% uptime across 3 production microservices.</li>
          <li>Eliminated 100% of manual deployments with Jenkins, Docker, and Kubernetes pipelines.</li>
          <li>Automated regression and integration testing with Selenium, JUnit, and Appium, increasing code coverage by 35%.</li>
        </ul>
      </div>

    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="wrap">
    <div class="section-label">// skills</div>
    <div class="section-title">Tech Stack</div>
    <div class="skills-grid">
      <div class="skill-group">
        <div class="skill-group-label">Frontend</div>
        <div class="skill-tags">
          <span class="tag">React.js</span><span class="tag">Angular</span><span class="tag">Vue.js</span><span class="tag">Redux</span><span class="tag">TypeScript</span><span class="tag">Bootstrap</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-label">Backend & APIs</div>
        <div class="skill-tags">
          <span class="tag">Spring Boot</span><span class="tag">Node.js</span><span class="tag">FastAPI</span><span class="tag">Flask</span><span class="tag">GraphQL</span><span class="tag">REST</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-label">AWS</div>
        <div class="skill-tags">
          <span class="tag">Lambda</span><span class="tag">EKS</span><span class="tag">ECS</span><span class="tag">Glue</span><span class="tag">Redshift</span><span class="tag">Cognito</span><span class="tag">S3</span><span class="tag">DynamoDB</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-label">DevOps & IaC</div>
        <div class="skill-tags">
          <span class="tag">Terraform</span><span class="tag">Docker</span><span class="tag">Kubernetes</span><span class="tag">Jenkins</span><span class="tag">GitHub Actions</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-label">Data & Messaging</div>
        <div class="skill-tags">
          <span class="tag">Kafka</span><span class="tag">PostgreSQL</span><span class="tag">MongoDB</span><span class="tag">Redis</span><span class="tag">Elasticsearch</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-label">Testing & Observability</div>
        <div class="skill-tags">
          <span class="tag">Jest</span><span class="tag">JUnit</span><span class="tag">Selenium</span><span class="tag">Prometheus</span><span class="tag">Grafana</span><span class="tag">ELK Stack</span>
        </div>
      </div>
    </div>

    <div class="cert-badge">
      <span class="cert-icon">🏆</span>
      <div>
        <div class="cert-text">AWS Certified Solutions Architect – Associate</div>
        <div class="cert-sub">Amazon Web Services · 2024</div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="wrap">
    <p>pavan kumar · pavanbathini329@gmail.com · (913) 296-0205 · Overland Park, KS</p>
  </div>
</footer>

</body>
</html>
