<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Faiz Hassan Mughal — FullStack AI Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --ink: #0A0E1A;
    --ink-2: #10182B;
    --ink-3: #1C2740;
    --signal: #F5A524;
    --current: #35C7C0;
    --paper: #EDEFF5;
    --paper-dim: #8993AC;
    --paper-dimmer: #5C6580;
    --radius: 10px;
    --maxw: 980px;
  }

  *{ box-sizing: border-box; }
  html{ scroll-behavior: smooth; }
  body{
    margin:0;
    background: var(--ink);
    color: var(--paper);
    font-family: 'Inter', sans-serif;
    -webkit-font-smoothing: antialiased;
    overflow-x: hidden;
  }
  ::selection{ background: var(--signal); color: var(--ink); }

  a{ color: inherit; text-decoration: none; }

  .eyebrow{
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.78rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--current);
  }

  h1,h2,h3{
    font-family: 'Space Grotesk', sans-serif;
    margin: 0;
    color: var(--paper);
    letter-spacing: -0.01em;
  }

  /* background grid texture */
  .bg-grid{
    position: fixed;
    inset: 0;
    z-index: 0;
    background-image:
      linear-gradient(to right, rgba(255,255,255,0.028) 1px, transparent 1px),
      linear-gradient(to bottom, rgba(255,255,255,0.028) 1px, transparent 1px);
    background-size: 42px 42px;
    mask-image: radial-gradient(ellipse 80% 60% at 50% 0%, #000 40%, transparent 100%);
    pointer-events: none;
  }

  /* NAV */
  nav{
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 50;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 22px clamp(20px, 5vw, 64px);
    background: linear-gradient(to bottom, rgba(10,14,26,0.92), rgba(10,14,26,0));
    backdrop-filter: blur(6px);
  }
  .logo{
    font-family: 'IBM Plex Mono', monospace;
    font-weight: 600;
    font-size: 0.95rem;
    color: var(--paper);
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .logo::before{
    content: '';
    width: 8px; height: 8px;
    background: var(--signal);
    border-radius: 50%;
    box-shadow: 0 0 0 3px rgba(245,165,36,0.18);
  }
  .nav-links{
    display: flex;
    gap: 32px;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.82rem;
  }
  .nav-links a{
    color: var(--paper-dim);
    transition: color 0.2s;
    position: relative;
  }
  .nav-links a:hover{ color: var(--paper); }
  .nav-links .num{ color: var(--paper-dimmer); margin-right: 4px; }
  @media (max-width: 720px){ .nav-links{ display: none; } }

  /* PIPELINE SPINE */
  .spine{
    position: absolute;
    left: 50%;
    top: 0;
    bottom: 0;
    width: 2px;
    background: linear-gradient(to bottom, transparent, var(--ink-3) 4%, var(--ink-3) 96%, transparent);
    transform: translateX(-50%);
    z-index: 1;
  }
  .spine-fill{
    position: absolute;
    top: 0; left: 0;
    width: 100%;
    height: 0%;
    background: linear-gradient(to bottom, var(--signal), var(--current));
    transition: height 0.1s linear;
  }
  @media (max-width: 720px){ .spine{ left: 28px; } }

  .wrap{ position: relative; max-width: var(--maxw); margin: 0 auto; padding: 0 clamp(20px, 5vw, 40px); z-index: 2; }

  /* HERO */
  .hero{
    min-height: 100svh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: relative;
    padding-top: 80px;
  }
  .hero-kicker{
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.85rem;
    color: var(--paper-dim);
    margin-bottom: 18px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .hero-kicker .dot{
    width: 7px; height: 7px; border-radius: 50%;
    background: var(--current);
    animation: pulse 2s infinite;
  }
  @keyframes pulse{
    0%,100%{ opacity: 1; box-shadow: 0 0 0 0 rgba(53,199,192,0.4); }
    50%{ opacity: 0.6; box-shadow: 0 0 0 6px rgba(53,199,192,0); }
  }
  .hero h1{
    font-size: clamp(2.6rem, 7vw, 5rem);
    line-height: 1.02;
    font-weight: 700;
  }
  .hero h1 .accent{ color: var(--signal); }
  .hero-role{
    font-size: clamp(1.1rem, 2.4vw, 1.5rem);
    color: var(--paper-dim);
    margin-top: 18px;
    font-weight: 400;
    max-width: 640px;
  }
  .hero-role b{ color: var(--paper); font-weight: 600; }

  .terminal{
    margin-top: 40px;
    background: var(--ink-2);
    border: 1px solid var(--ink-3);
    border-radius: var(--radius);
    max-width: 560px;
    overflow: hidden;
    box-shadow: 0 20px 60px -20px rgba(0,0,0,0.6);
  }
  .terminal-head{
    display: flex;
    align-items: center;
    gap: 6px;
    padding: 10px 14px;
    border-bottom: 1px solid var(--ink-3);
  }
  .terminal-head span{
    width: 9px; height: 9px; border-radius: 50%;
    background: var(--ink-3);
  }
  .terminal-body{
    padding: 18px 20px 22px;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.88rem;
    color: var(--paper-dim);
    line-height: 1.7;
  }
  .terminal-body .prompt{ color: var(--current); }
  .terminal-body .out{ color: var(--paper); }
  .cursor{
    display: inline-block;
    width: 7px; height: 1.1em;
    background: var(--signal);
    margin-left: 2px;
    vertical-align: text-bottom;
    animation: blink 1s step-end infinite;
  }
  @keyframes blink{ 50%{ opacity: 0; } }

  .hero-actions{
    margin-top: 36px;
    display: flex;
    gap: 14px;
    flex-wrap: wrap;
  }
  .btn{
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.85rem;
    padding: 13px 22px;
    border-radius: 8px;
    display: inline-flex;
    align-items: center;
    gap: 8px;
    transition: all 0.2s ease;
    border: 1px solid transparent;
  }
  .btn-primary{
    background: var(--signal);
    color: var(--ink);
    font-weight: 600;
  }
  .btn-primary:hover{ background: #ffb841; transform: translateY(-2px); }
  .btn-ghost{
    border-color: var(--ink-3);
    color: var(--paper);
  }
  .btn-ghost:hover{ border-color: var(--current); color: var(--current); transform: translateY(-2px); }

  .scroll-cue{
    position: absolute;
    bottom: 36px;
    left: clamp(20px, 5vw, 40px);
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.72rem;
    color: var(--paper-dimmer);
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .scroll-cue .line{ width: 28px; height: 1px; background: var(--paper-dimmer); }

  /* SECTIONS / STAGES */
  .stage{
    position: relative;
    padding: 110px 0;
    display: grid;
    grid-template-columns: 1fr;
  }
  .stage-marker{
    position: absolute;
    left: 50%;
    top: 110px;
    transform: translateX(-50%);
    width: 15px; height: 15px;
    border-radius: 50%;
    background: var(--ink-2);
    border: 2px solid var(--ink-3);
    z-index: 3;
    transition: all 0.4s ease;
  }
  .stage-marker.active{
    border-color: var(--signal);
    background: var(--signal);
    box-shadow: 0 0 0 6px rgba(245,165,36,0.15);
  }
  @media (max-width: 720px){
    .stage-marker{ left: 28px; }
  }

  .stage-inner{
    max-width: 620px;
  }
  .stage:nth-child(even) .stage-inner{ margin-left: auto; text-align: right; }
  .stage:nth-child(even) .tag-row{ justify-content: flex-end; }
  .stage:nth-child(even) .stage-num{ margin-left: auto; }
  @media (max-width: 900px){
    .stage-inner{ max-width: 100%; margin-left: 64px !important; text-align: left !important; }
    .stage:nth-child(even) .tag-row{ justify-content: flex-start !important; }
    .stage:nth-child(even) .stage-num{ margin-left: 0 !important; }
  }

  .stage-num{
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.8rem;
    color: var(--paper-dimmer);
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 14px;
  }
  .stage-num b{ color: var(--current); font-weight: 600; }

  .stage h2{
    font-size: clamp(1.7rem, 3.2vw, 2.3rem);
    margin-bottom: 20px;
  }
  .stage p{
    color: var(--paper-dim);
    font-size: 1.02rem;
    line-height: 1.75;
  }
  .stage p + p{ margin-top: 14px; }

  /* about list */
  .fact-grid{
    margin-top: 28px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 14px;
    text-align: left !important;
  }
  .fact{
    background: var(--ink-2);
    border: 1px solid var(--ink-3);
    border-radius: var(--radius);
    padding: 16px 18px;
  }
  .fact .k{ font-family: 'IBM Plex Mono', monospace; font-size: 0.72rem; color: var(--paper-dimmer); text-transform: uppercase; letter-spacing: 0.08em; }
  .fact .v{ margin-top: 6px; font-size: 0.95rem; color: var(--paper); }
  @media (max-width: 560px){ .fact-grid{ grid-template-columns: 1fr; } }

  /* stack tags */
  .stack-group{ margin-top: 26px; }
  .stack-group + .stack-group{ margin-top: 22px; }
  .stack-label{
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.72rem;
    color: var(--paper-dimmer);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    margin-bottom: 10px;
  }
  .tag-row{ display: flex; flex-wrap: wrap; gap: 8px; }
  .tag{
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.8rem;
    padding: 7px 13px;
    border: 1px solid var(--ink-3);
    border-radius: 6px;
    color: var(--paper-dim);
    background: var(--ink-2);
    transition: all 0.2s ease;
  }
  .tag:hover{ border-color: var(--current); color: var(--current); }

  /* experience */
  .exp-card{
    text-align: left !important;
    background: var(--ink-2);
    border: 1px solid var(--ink-3);
    border-radius: var(--radius);
    padding: 22px 24px;
    margin-top: 16px;
  }
  .exp-card .role{ font-family: 'Space Grotesk', sans-serif; font-size: 1.08rem; font-weight: 600; color: var(--paper); }
  .exp-card .org{ color: var(--current); font-family: 'IBM Plex Mono', monospace; font-size: 0.85rem; margin-top: 4px; }
  .exp-card p{ margin-top: 10px; font-size: 0.94rem; }
  .stage:nth-child(even) .exp-card{ margin-left: auto; }

  /* projects */
  .project-grid{
    text-align: left !important;
    margin-top: 26px;
    display: grid;
    grid-template-columns: 1fr;
    gap: 16px;
  }
  .project-card{
    background: var(--ink-2);
    border: 1px dashed var(--ink-3);
    border-radius: var(--radius);
    padding: 22px 24px;
    position: relative;
  }
  .project-card .ph-tag{
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.68rem;
    color: var(--ink);
    background: var(--current);
    padding: 3px 9px;
    border-radius: 5px;
    position: absolute;
    top: 18px; right: 18px;
    text-transform: uppercase;
    letter-spacing: 0.06em;
  }
  .project-card h3{ font-size: 1.05rem; font-weight: 600; padding-right: 90px; }
  .project-card p{ margin-top: 8px; font-size: 0.9rem; }
  .project-card .tag-row{ margin-top: 14px; justify-content: flex-start !important; }

  /* contact */
  .contact-links{
    text-align: left !important;
    margin-top: 28px;
    display: flex;
    flex-direction: column;
    gap: 12px;
    align-items: flex-start;
  }
  .stage:nth-child(even) .contact-links{ align-items: flex-end; margin-left: auto; }
  .contact-link{
    display: inline-flex;
    align-items: center;
    gap: 10px;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.95rem;
    color: var(--paper);
    padding: 12px 18px;
    border: 1px solid var(--ink-3);
    border-radius: 8px;
    background: var(--ink-2);
    transition: all 0.2s ease;
  }
  .contact-link:hover{ border-color: var(--signal); color: var(--signal); transform: translateX(4px); }
  .contact-link svg{ width: 16px; height: 16px; flex-shrink: 0; }

  footer{
    text-align: center;
    padding: 40px 20px 50px;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 0.75rem;
    color: var(--paper-dimmer);
    position: relative;
    z-index: 2;
  }

  /* reveal animation */
  .reveal{
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.in{ opacity: 1; transform: translateY(0); }

  @media (prefers-reduced-motion: reduce){
    *{ animation: none !important; transition: none !important; scroll-behavior: auto !important; }
  }

  a:focus-visible, button:focus-visible{
    outline: 2px solid var(--signal);
    outline-offset: 3px;
  }
</style>
</head>
<body>

<div class="bg-grid"></div>

<nav>
  <div class="logo">faiz.dev</div>
  <div class="nav-links">
    <a href="#about"><span class="num">01</span>Ingest</a>
    <a href="#stack"><span class="num">02</span>Train</a>
    <a href="#experience"><span class="num">03</span>Ship</a>
    <a href="#projects"><span class="num">04</span>Deploy</a>
    <a href="#contact"><span class="num">05</span>Connect</a>
  </div>
</nav>

<div class="spine"><div class="spine-fill" id="spineFill"></div></div>

<!-- HERO -->
<section class="hero wrap">
  <div class="hero-kicker"><span class="dot"></span>AVAILABLE FOR OPPORTUNITIES</div>
  <h1>Faiz Hassan<br><span class="accent">Mughal</span></h1>
  <p class="hero-role">FullStack <b>AI Engineer</b> & Data Scientist — I build the pipeline from raw data to shipped product, and the interface people actually use to touch it.</p>

  <div class="terminal">
    <div class="terminal-head"><span></span><span></span><span></span></div>
    <div class="terminal-body">
      <div><span class="prompt">faiz@pipeline</span> ~ % whoami</div>
      <div class="out" id="typedOut"></div>
    </div>
  </div>

  <div class="hero-actions">
    <a href="#projects" class="btn btn-primary">View the work →</a>
    <a href="#contact" class="btn btn-ghost">Get in touch</a>
  </div>

  <div class="scroll-cue"><div class="line"></div>scroll to run the pipeline</div>
</section>

<!-- 01 ABOUT -->
<section class="stage reveal" id="about">
  <div class="stage-marker" data-marker></div>
  <div class="wrap">
    <div class="stage-inner">
      <div class="stage-num"><b>01</b> / INGEST — ABOUT</div>
      <h2>Data scientist by trade, full-stack builder by habit.</h2>
      <p>I work as a Data Scientist at <b style="color:var(--paper)">Datics AI</b>, and spend my free time contributing to <b style="color:var(--paper)">ReactPlay</b>, an open playground for React developers. I like projects that force both halves of my brain to show up — the modeling side and the shipping side.</p>
      <p>Currently deep in Next.js and machine learning, and always looking for the next thing worth learning in public.</p>

      <div class="fact-grid">
        <div class="fact"><div class="k">Role</div><div class="v">Data Scientist, Datics AI</div></div>
        <div class="fact"><div class="k">Open Source</div><div class="v">Contributor, ReactPlay</div></div>
        <div class="fact"><div class="k">Background</div><div class="v">B.Sc. Computer Science</div></div>
        <div class="fact"><div class="k">Off the clock</div><div class="v">Sketching & watching shows</div></div>
      </div>
    </div>
  </div>
</section>

<!-- 02 STACK -->
<section class="stage reveal" id="stack">
  <div class="stage-marker" data-marker></div>
  <div class="wrap">
    <div class="stage-inner">
      <div class="stage-num"><b>02</b> / TRAIN — STACK</div>
      <h2>Tools I reach for at each layer.</h2>
      <p>From the model to the pixel — languages, frameworks, and infra I use to take an idea from notebook to production.</p>

      <div class="stack-group">
        <div class="stack-label">Languages</div>
        <div class="tag-row">
          <span class="tag">Python</span><span class="tag">JavaScript</span><span class="tag">Java</span><span class="tag">HTML5</span><span class="tag">CSS3</span>
        </div>
      </div>
      <div class="stack-group">
        <div class="stack-label">Frontend</div>
        <div class="tag-row">
          <span class="tag">React</span><span class="tag">Next.js</span><span class="tag">Redux</span><span class="tag">TailwindCSS</span><span class="tag">SASS</span><span class="tag">MUI</span><span class="tag">Framer Motion</span>
        </div>
      </div>
      <div class="stack-group">
        <div class="stack-label">Backend & Data</div>
        <div class="tag-row">
          <span class="tag">Node.js</span><span class="tag">GraphQL</span><span class="tag">Apollo</span><span class="tag">MongoDB</span><span class="tag">MySQL</span><span class="tag">JWT</span>
        </div>
      </div>
      <div class="stack-group">
        <div class="stack-label">Tooling & Infra</div>
        <div class="tag-row">
          <span class="tag">Docker</span><span class="tag">Kubernetes</span><span class="tag">Linux</span><span class="tag">Postman</span><span class="tag">Jira</span><span class="tag">Vercel</span><span class="tag">Figma</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- 03 EXPERIENCE -->
<section class="stage reveal" id="experience">
  <div class="stage-marker" data-marker></div>
  <div class="wrap">
    <div class="stage-inner">
      <div class="stage-num"><b>03</b> / SHIP — EXPERIENCE</div>
      <h2>Where the work has lived.</h2>

      <div class="exp-card">
        <div class="role">Data Scientist</div>
        <div class="org">Datics AI</div>
        <p>Working on data-driven products — from modeling to the systems that put those models in front of people.</p>
      </div>
      <div class="exp-card">
        <div class="role">Open Source Contributor</div>
        <div class="org">ReactPlay</div>
        <p>Contributing to a community playground for React developers to build and share small, focused projects.</p>
      </div>
    </div>
  </div>
</section>

<!-- 04 PROJECTS -->
<section class="stage reveal" id="projects">
  <div class="stage-marker" data-marker></div>
  <div class="wrap">
    <div class="stage-inner">
      <div class="stage-num"><b>04</b> / DEPLOY — PROJECTS</div>
      <h2>Selected work.</h2>
      <p>Three slots, ready to load — swap in your real projects here.</p>

      <div class="project-grid">
        <div class="project-card">
          <span class="ph-tag">Edit me</span>
          <h3>Project One — ML-powered product</h3>
          <p>One line on the problem it solves and the impact it had. Add a link to the repo or live demo.</p>
          <div class="tag-row"><span class="tag">Python</span><span class="tag">React</span></div>
        </div>
        <div class="project-card">
          <span class="ph-tag">Edit me</span>
          <h3>Project Two — Full-stack app</h3>
          <p>What it does, who it's for, and the stack it's built on. Keep it to two sentences.</p>
          <div class="tag-row"><span class="tag">Next.js</span><span class="tag">MongoDB</span></div>
        </div>
        <div class="project-card">
          <span class="ph-tag">Edit me</span>
          <h3>Project Three — Open source contribution</h3>
          <p>A ReactPlay project or repo you're proud of, with a short note on your role in it.</p>
          <div class="tag-row"><span class="tag">GraphQL</span><span class="tag">Node.js</span></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- 05 CONTACT -->
<section class="stage reveal" id="contact">
  <div class="stage-marker" data-marker></div>
  <div class="wrap">
    <div class="stage-inner">
      <div class="stage-num"><b>05</b> / CONNECT — CONTACT</div>
      <h2>Let's build something.</h2>
      <p>Open to new opportunities, collaborations, and conversations about data, product, or anything worth learning in public.</p>

      <div class="contact-links">
        <a class="contact-link" href="mailto:faizh1512@gmail.com">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect x="3" y="5" width="18" height="14" rx="2"/><path d="m3 7 9 6 9-6"/></svg>
          faizh1512@gmail.com
        </a>
        <a class="contact-link" href="https://www.linkedin.com/in/faizhassanmughal/" target="_blank" rel="noopener">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M7 10v6M7 7v.01M12 16v-3.5a2.5 2.5 0 0 1 5 0V16M12 10v6"/></svg>
          linkedin.com/in/faizhassanmughal
        </a>
      </div>
    </div>
  </div>
</section>

<footer>Built by Faiz Hassan Mughal · Pipeline status: <span style="color:var(--current)">deployed</span></footer>

<script>
  // typing effect
  const line = "FullStack AI Engineer — trained on data, deployed to production.";
  const out = document.getElementById('typedOut');
  let i = 0;
  function type(){
    if(i <= line.length){
      out.innerHTML = line.slice(0,i) + '<span class="cursor"></span>';
      i++;
      setTimeout(type, 32);
    }
  }
  type();

  // spine fill on scroll
  const spineFill = document.getElementById('spineFill');
  const prefersReduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  function updateSpine(){
    const scrollTop = window.scrollY;
    const docHeight = document.documentElement.scrollHeight - window.innerHeight;
    const pct = docHeight > 0 ? Math.min(100, (scrollTop/docHeight)*100) : 0;
    spineFill.style.height = pct + '%';
  }
  window.addEventListener('scroll', updateSpine, {passive:true});
  updateSpine();

  // reveal + marker activation
  const stages = document.querySelectorAll('.stage.reveal');
  const observer = new IntersectionObserver((entries)=>{
    entries.forEach(entry=>{
      if(entry.isIntersecting){
        entry.target.classList.add('in');
        const marker = entry.target.querySelector('[data-marker]');
        if(marker) marker.classList.add('active');
      }
    });
  }, {threshold: 0.25});
  stages.forEach(s=>observer.observe(s));
</script>

</body>
</html>
