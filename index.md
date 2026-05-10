

---
layout: default
---

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.layout-container {
  display: flex;
  gap: 30px;
  max-width: 1400px;
  margin: 20px auto;
  padding: 0 20px;
  min-height: 80vh;
}

.profile-section {
  width: 300px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
  position: sticky;
  top: 20px;
  height: fit-content;
}

.profile-section h2 {
  margin-bottom: 15px;
  font-size: 24px;
  border-bottom: 2px solid rgba(255,255,255,0.3);
  padding-bottom: 10px;
}

.profile-section h3 {
  margin-top: 20px;
  margin-bottom: 10px;
  font-size: 18px;
}

.profile-section p {
  line-height: 1.6;
  margin-bottom: 10px;
}

.profile-section ul {
  list-style: none;
  padding-left: 0;
}

.profile-section li {
  margin: 8px 0;
  padding-left: 20px;
  position: relative;
}

.profile-section li:before {
  content: "▸";
  position: absolute;
  left: 0;
}

.profile-section a {
  color: #ffd700;
  text-decoration: none;
}

.profile-section a:hover {
  text-decoration: underline;
}

.content-frame {
  flex: 1;
  background: white;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
  overflow: hidden;
}

.content-frame iframe {
  width: 100%;
  height: 700px;
  border: none;
  display: block;
}

.nav-menu {
  margin-top: 20px;
  padding-top: 20px;
  border-top: 2px solid rgba(255,255,255,0.3);
}

.nav-menu a {
  display: block;
  padding: 10px 15px;
  margin: 5px 0;
  background: rgba(255,255,255,0.1);
  border-radius: 6px;
  transition: all 0.3s;
}

.nav-menu a:hover {
  background: rgba(255,255,255,0.2);
  transform: translateX(5px);
}

@media (max-width: 768px) {
  .layout-container {
    flex-direction: column;
  }
  
  .profile-section {
    width: 100%;
    position: relative;
  }
}
</style>

<div class="layout-container">
  <!-- 좌측 소개란 -->
  <div class="profile-section">
    <h2>👋 창현</h2>
    
    <h3>📌 소개</h3>
    <p>안녕하세요! GitHub Pages를 활용하여 개인 웹사이트를 만들고 있습니다.</p>
    
    <h3>💡 관심 분야</h3>
    <ul>
      <li>웹 개발</li>
      <li>프로그래밍</li>
      <li>오픈소스</li>
    </ul>
    
    <h3>🔗 링크</h3>
    <ul>
      <li><a href="https://github.com/chh930" target="_blank">GitHub</a></li>
      <li><a href="mailto:your-email@example.com">Email</a></li>
    </ul>
    
    <div class="nav-menu">
      <h3>📂 페이지</h3>
      <a href="#" onclick="loadPage('about'); return false;">소개 페이지</a>
      <a href="#" onclick="loadPage('projects'); return false;">프로젝트</a>
      <a href="#" onclick="loadPage('contact'); return false;">연락처</a>
      <a href="https://github.com/chh930" target="main-frame">GitHub 프로필</a>
    </div>
  </div>
  
  <!-- 우측 프레임 -->
  <div class="content-frame">
    <iframe id="main-frame" name="main-frame" src="about:blank"></iframe>
  </div>
</div>

<script>
function loadPage(page) {
  const frame = document.getElementById('main-frame');
  
  const pages = {
    about: `
      <div style="padding: 40px; font-family: -apple-system, sans-serif;">
        <h1 style="color: #333; margin-bottom: 20px;">📖 소개</h1>
        <p style="font-size: 18px; line-height: 1.8; color: #555;">
          이 사이트는 GitHub Pages와 Jekyll을 활용하여 만든 개인 홈페이지입니다.
          마크다운으로 간편하게 작성하고 관리할 수 있습니다.
        </p>
        <h2 style="color: #667eea; margin-top: 30px;">🎯 목표</h2>
        <ul style="font-size: 16px; line-height: 2; color: #555;">
          <li>GitHub Pages 활용 능력 향상</li>
          <li>웹 개발 포트폴리오 구축</li>
          <li>지속적인 학습과 성장</li>
        </ul>
      </div>
    `,
    projects: `
      <div style="padding: 40px; font-family: -apple-system, sans-serif;">
        <h1 style="color: #333; margin-bottom: 20px;">💼 프로젝트</h1>
        <div style="background: #f6f8fa; padding: 20px; border-radius: 8px; margin: 15px 0;">
          <h3 style="color: #667eea;">프로젝트 1</h3>
          <p style="color: #555; line-height: 1.6;">프로젝트 설명을 여기에 작성하세요.</p>
          <p style="color: #888; font-size: 14px;">기술 스택: HTML, CSS, JavaScript</p>
        </div>
        <div style="background: #f6f8fa; padding: 20px; border-radius: 8px; margin: 15px 0;">
          <h3 style="color: #667eea;">프로젝트 2</h3>
          <p style="color: #555; line-height: 1.6;">또 다른 프로젝트 설명입니다.</p>
          <p style="color: #888; font-size: 14px;">기술 스택: Jekyll, GitHub Pages</p>
        </div>
      </div>
    `,
    contact: `
      <div style="padding: 40px; font-family: -apple-system, sans-serif;">
        <h1 style="color: #333; margin-bottom: 20px;">📧 연락처</h1>
        <div style="font-size: 18px; line-height: 2.5; color: #555;">
          <p><strong>GitHub:</strong> <a href="https://github.com/chh930" style="color: #667eea;">@chh930</a></p>
          <p><strong>Email:</strong> <a href="mailto:your-email@example.com" style="color: #667eea;">your-email@example.com</a></p>
        </div>
      </div>
    `
  };
  
  frame.srcdoc = `
    <!DOCTYPE html>
    <html>
    <head>
      <meta charset="UTF-8">
      <style>
        body { margin: 0; padding: 0; }
        a { text-decoration: none; }
        a:hover { text-decoration: underline; }
      </style>
    </head>
    <body>${pages[page]}</body>
    </html>
  `;
}

// 페이지 로드 시 기본 페이지 표시
window.onload = function() {
  loadPage('about');
};
</script>

