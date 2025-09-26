<!doctype html>
<html lang="zh-CN">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Aviation Club — 简洁展示</title>
  <style>
    /* 页面重置和全局样式 */
    * { box-sizing: border-box; }
    html,body { height:100%; margin:0; font-family: "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; color:#03324a; }
    body {
      /* 背景：使用海报图片（请将 IMG_0141.jpeg 和此 html 放在同一文件夹） */
      background-image: url("IMG_0141.jpeg");
      background-size: cover;
      background-position: center top;
      background-repeat: no-repeat;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:40px;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }

    /* 半透明覆盖层，提升卡片可读性 */
    .overlay {
      width:100%;
      max-width:1100px;
      background: linear-gradient(180deg, rgba(255,255,255,0.92), rgba(255,255,255,0.88));
      border-radius:16px;
      box-shadow: 0 10px 30px rgba(2,40,72,0.25);
      padding:28px;
      backdrop-filter: blur(2px);
    }

    header{
      display:flex;
      align-items:center;
      gap:20px;
      margin-bottom:18px;
    }
    .logo{
      width:84px;
      height:84px;
      border-radius:10px;
      background: linear-gradient(135deg,#bfe1ff,#8ec7ff);
      display:flex;
      align-items:center;
      justify-content:center;
      font-weight:700;
      color:#013c6b;
      box-shadow: 0 4px 14px rgba(2,40,72,0.1);
    }
    h1 { font-size:32px; margin:0; color:#063a5a; letter-spacing:1px; }
    h2 { font-size:20px; margin:0 0 8px 0; color:#0b4b6b; }

    /* 三列布局 */
    .grid {
      display:grid;
      grid-template-columns: 1fr 1fr 1fr;
      gap:18px;
    }

    .card {
      background: rgba(255,255,255,0.95);
      border-radius:12px;
      padding:16px;
      min-height:220px;
      box-shadow: 0 6px 18px rgba(3,50,80,0.06);
      border: 1px solid rgba(3,50,80,0.04);
    }

    .card h3 {
      margin:0 0 8px 0;
      font-size:18px;
      color:#03324a;
      display:flex;
      align-items:center;
      gap:8px;
    }

    .card p, .card ul { margin:0 0 8px 0; line-height:1.45; color:#123d52; font-size:14px; }
    .card ul { padding-left:18px; }
    .benefit-list { list-style: none; padding:0; margin:8px 0 0 0; }
    .benefit-list li {
      display:flex;
      align-items:flex-start;
      gap:10px;
      margin-bottom:10px;
    }
    .check {
      width:18px;
      height:18px;
      border-radius:50%;
      background:#0b74c3;
      color:white;
      display:inline-flex;
      align-items:center;
      justify-content:center;
      font-size:12px;
      flex:0 0 18px;
      margin-top:2px;
      box-shadow:0 2px 6px rgba(11,116,195,0.2);
    }

    /* Activities 列表图标样式 */
    .activity {
      display:flex;
      gap:12px;
      margin-bottom:10px;
      align-items:flex-start;
    }
    .act-icon {
      width:40px;height:40px;border-radius:8px;
      background:linear-gradient(180deg,#e7f5ff,#d0ebff);
      display:flex;align-items:center;justify-content:center;
      font-weight:700;color:#0b4b6b;flex:0 0 40px;
      box-shadow:0 6px 14px rgba(3,50,80,0.04);
    }
    .small-cta { margin-top:12px; font-size:13px; color:#04506f; }

    /* 页脚鼓励语 */
    .footer {
      margin-top:18px;
      text-align:center;
      padding-top:10px;
      border-top:1px dashed rgba(3,50,80,0.06);
      color:#034b6b;
      font-weight:600;
      letter-spacing:0.6px;
    }

    /* 响应式 */
    @media (max-width:980px){
      .grid { grid-template-columns: 1fr; }
      header { gap:12px; }
    }
  </style>
</head>
<body>
  <div class="overlay" role="main">
    <header>
      <div class="logo">AV</div>
      <div>
        <h1>CHASE THE BLUE SKY</h1>
        <div style="color:#0b5f83; font-weight:600; margin-top:6px;">THE AVIATION CLUB</div>
      </div>
    </header>

    <div class="grid" role="region" aria-label="Club info sections">
      <!-- Introduction -->
      <section class="card" id="introduction" aria-labelledby="intro-title">
        <h3 id="intro-title">Introduction</h3>
        <p><strong>The flying club</strong> is an organization for students interested in aviation and flying. Members learn about aviation knowledge, experience flight simulations, and share a love for the sky.</p>
        <p>Members will explore aircraft principles, basic aerodynamics, and gain an introduction to flight operations in a friendly, educational environment.</p>
      </section>

      <!-- Activities -->
      <section class="card" id="activities" aria-labelledby="acts-title">
        <h3 id="acts-title">Activities</h3>

        <div class="activity">
          <div class="act-icon">📘</div>
          <div>
            <strong>Aviation lectures</strong>
            <div style="font-size:13px; color:#114857; margin-top:6px;">Learn about flight principles and aircraft knowledge.</div>
          </div>
        </div>

        <div class="activity">
          <div class="act-icon">🕹️</div>
          <div>
            <strong>Flight simulation</strong>
            <div style="font-size:13px; color:#114857; margin-top:6px;">Operate flight simulators, practice instrument procedures and basic cockpit workflows.</div>
          </div>
        </div>

        <div class="activity">
          <div class="act-icon">✈️</div>
          <div>
            <strong>Visits and practice</strong>
            <div style="font-size:13px; color:#114857; margin-top:6px;">Visit airports and air shows to gain close-up aviation experience and observe real operations.</div>
          </div>
        </div>

        <div class="activity">
          <div class="act-icon">👥</div>
          <div>
            <strong>Exchange and sharing</strong>
            <div style="font-size:13px; color:#114857; margin-top:6px;">Members regularly share experiences and skills to help each other grow.</div>
          </div>
        </div>

        <div class="small-cta">（以上活动来源：海报内容整理）</div>
      </section>

      <!-- Benefits -->
      <aside class="card" id="benefits" aria-labelledby="ben-title">
        <h3 id="ben-title">Benefits</h3>
        <ul class="benefit-list" aria-hidden="false">
          <li><span class="check">✓</span><div>Learn rich aviation knowledge</div></li>
          <li><span class="check">✓</span><div>Cultivate teamwork spirit</div></li>
          <li><span class="check">✓</span><div>Inspire scientific exploration</div></li>
          <li><span class="check">✓</span><div>Lay foundation for future career planning</div></li>
        </ul>
        <p style="margin-top:6px; font-size:13px; color:#0a526e;">加入俱乐部可为未来航空或工程类职业路径打下良好基础，并提升动手与协作能力。</p>
      </aside>
    </div>

    <div class="footer">EMBRACE THE BLUE SKY, PURSUE THE DREAM OF FLYING!</div>
  </div>
</body>
</html>
