<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Yash Jain — Flutter & Android Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300..700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<link href="https://api.fontshare.com/v2/css?f[]=cabinet-grotesk@400,500,700,800&display=swap" rel="stylesheet">
<style>
/* === TOKENS === */
:root,[data-theme="light"]{
  --color-bg:#f7f6f2;--color-surface:#f0eeea;--color-surface-2:#e8e5e0;
  --color-border:oklch(0.2 0.01 80/0.12);--color-divider:oklch(0.2 0.01 80/0.08);
  --color-text:#1a1a1a;--color-text-muted:#5a5a5a;--color-text-faint:#999;
  --color-primary:#0175C2;--color-primary-hover:#015fa3;--color-primary-hl:oklch(0.6 0.15 225/0.12);
  --color-flutter:#02569B;--color-dart:#0175C2;
  --shadow-sm:0 1px 3px oklch(0.2 0.01 80/0.07);--shadow-md:0 4px 16px oklch(0.2 0.01 80/0.10);--shadow-lg:0 12px 40px oklch(0.2 0.01 80/0.14);
  --radius-sm:0.375rem;--radius-md:0.5rem;--radius-lg:0.75rem;--radius-xl:1rem;--radius-full:9999px;
  --space-1:.25rem;--space-2:.5rem;--space-3:.75rem;--space-4:1rem;--space-5:1.25rem;--space-6:1.5rem;--space-8:2rem;--space-10:2.5rem;--space-12:3rem;--space-16:4rem;--space-20:5rem;
  --text-xs:clamp(.75rem,.7rem + .25vw,.875rem);--text-sm:clamp(.875rem,.8rem + .35vw,1rem);
  --text-base:clamp(1rem,.95rem + .25vw,1.125rem);--text-lg:clamp(1.125rem,1rem + .75vw,1.5rem);
  --text-xl:clamp(1.5rem,1.2rem + 1.25vw,2.25rem);--text-2xl:clamp(2rem,1.2rem + 2.5vw,3.5rem);
  --text-hero:clamp(2.8rem,.5rem + 6vw,6rem);
  --font-display:'Cabinet Grotesk','Space Grotesk',sans-serif;--font-body:'Space Grotesk',sans-serif;--font-mono:'Space Mono',monospace;
  --transition:180ms cubic-bezier(0.16,1,0.3,1);
}
[data-theme="dark"]{
  --color-bg:#0d1117;--color-surface:#161b22;--color-surface-2:#21262d;
  --color-border:oklch(1 0 0/0.09);--color-divider:oklch(1 0 0/0.06);
  --color-text:#e6edf3;--color-text-muted:#8b949e;--color-text-faint:#484f58;
  --color-primary:#58a6ff;--color-primary-hover:#79c0ff;--color-primary-hl:oklch(0.7 0.15 225/0.12);
  --color-flutter:#47b5ff;--color-dart:#58a6ff;
  --shadow-sm:0 1px 3px oklch(0 0 0/0.3);--shadow-md:0 4px 16px oklch(0 0 0/0.4);--shadow-lg:0 12px 40px oklch(0 0 0/0.5);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
html{-webkit-font-smoothing:antialiased;text-rendering:optimizeLegibility;scroll-behavior:smooth;scroll-padding-top:5rem;}
body{min-height:100dvh;line-height:1.6;font-family:var(--font-body);font-size:var(--text-base);color:var(--color-text);background:var(--color-bg);transition:background var(--transition),color var(--transition);}
img,svg{display:block;max-width:100%;}
a{color:var(--color-primary);text-decoration:none;transition:color var(--transition);}
a:hover{color:var(--color-primary-hover);}
button{cursor:pointer;background:none;border:none;font:inherit;color:inherit;}
::selection{background:var(--color-primary-hl);color:var(--color-text);}
:focus-visible{outline:2px solid var(--color-primary);outline-offset:3px;border-radius:var(--radius-sm);}
@media(prefers-reduced-motion:reduce){*,*::before,*::after{animation-duration:.01ms!important;transition-duration:.01ms!important;}}

/* === LAYOUT === */
.container{max-width:1040px;margin-inline:auto;padding-inline:clamp(var(--space-4),4vw,var(--space-8));}
.container--narrow{max-width:720px;margin-inline:auto;padding-inline:clamp(var(--space-4),4vw,var(--space-8));}
section{padding-block:clamp(var(--space-12),6vw,var(--space-20));}

/* === NAV === */
nav{position:sticky;top:0;z-index:100;background:oklch(from var(--color-bg) l c h/0.85);backdrop-filter:blur(12px);-webkit-backdrop-filter:blur(12px);border-bottom:1px solid var(--color-border);}
.nav-inner{max-width:1040px;margin-inline:auto;padding-inline:clamp(var(--space-4),4vw,var(--space-8));height:3.5rem;display:flex;align-items:center;justify-content:space-between;}
.nav-logo{font-family:var(--font-display);font-weight:800;font-size:var(--text-lg);letter-spacing:-.02em;}
.nav-logo span{color:var(--color-primary);}
.nav-links{display:flex;gap:var(--space-6);list-style:none;}
.nav-links a{font-size:var(--text-sm);color:var(--color-text-muted);transition:color var(--transition);}
.nav-links a:hover{color:var(--color-text);}
.nav-actions{display:flex;align-items:center;gap:var(--space-3);}
#theme-toggle{width:2rem;height:2rem;display:flex;align-items:center;justify-content:center;border-radius:var(--radius-md);color:var(--color-text-muted);transition:color var(--transition),background var(--transition);}
#theme-toggle:hover{background:var(--color-surface);color:var(--color-text);}
.hamburger{display:none;width:2rem;height:2rem;align-items:center;justify-content:center;border-radius:var(--radius-md);color:var(--color-text-muted);}
@media(max-width:640px){.nav-links{display:none;}.hamburger{display:flex;}}

/* === HERO === */
.hero{padding-block:clamp(var(--space-16),10vw,var(--space-20)) clamp(var(--space-12),6vw,var(--space-16));position:relative;overflow:hidden;}
.hero::before{content:"";position:absolute;inset:0;background:radial-gradient(ellipse 80% 60% at 50% -10%,oklch(0.6 0.15 225/0.10),transparent);pointer-events:none;}
.hero-eyebrow{font-family:var(--font-mono);font-size:var(--text-xs);color:var(--color-primary);letter-spacing:.12em;text-transform:uppercase;margin-bottom:var(--space-4);}
.hero h1{font-family:var(--font-display);font-size:var(--text-hero);font-weight:800;line-height:1.05;letter-spacing:-.04em;margin-bottom:var(--space-5);}
.hero h1 .accent{color:var(--color-primary);}
.hero-desc{font-size:var(--text-lg);color:var(--color-text-muted);max-width:56ch;margin-bottom:var(--space-8);line-height:1.55;}
.hero-badges{display:flex;flex-wrap:wrap;gap:var(--space-3);margin-bottom:var(--space-8);}
.badge{display:inline-flex;align-items:center;gap:var(--space-2);padding:var(--space-2) var(--space-3);background:var(--color-surface);border:1px solid var(--color-border);border-radius:var(--radius-full);font-size:var(--text-xs);font-weight:500;white-space:nowrap;}
.badge-trophy{background:oklch(0.75 0.12 80/0.15);border-color:oklch(0.7 0.12 80/0.3);color:var(--color-text);}
.hero-ctas{display:flex;flex-wrap:wrap;gap:var(--space-3);}
.btn{display:inline-flex;align-items:center;gap:var(--space-2);padding:var(--space-3) var(--space-5);border-radius:var(--radius-md);font-size:var(--text-sm);font-weight:600;transition:all var(--transition);}
.btn-primary{background:var(--color-primary);color:#fff;}
.btn-primary:hover{background:var(--color-primary-hover);color:#fff;box-shadow:var(--shadow-md);}
.btn-ghost{border:1px solid var(--color-border);color:var(--color-text-muted);}
.btn-ghost:hover{border-color:var(--color-primary);color:var(--color-primary);background:var(--color-primary-hl);}
.scroll-hint{position:absolute;bottom:var(--space-6);left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:var(--space-2);color:var(--color-text-faint);font-size:var(--text-xs);}
.scroll-hint svg{animation:bounce 2s ease-in-out infinite;}
@keyframes bounce{0%,100%{transform:translateY(0);}50%{transform:translateY(5px);}}

/* === SECTION HEADERS === */
.section-label{font-family:var(--font-mono);font-size:var(--text-xs);color:var(--color-primary);letter-spacing:.12em;text-transform:uppercase;margin-bottom:var(--space-3);}
.section-title{font-family:var(--font-display);font-size:var(--text-xl);font-weight:800;letter-spacing:-.02em;margin-bottom:var(--space-2);}
.section-sub{font-size:var(--text-base);color:var(--color-text-muted);max-width:52ch;margin-bottom:var(--space-10);}
.divider{height:1px;background:var(--color-divider);margin-block:var(--space-2);}

/* === ACHIEVEMENTS === */
.achievements-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(min(280px,100%),1fr));gap:var(--space-4);}
.achievement-card{background:var(--color-surface);border:1px solid var(--color-border);border-radius:var(--radius-lg);padding:var(--space-5) var(--space-6);box-shadow:var(--shadow-sm);transition:box-shadow var(--transition),border-color var(--transition);}
.achievement-card:hover{box-shadow:var(--shadow-md);border-color:var(--color-primary);}
.achievement-icon{font-size:1.6rem;margin-bottom:var(--space-3);}
.achievement-card h3{font-family:var(--font-display);font-size:var(--text-base);font-weight:700;margin-bottom:var(--space-1);}
.achievement-card p{font-size:var(--text-sm);color:var(--color-text-muted);}

/* === SKILLS === */
.skills-layout{display:grid;grid-template-columns:1fr 1fr 1fr;gap:var(--space-6);}
@media(max-width:768px){.skills-layout{grid-template-columns:1fr 1fr;}}
@media(max-width:480px){.skills-layout{grid-template-columns:1fr;}}
.skill-group{background:var(--color-surface);border:1px solid var(--color-border);border-radius:var(--radius-lg);padding:var(--space-5) var(--space-6);}
.skill-group-title{font-family:var(--font-mono);font-size:var(--text-xs);color:var(--color-primary);letter-spacing:.1em;text-transform:uppercase;margin-bottom:var(--space-4);}
.skill-tags{display:flex;flex-wrap:wrap;gap:var(--space-2);}
.skill-tag{padding:var(--space-1) var(--space-3);background:var(--color-bg);border:1px solid var(--color-border);border-radius:var(--radius-full);font-size:var(--text-xs);font-weight:500;transition:all var(--transition);}
.skill-tag:hover{border-color:var(--color-primary);color:var(--color-primary);}
.skill-tag.featured{background:var(--color-primary-hl);border-color:oklch(0.6 0.15 225/0.3);color:var(--color-primary);}

/* === PROJECTS === */
.projects-grid{display:grid;grid-template-columns:1fr 1fr;gap:var(--space-5);}
@media(max-width:700px){.projects-grid{grid-template-columns:1fr;}}
.project-card{background:var(--color-surface);border:1px solid var(--color-border);border-radius:var(--radius-xl);padding:var(--space-6);box-shadow:var(--shadow-sm);transition:all var(--transition);position:relative;}
.project-card:hover{box-shadow:var(--shadow-lg);border-color:var(--color-primary);transform:translateY(-2px);}
.project-card.featured{grid-column:1/-1;display:grid;grid-template-columns:1fr 1fr;gap:var(--space-8);align-items:center;}
@media(max-width:700px){.project-card.featured{grid-column:auto;grid-template-columns:1fr;}}
.project-icon{font-size:2rem;margin-bottom:var(--space-4);}
.project-trophy{position:absolute;top:var(--space-4);right:var(--space-4);font-size:1.2rem;}
.project-card h3{font-family:var(--font-display);font-size:var(--text-lg);font-weight:700;margin-bottom:var(--space-2);}
.project-card p{font-size:var(--text-sm);color:var(--color-text-muted);max-width:52ch;margin-bottom:var(--space-4);line-height:1.55;}
.project-stack{display:flex;flex-wrap:wrap;gap:var(--space-2);margin-bottom:var(--space-5);}
.stack-tag{padding:2px var(--space-2);background:var(--color-surface-2);border:1px solid var(--color-border);border-radius:var(--radius-sm);font-size:var(--text-xs);font-family:var(--font-mono);color:var(--color-text-muted);}
.project-links{display:flex;gap:var(--space-3);align-items:center;}
.project-link{display:inline-flex;align-items:center;gap:var(--space-1);font-size:var(--text-xs);color:var(--color-text-muted);transition:color var(--transition);}
.project-link:hover{color:var(--color-primary);}
.project-stat{font-size:var(--text-xs);color:var(--color-text-faint);}
.featured-visual{background:linear-gradient(135deg,var(--color-primary-hl),oklch(0.6 0.12 200/0.08));border-radius:var(--radius-lg);aspect-ratio:4/3;display:flex;align-items:center;justify-content:center;font-size:4rem;border:1px solid var(--color-border);}

/* === CONTACT === */
.contact-layout{display:grid;grid-template-columns:1fr 1fr;gap:var(--space-12);align-items:start;}
@media(max-width:700px){.contact-layout{grid-template-columns:1fr;}}
.contact-links{display:flex;flex-direction:column;gap:var(--space-3);}
.contact-link{display:flex;align-items:center;gap:var(--space-4);padding:var(--space-4) var(--space-5);background:var(--color-surface);border:1px solid var(--color-border);border-radius:var(--radius-lg);transition:all var(--transition);color:var(--color-text);}
.contact-link:hover{border-color:var(--color-primary);box-shadow:var(--shadow-md);background:var(--color-surface-2);}
.contact-link-icon{width:2.5rem;height:2.5rem;display:flex;align-items:center;justify-content:center;border-radius:var(--radius-md);background:var(--color-primary-hl);color:var(--color-primary);flex-shrink:0;}
.contact-link-text{font-size:var(--text-sm);font-weight:500;}
.contact-link-sub{font-size:var(--text-xs);color:var(--color-text-muted);}
.edu-card{background:var(--color-surface);border:1px solid var(--color-border);border-radius:var(--radius-lg);padding:var(--space-6);}
.edu-card h3{font-family:var(--font-display);font-size:var(--text-lg);font-weight:700;margin-bottom:var(--space-1);}
.edu-card p{font-size:var(--text-sm);color:var(--color-text-muted);}

/* === FOOTER === */
footer{border-top:1px solid var(--color-border);padding-block:var(--space-8);text-align:center;color:var(--color-text-faint);font-size:var(--text-xs);}
footer a{color:var(--color-text-faint);}footer a:hover{color:var(--color-primary);}

/* === STATS SCROLL MARQUEE === */
.stats-bar{background:var(--color-surface);border-block:1px solid var(--color-border);overflow:hidden;padding-block:var(--space-3);}
.stats-marquee{display:flex;gap:var(--space-12);animation:marquee 20s linear infinite;white-space:nowrap;width:max-content;}
.stats-marquee:hover{animation-play-state:paused;}
.stat-item{display:flex;align-items:center;gap:var(--space-3);font-size:var(--text-sm);}
.stat-item span.num{font-family:var(--font-display);font-weight:700;color:var(--color-primary);}
@keyframes marquee{from{transform:translateX(0);}to{transform:translateX(-50%);}}

/* === SCROLL REVEAL === */
.reveal{opacity:0;transform:translateY(18px);transition:opacity 0.55s cubic-bezier(0.16,1,0.3,1),transform 0.55s cubic-bezier(0.16,1,0.3,1);}
.reveal.visible{opacity:1;transform:translateY(0);}
@media(prefers-reduced-motion:reduce){.reveal{opacity:1;transform:none;}}
</style>
</head>
<body>

<!-- NAV -->
<nav aria-label="Main navigation">
  <div class="nav-inner">
    <a href="#" class="nav-logo">YJ<span>.</span></a>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <div class="nav-actions">
      <button id="theme-toggle" aria-label="Switch to light mode" title="Toggle theme">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/></svg>
      </button>
      <button class="hamburger" aria-label="Menu">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="3" y1="6" x2="21" y2="6"/><line x1="3" y1="12" x2="21" y2="12"/><line x1="3" y1="18" x2="21" y2="18"/></svg>
      </button>
    </div>
  </div>
</nav>

<!-- HERO -->
<section class="hero" id="about">
  <div class="container--narrow">
    <p class="hero-eyebrow">Flutter &bull; Android &bull; AI Builder &bull; CS Student</p>
    <h1>Yash<br><span class="accent">Jain.</span></h1>
    <p class="hero-desc">Building production-ready mobile experiences with Flutter & Android — from civic AI platforms to logistics apps. Currently pursuing B.Tech + M.Tech in CSE at NIMS University (2022&ndash;2027).</p>
    <div class="hero-badges">
      <span class="badge badge-trophy">🏆 Hack2Skill PromptWars 2026 Winner</span>
      <span class="badge badge-trophy">🏅 Intern of the Month — UptoSkills</span>
      <span class="badge badge-trophy">🥉 9th Place — National Ideathon 2.0</span>
    </div>
    <div class="hero-ctas">
      <a href="https://yashjain-portfolio-dev.netlify.app" class="btn btn-primary" target="_blank" rel="noopener noreferrer">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
        View Portfolio
      </a>
      <a href="https://github.com/Yashjain329" class="btn btn-ghost" target="_blank" rel="noopener noreferrer">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.6.11.82-.26.82-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.73.083-.73 1.205.085 1.84 1.238 1.84 1.238 1.07 1.834 2.807 1.305 3.492.998.108-.775.418-1.305.762-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23A11.52 11.52 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.29-1.552 3.297-1.23 3.297-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22v3.293c0 .319.21.694.825.576C20.565 21.796 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
        GitHub
      </a>
      <a href="mailto:Yashjain9350@gmail.com" class="btn btn-ghost">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
        Email
      </a>
    </div>
  </div>
  <div class="scroll-hint" aria-hidden="true">
    <span>scroll</span>
    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="6 9 12 15 18 9"/></svg>
  </div>
</section>

<!-- STATS BAR -->
<div class="stats-bar" aria-label="Quick stats">
  <div class="stats-marquee" aria-hidden="true">
    <div class="stat-item"><span class="num">10+</span> Projects Built</div>
    <div class="stat-item"><span class="num">3</span> Hackathon Awards</div>
    <div class="stat-item"><span class="num">15–20</span> Devs Led</div>
    <div class="stat-item"><span class="num">Flutter</span> Primary Stack</div>
    <div class="stat-item"><span class="num">Kotlin</span> Android Native</div>
    <div class="stat-item"><span class="num">Firebase</span> Backend</div>
    <div class="stat-item"><span class="num">Supabase</span> Cloud</div>
    <div class="stat-item"><span class="num">GCP</span> Infrastructure</div>
    <!-- duplicate for seamless loop -->
    <div class="stat-item"><span class="num">10+</span> Projects Built</div>
    <div class="stat-item"><span class="num">3</span> Hackathon Awards</div>
    <div class="stat-item"><span class="num">15–20</span> Devs Led</div>
    <div class="stat-item"><span class="num">Flutter</span> Primary Stack</div>
    <div class="stat-item"><span class="num">Kotlin</span> Android Native</div>
    <div class="stat-item"><span class="num">Firebase</span> Backend</div>
    <div class="stat-item"><span class="num">Supabase</span> Cloud</div>
    <div class="stat-item"><span class="num">GCP</span> Infrastructure</div>
  </div>
</div>

<!-- ACHIEVEMENTS -->
<section id="achievements">
  <div class="container">
    <div class="reveal">
      <p class="section-label">Recognition</p>
      <h2 class="section-title">Achievements</h2>
      <p class="section-sub">Awards and recognition from hackathons, internships, and competitions.</p>
    </div>
    <div class="achievements-grid">
      <div class="achievement-card reveal">
        <div class="achievement-icon">🏆</div>
        <h3>Hack2Skill PromptWars 2026</h3>
        <p>Winner — Built <em>ElectWise</em>, an AI-powered civic education platform for Indian elections.</p>
      </div>
      <div class="achievement-card reveal">
        <div class="achievement-icon">🏅</div>
        <h3>Intern of the Month — UptoSkills</h3>
        <p>Recognised as Flutter Developer intern while leading a team of 15–20 developers.</p>
      </div>
      <div class="achievement-card reveal">
        <div class="achievement-icon">🥉</div>
        <h3>9th Place — National Ideathon 2.0</h3>
        <p>Competed nationally as part of Team GRUBOX with an innovative product concept.</p>
      </div>
      <div class="achievement-card reveal">
        <div class="achievement-icon">🎓</div>
        <h3>B.Tech + M.Tech (Int.) CSE</h3>
        <p>NIMS University, 2022–2027. Dual degree in Computer Science &amp; Engineering.</p>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills" style="background:var(--color-surface);border-block:1px solid var(--color-border);">
  <div class="container">
    <div class="reveal">
      <p class="section-label">Expertise</p>
      <h2 class="section-title">Skills &amp; Stack</h2>
      <p class="section-sub">Languages, frameworks, tools, and platforms I work with daily.</p>
    </div>
    <div class="skills-layout">
      <div class="skill-group reveal">
        <div class="skill-group-title">// Languages</div>
        <div class="skill-tags">
          <span class="skill-tag featured">Dart</span>
          <span class="skill-tag featured">Kotlin</span>
          <span class="skill-tag">Swift</span>
          <span class="skill-tag">Java</span>
          <span class="skill-tag">Python</span>
          <span class="skill-tag">TypeScript</span>
          <span class="skill-tag">HTML5</span>
          <span class="skill-tag">CSS3</span>
        </div>
      </div>
      <div class="skill-group reveal">
        <div class="skill-group-title">// Frameworks &amp; Tools</div>
        <div class="skill-tags">
          <span class="skill-tag featured">Flutter</span>
          <span class="skill-tag featured">Jetpack Compose</span>
          <span class="skill-tag">React 19</span>
          <span class="skill-tag">Android Studio</span>
          <span class="skill-tag">Firebase</span>
          <span class="skill-tag">Supabase</span>
          <span class="skill-tag">Docker</span>
        </div>
      </div>
      <div class="skill-group reveal">
        <div class="skill-group-title">// Databases &amp; Cloud</div>
        <div class="skill-tags">
          <span class="skill-tag featured">PostgreSQL</span>
          <span class="skill-tag">MySQL</span>
          <span class="skill-tag">Room DB</span>
          <span class="skill-tag">GCP</span>
          <span class="skill-tag">Cloud Run</span>
          <span class="skill-tag">Gemini AI</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="container">
    <div class="reveal">
      <p class="section-label">Work</p>
      <h2 class="section-title">Featured Projects</h2>
      <p class="section-sub">Production apps, hackathon winners, and open-source experiments.</p>
    </div>
    <div class="projects-grid">

      <!-- ElectWise — featured -->
      <div class="project-card featured reveal">
        <div>
          <div class="project-icon">⚡</div>
          <span class="project-trophy">🏆</span>
          <h3>ElectWise</h3>
          <p>AI-powered Civic Education Platform for Indian Elections. Built with React 19, Firebase, and Gemini AI — winner of Hack2Skill PromptWars 2026.</p>
          <div class="project-stack">
            <span class="stack-tag">React 19</span>
            <span class="stack-tag">Firebase</span>
            <span class="stack-tag">Gemini AI</span>
          </div>
          <div class="project-links">
            <a href="https://github.com/Yashjain329/electwise" class="project-link" target="_blank" rel="noopener noreferrer">
              <svg width="13" height="13" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.6.11.82-.26.82-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.73.083-.73 1.205.085 1.84 1.238 1.84 1.238 1.07 1.834 2.807 1.305 3.492.998.108-.775.418-1.305.762-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23A11.52 11.52 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.29-1.552 3.297-1.23 3.297-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22v3.293c0 .319.21.694.825.576C20.565 21.796 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
              View Source
            </a>
          </div>
        </div>
        <div class="featured-visual" aria-hidden="true">
          <span style="font-size:5rem;">🗳️</span>
        </div>
      </div>

      <!-- MediMind AI -->
      <div class="project-card reveal">
        <div class="project-icon">🏥</div>
        <h3>MediMind AI</h3>
        <p>AI-driven healthcare platform streamlining doctor–patient interactions with smart assistants.</p>
        <div class="project-stack">
          <span class="stack-tag">TypeScript</span>
          <span class="stack-tag">Firebase</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Yashjain329/Medimind_AI" class="project-link" target="_blank" rel="noopener noreferrer">GitHub →</a>
        </div>
      </div>

      <!-- Truck Singh -->
      <div class="project-card reveal">
        <div class="project-icon">🚛</div>
        <h3>Truck Singh</h3>
        <p>Logistics &amp; freight scheduling app built in Flutter. ⭐ 2 · 🍴 6</p>
        <div class="project-stack">
          <span class="stack-tag">Flutter</span>
          <span class="stack-tag">Dart</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Yashjain329/truck_singh" class="project-link" target="_blank" rel="noopener noreferrer">GitHub →</a>
        </div>
      </div>

      <!-- ImgShape -->
      <div class="project-card reveal">
        <div class="project-icon">🖼️</div>
        <h3>ImgShape</h3>
        <p>Image upload, deep AI analysis &amp; downloadable insights powered by Supabase. ⭐ 1 · 🍴 2</p>
        <div class="project-stack">
          <span class="stack-tag">Flutter</span>
          <span class="stack-tag">Supabase</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Yashjain329/imgshape" class="project-link" target="_blank" rel="noopener noreferrer">GitHub →</a>
        </div>
      </div>

      <!-- FinTrackr -->
      <div class="project-card reveal">
        <div class="project-icon">💰</div>
        <h3>FinTrackr</h3>
        <p>Personal finance tracker — transactions, spending patterns &amp; savings goals. ⭐ 1</p>
        <div class="project-stack">
          <span class="stack-tag">Flutter</span>
          <span class="stack-tag">Dart</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Yashjain329/fintrackr" class="project-link" target="_blank" rel="noopener noreferrer">GitHub →</a>
        </div>
      </div>

      <!-- StatGenie -->
      <div class="project-card reveal">
        <div class="project-icon">📊</div>
        <h3>StatGenie</h3>
        <p>Upload datasets, generate interactive charts &amp; AI insights. ⭐ 1</p>
        <div class="project-stack">
          <span class="stack-tag">Flutter</span>
          <span class="stack-tag">Supabase</span>
          <span class="stack-tag">PostgreSQL</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Yashjain329/statgenie" class="project-link" target="_blank" rel="noopener noreferrer">GitHub →</a>
        </div>
      </div>

      <!-- Shadow Talk -->
      <div class="project-card reveal">
        <div class="project-icon">💬</div>
        <h3>Shadow Talk</h3>
        <p>Real-time cross-platform chat application built with Flutter &amp; Supabase. ⭐ 1</p>
        <div class="project-stack">
          <span class="stack-tag">Flutter</span>
          <span class="stack-tag">Supabase</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Yashjain329/Shadow_Talk" class="project-link" target="_blank" rel="noopener noreferrer">GitHub →</a>
        </div>
      </div>

      <!-- AnimeExplorer Android -->
      <div class="project-card reveal">
        <div class="project-icon">🎌</div>
        <h3>AnimeExplorer (Android)</h3>
        <p>Modern anime browser using Jetpack Compose, MVVM architecture &amp; Jikan API.</p>
        <div class="project-stack">
          <span class="stack-tag">Kotlin</span>
          <span class="stack-tag">Jetpack Compose</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Yashjain329/AnimeExplorer" class="project-link" target="_blank" rel="noopener noreferrer">GitHub →</a>
        </div>
      </div>

      <!-- AnimeExplorer iOS -->
      <div class="project-card reveal">
        <div class="project-icon">🍎</div>
        <h3>AnimeExplorer (iOS)</h3>
        <p>iOS version of AnimeExplorer in Swift, built for the Meetmux Placement Drive.</p>
        <div class="project-stack">
          <span class="stack-tag">Swift</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Yashjain329/AnimeExplorer-IOS-" class="project-link" target="_blank" rel="noopener noreferrer">GitHub →</a>
        </div>
      </div>

      <!-- Billboard Detector -->
      <div class="project-card reveal">
        <div class="project-icon">📸</div>
        <h3>Billboard Detector</h3>
        <p>Flutter app to detect &amp; analyze billboards using image processing. ⭐ 2</p>
        <div class="project-stack">
          <span class="stack-tag">Flutter</span>
          <span class="stack-tag">Dart</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Yashjain329/billboard_detector" class="project-link" target="_blank" rel="noopener noreferrer">GitHub →</a>
        </div>
      </div>

      <!-- Sensor Explorer -->
      <div class="project-card reveal">
        <div class="project-icon">🔬</div>
        <h3>Sensor Explorer</h3>
        <p>Android app to explore &amp; visualize smartphone sensors in real time. ⭐ 2</p>
        <div class="project-stack">
          <span class="stack-tag">Java</span>
          <span class="stack-tag">Android</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Yashjain329/Sensor-Explorer" class="project-link" target="_blank" rel="noopener noreferrer">GitHub →</a>
        </div>
      </div>

      <!-- AI Web Agent -->
      <div class="project-card reveal">
        <div class="project-icon">🤖</div>
        <h3>AI Web Agent</h3>
        <p>Locally running AI agent that autonomously browses, searches, and fills forms via NLP.</p>
        <div class="project-stack">
          <span class="stack-tag">Python</span>
        </div>
        <div class="project-links">
          <a href="https://github.com/Yashjain329/ai-web-agent" class="project-link" target="_blank" rel="noopener noreferrer">GitHub →</a>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact" style="background:var(--color-surface);border-top:1px solid var(--color-border);">
  <div class="container">
    <div class="reveal">
      <p class="section-label">Say Hello</p>
      <h2 class="section-title">Get In Touch</h2>
      <p class="section-sub">Open for freelance projects, internships, and interesting collaborations.</p>
    </div>
    <div class="contact-layout">
      <div class="contact-links">
        <a href="https://www.linkedin.com/in/yash-jain329/" class="contact-link reveal" target="_blank" rel="noopener noreferrer">
          <div class="contact-link-icon">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
          </div>
          <div>
            <div class="contact-link-text">LinkedIn</div>
            <div class="contact-link-sub">linkedin.com/in/yash-jain329</div>
          </div>
        </a>
        <a href="mailto:Yashjain9350@gmail.com" class="contact-link reveal">
          <div class="contact-link-icon">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
          </div>
          <div>
            <div class="contact-link-text">Email</div>
            <div class="contact-link-sub">Yashjain9350@gmail.com</div>
          </div>
        </a>
        <a href="https://github.com/Yashjain329" class="contact-link reveal" target="_blank" rel="noopener noreferrer">
          <div class="contact-link-icon">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.6.11.82-.26.82-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.73.083-.73 1.205.085 1.84 1.238 1.84 1.238 1.07 1.834 2.807 1.305 3.492.998.108-.775.418-1.305.762-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23A11.52 11.52 0 0 1 12 5.803c1.02.005 2.047.138 3.006.404 2.29-1.552 3.297-1.23 3.297-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22v3.293c0 .319.21.694.825.576C20.565 21.796 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
          </div>
          <div>
            <div class="contact-link-text">GitHub</div>
            <div class="contact-link-sub">github.com/Yashjain329</div>
          </div>
        </a>
        <a href="https://yashjain-portfolio-dev.netlify.app" class="contact-link reveal" target="_blank" rel="noopener noreferrer">
          <div class="contact-link-icon">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg>
          </div>
          <div>
            <div class="contact-link-text">Portfolio</div>
            <div class="contact-link-sub">yashjain-portfolio-dev.netlify.app</div>
          </div>
        </a>
      </div>
      <div class="edu-card reveal">
        <h3>🎓 Education</h3>
        <div style="height:var(--space-4)"></div>
        <p style="font-size:var(--text-sm);font-weight:600;margin-bottom:var(--space-1);">B.Tech + M.Tech (Integrated) in CSE</p>
        <p>NIMS University &nbsp;·&nbsp; 2022 – 2027</p>
        <div style="height:var(--space-6)"></div>
        <p class="section-label" style="margin-bottom:var(--space-3);">Currently Exploring</p>
        <div class="skill-tags">
          <span class="skill-tag">AI Integration</span>
          <span class="skill-tag">Cloud Backends</span>
          <span class="skill-tag">Flutter 3.x</span>
          <span class="skill-tag">Material 3</span>
          <span class="skill-tag">Coroutines</span>
        </div>
      </div>
    </div>
  </div>
</section>

<footer>
  <p>Built with care &nbsp;&bull;&nbsp; <a href="https://github.com/Yashjain329" target="_blank" rel="noopener noreferrer">@Yashjain329</a> &nbsp;&bull;&nbsp; 2025</p>
</footer>

<script>
// Theme toggle
(function(){
  var btn=document.getElementById('theme-toggle');
  var html=document.documentElement;
  var isDark=html.getAttribute('data-theme')==='dark';
  function setIcon(dark){
    btn.innerHTML=dark
      ?'<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/></svg>'
      :'<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="5"/><path d="M12 1v2M12 21v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M1 12h2M21 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"/></svg>';
    btn.setAttribute('aria-label','Switch to '+(dark?'light':'dark')+' mode');
  }
  setIcon(isDark);
  btn.addEventListener('click',function(){
    isDark=!isDark;
    html.setAttribute('data-theme',isDark?'dark':'light');
    setIcon(isDark);
  });
})();

// Scroll reveal
(function(){
  var els=document.querySelectorAll('.reveal');
  var io=new IntersectionObserver(function(entries){
    entries.forEach(function(e){
      if(e.isIntersecting){e.target.classList.add('visible');io.unobserve(e.target);}
    });
  },{threshold:0.1,rootMargin:'0px 0px -40px 0px'});
  els.forEach(function(el){io.observe(el);});
})();
</script>
</body>
</html>
