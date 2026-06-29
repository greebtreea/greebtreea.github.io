<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>최민혁 | 포트폴리오</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --primary: #0E4A84;
    --primary-light: #1a6ab8;
    --primary-ultra: #e8f0fb;
    --text: #1a1a2e;
    --text-sub: #555577;
    --text-muted: #888;
    --bg: #ffffff;
    --bg-alt: #f7f9fc;
    --border: #e2e8f0;
    --empty: #d0d8e4;
    --radius: 12px;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body { font-family: 'Inter', sans-serif; color: var(--text); background: var(--bg); line-height: 1.7; }

  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    background: rgba(255,255,255,0.92); backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 5%; height: 64px;
  }
  .nav-logo { font-weight: 700; font-size: 18px; color: var(--primary); letter-spacing: -0.5px; }
  .nav-links { display: flex; gap: 32px; list-style: none; }
  .nav-links a { text-decoration: none; color: var(--text-sub); font-size: 14px; font-weight: 500; transition: color 0.2s; }
  .nav-links a:hover { color: var(--primary); }

  section { padding: 100px 10%; }
  section:nth-child(even) { background: var(--bg-alt); }

  #hero {
    min-height: 100vh; display: flex; align-items: center;
    padding-top: 64px; background: linear-gradient(135deg, #f0f6ff 0%, #ffffff 60%);
  }
  .hero-inner { max-width: 800px; }
  .hero-badge {
    display: inline-block; background: var(--primary-ultra); color: var(--primary);
    font-size: 13px; font-weight: 600; padding: 6px 14px; border-radius: 20px;
    margin-bottom: 24px;
  }
  .hero-inner h1 { font-size: clamp(36px, 5vw, 60px); font-weight: 700; line-height: 1.15; letter-spacing: -1.5px; margin-bottom: 16px; }
  .hero-inner h1 span { color: var(--primary); }
  .hero-sub { font-size: 18px; color: var(--text-sub); margin-bottom: 36px; max-width: 560px; }
  .hero-btns { display: flex; gap: 14px; flex-wrap: wrap; }
  .btn-primary {
    background: var(--primary); color: #fff; padding: 13px 28px; border-radius: 8px;
    font-weight: 600; font-size: 15px; text-decoration: none; transition: background 0.2s, transform 0.15s;
  }
  .btn-primary:hover { background: var(--primary-light); transform: translateY(-1px); }
  .btn-outline {
    border: 1.5px solid var(--primary); color: var(--primary); padding: 12px 28px; border-radius: 8px;
    font-weight: 600; font-size: 15px; text-decoration: none; transition: background 0.2s;
  }
  .btn-outline:hover { background: var(--primary-ultra); }

  .sec-label { color: var(--primary); font-size: 13px; font-weight: 600; letter-spacing: 1.5px; text-transform: uppercase; margin-bottom: 10px; }
  .sec-title { font-size: clamp(26px, 3.5vw, 38px); font-weight: 700; letter-spacing: -0.8px; margin-bottom: 14px; }
  .sec-divider { width: 48px; height: 3px; background: var(--primary); border-radius: 2px; margin: 14px 0 48px; }

  /* 공란 표시 */
  .empty-block {
    background: var(--bg-alt); border: 1.5px dashed var(--empty);
    border-radius: 8px; padding: 14px 18px;
    color: var(--text-muted); font-size: 14px; font-style: italic;
  }
  .empty-inline {
    color: var(--empty); font-style: italic; font-size: 14px;
  }

  .about-grid { display: grid; grid-template-columns: 1fr 1.6fr; gap: 64px; align-items: center; }
  .about-avatar-wrap { text-align: center; }
  .about-avatar {
    width: 200px; height: 200px; border-radius: 50%; background: var(--primary-ultra);
    border: 4px solid var(--primary); margin: 0 auto 20px; display: flex;
    align-items: center; justify-content: center; font-size: 64px; font-weight: 700; color: var(--primary);
  }
  .about-avatar-name { font-weight: 600; color: var(--text); }
  .about-avatar-role { font-size: 14px; color: var(--text-sub); margin-top: 4px; }
  .about-text p { color: var(--text-sub); font-size: 16px; margin-bottom: 16px; }
  .about-tags { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 24px; }
  .tag { background: var(--primary-ultra); color: var(--primary); font-size: 13px; font-weight: 500; padding: 5px 13px; border-radius: 20px; }

  .cards-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 24px; }
  .card {
    background: var(--bg); border: 1px solid var(--border); border-radius: var(--radius);
    padding: 28px; transition: box-shadow 0.2s, transform 0.2s;
  }
  .card:hover { box-shadow: 0 8px 32px rgba(14,74,132,0.10); transform: translateY(-3px); }
  .card h3 { font-size: 17px; font-weight: 600; margin-bottom: 10px; }
  .card p { font-size: 14px; color: var(--text-sub); line-height: 1.6; margin-bottom: 16px; }
  .card-tags { display: flex; flex-wrap: wrap; gap: 6px; }
  .card-tag { background: var(--primary-ultra); color: var(--primary); font-size: 11px; font-weight: 600; padding: 3px 10px; border-radius: 12px; }

  .pub-list { display: flex; flex-direction: column; gap: 20px; }
  .pub-item {
    background: var(--bg); border: 1px solid var(--border); border-radius: var(--radius);
    padding: 24px 28px; display: flex; gap: 20px; align-items: flex-start;
  }
  .pub-year { color: var(--primary); font-weight: 700; font-size: 14px; min-width: 44px; padding-top: 3px; }
  .pub-body h4 { font-size: 16px; font-weight: 600; margin-bottom: 6px; }
  .pub-body p { font-size: 14px; color: var(--text-sub); margin-bottom: 10px; }
  .pub-venue { display: inline-block; background: var(--primary-ultra); color: var(--primary); font-size: 12px; font-weight: 600; padding: 3px 10px; border-radius: 10px; }

  .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 24px; }
  .skill-group { background: var(--bg); border: 1px solid var(--border); border-radius: var(--radius); padding: 24px; }
  .skill-group h4 { font-size: 14px; font-weight: 700; color: var(--primary); text-transform: uppercase; letter-spacing: 1px; margin-bottom: 16px; }
  .skill-item { display: flex; align-items: center; justify-content: space-between; margin-bottom: 12px; }
  .skill-item span { font-size: 14px; color: var(--text-sub); }
  .skill-bar { width: 120px; height: 5px; background: var(--border); border-radius: 4px; overflow: hidden; }
  .skill-fill { height: 100%; background: var(--primary); border-radius: 4px; }

  .contact-inner { max-width: 680px; margin: 0 auto; text-align: center; }
  .contact-links { display: flex; justify-content: center; gap: 16px; flex-wrap: wrap; margin-top: 40px; }
  .contact-link {
    display: flex; align-items: center; gap: 8px;
    border: 1.5px solid var(--border); border-radius: 8px; padding: 12px 24px;
    text-decoration: none; color: var(--text); font-size: 15px; font-weight: 500;
    transition: border-color 0.2s, color 0.2s, background 0.2s;
  }
  .contact-link:hover { border-color: var(--primary); color: var(--primary); background: var(--primary-ultra); }
  .contact-link svg { width: 18px; height: 18px; }

  footer { text-align: center; padding: 32px; font-size: 13px; color: var(--text-muted); border-top: 1px solid var(--border); }

  .fade-in { opacity: 0; transform: translateY(24px); transition: opacity 0.6s ease, transform 0.6s ease; }
  .fade-in.visible { opacity: 1; transform: none; }

  @media (max-width: 700px) {
    section { padding: 80px 6%; }
    .about-grid { grid-template-columns: 1fr; gap: 36px; }
    nav { padding: 0 4%; }
    .nav-links { gap: 18px; }
  }
</style>
</head>
<body>

<nav>
  <div class="nav-logo">Minhyeok Choi</div>
  <ul class="nav-links">
    <li><a href="#about">소개</a></li>
    <li><a href="#research">연구</a></li>
    <li><a href="#publications">논문</a></li>
    <li><a href="#skills">기술</a></li>
    <li><a href="#contact">연락처</a></li>
  </ul>
</nav>

<section id="hero">
  <div class="hero-inner fade-in">
    <div class="hero-badge">학부연구생 · 기계공학과 · IDEA LAB</div>
    <h1>안녕하세요,<br><span>최민혁</span>입니다.</h1>
    <p class="hero-sub">한양대학교 ERICA 캠퍼스 기계공학과 학부연구생 · IDEA LAB</p>
    <div class="hero-btns">
      <a href="#research" class="btn-primary">연구 보기</a>
      <a href="#contact" class="btn-outline">연락하기</a>
    </div>
  </div>
</section>

<section id="about">
  <div class="about-grid">
    <div class="about-avatar-wrap fade-in">
      <div class="about-avatar">최</div>
      <div class="about-avatar-name">최민혁 · Minhyeok Choi</div>
      <div class="about-avatar-role">학부연구생 · 기계공학과 · IDEA LAB</div>
    </div>
    <div class="about-text fade-in">
      <div class="sec-label">About Me</div>
      <h2 class="sec-title">연구자 소개</h2>
      <div class="sec-divider"></div>
      <div class="empty-block">자기소개는 업데이트 예정입니다.</div>
      <div class="about-tags" style="margin-top:24px;">
        <span class="tag">방산</span>
      </div>
    </div>
  </div>
</section>

<section id="research">
  <div class="fade-in">
    <div class="sec-label">Research</div>
    <h2 class="sec-title">연구 및 프로젝트</h2>
    <div class="sec-divider"></div>
  </div>
  <div class="cards-grid">
    <div class="card fade-in" style="border: 1.5px dashed var(--empty);">
      <h3 class="empty-inline">업데이트 예정입니다.</h3>
      <p class="empty-inline" style="display:block; margin: 12px 0 16px;">프로젝트 설명은 업데이트 예정입니다.</p>
      <div class="card-tags"><span style="font-size:12px; color:var(--empty); font-style:italic;">기술 태그 업데이트 예정</span></div>
    </div>
    <div class="card fade-in" style="border: 1.5px dashed var(--empty);">
      <h3 class="empty-inline">업데이트 예정입니다.</h3>
      <p class="empty-inline" style="display:block; margin: 12px 0 16px;">프로젝트 설명은 업데이트 예정입니다.</p>
      <div class="card-tags"><span style="font-size:12px; color:var(--empty); font-style:italic;">기술 태그 업데이트 예정</span></div>
    </div>
  </div>
</section>

<section id="publications">
  <div class="fade-in">
    <div class="sec-label">Publications</div>
    <h2 class="sec-title">논문 및 발표</h2>
    <div class="sec-divider"></div>
  </div>
  <div class="pub-list">
    <div class="pub-item fade-in" style="border: 1.5px dashed var(--empty); background: var(--bg-alt);">
      <div class="pub-year empty-inline">업데이트 예정</div>
      <div class="pub-body">
        <h4 class="empty-inline">논문 및 발표는 업데이트 예정입니다.</h4>
        <p class="empty-inline" style="display:block; margin: 8px 0;">저자 업데이트 예정</p>
        <span class="pub-venue" style="background: var(--bg-alt); color: var(--empty); border: 1px dashed var(--empty);">학회 / 저널명 업데이트 예정</span>
      </div>
    </div>
  </div>
</section>

<section id="skills">
  <div class="fade-in">
    <div class="sec-label">Skills</div>
    <h2 class="sec-title">기술 스택</h2>
    <div class="sec-divider"></div>
  </div>
  <div class="empty-block fade-in">기술 스택은 업데이트 예정입니다.</div>
</section>

<section id="contact">
  <div class="contact-inner">
    <div class="sec-label fade-in">Contact</div>
    <h2 class="sec-title fade-in">연락하기</h2>
    <div class="sec-divider" style="margin: 14px auto 24px; display:block; width:48px; height:3px; background:var(--primary); border-radius:2px;"></div>
    <div class="empty-block fade-in" style="margin-bottom: 0;">GitHub, LinkedIn 등 추가 연락처는 업데이트 예정입니다.</div>
    <div class="contact-links">
      <a href="mailto:mindat@hanyang.ac.kr" class="contact-link">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
        mindat@hanyang.ac.kr
      </a>
    </div>
  </div>
</section>

<footer>
  © 2024 최민혁 · Minhyeok Choi · Built with GitHub Pages
</footer>

<script>
const obs = new IntersectionObserver(entries => {
  entries.forEach(e => { if(e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); } });
}, { threshold: 0.12 });
document.querySelectorAll('.fade-in').forEach(el => obs.observe(el));
</script>
</body>
</html>
