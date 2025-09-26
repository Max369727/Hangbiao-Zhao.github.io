<!doctype html>
<html lang="zh-CN">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>飞机背景 - 三个小块示例</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
  <style>
    :root{
      --card-bg: rgba(255,255,255,0.92);
      --accent: #0b69ff;
      --muted: #5b6470;
      --glass: rgba(255,255,255,0.6);
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial}

    /* 飞机 SVG 作为页面背景（居中并覆盖） */
    body{
      background:
        radial-gradient(ellipse at top left, rgba(11,105,255,0.12), transparent 25%),
        linear-gradient(180deg, #e9f1ff 0%, #f6fbff 60%);
      min-height:100%;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:40px;
      background-image: url('data:image/svg+xml;utf8,<?xml version="1.0" encoding="UTF-8"?><svg xmlns="http://www.w3.org/2000/svg" width="1200" height="800" viewBox="0 0 1200 800"><defs><linearGradient id="g" x1="0" x2="1"><stop offset="0" stop-color="%230b69ff" stop-opacity="0.06"/><stop offset="1" stop-color="%23ffffff" stop-opacity="0.02"/></linearGradient></defs><rect width="1200" height="800" fill="none"/><g transform="translate(200,120) scale(1.4)"><path d="M10 120 C40 80 120 80 160 110 L420 210 C460 230 520 200 580 170 C640 140 740 120 860 140 C980 160 1050 240 1110 280" stroke="%230b69ff" stroke-opacity="0.12" stroke-width="12" fill="none" stroke-linecap="round" stroke-linejoin="round"/></g><g transform="translate(600,180) scale(0.6)"><path d="M120 20 L160 60 L220 70 L260 40 L320 30 L360 50 L420 40 L460 10 L420 -30 L360 -20 L320 0 L260 -10 L220 -40 L160 -30 Z" fill="%230b69ff" fill-opacity="0.08"/></g></svg>');
      background-repeat:no-repeat;
      background-position: center -60px;
      background-size: cover;
    }

    .wrap{
      width:100%;
      max-width:1100px;
      display:grid;
      grid-template-columns: 1fr 340px;
      gap:28px;
      align-items:start;
    }

    .hero{
      padding:28px 30px;
      background: linear-gradient(180deg, rgba(255,255,255,0.8), rgba(255,255,255,0.7));
      border-radius:16px;
      box-shadow: 0 10px 30px rgba(19,34,68,0.08);
      backdrop-filter: blur(6px) saturate(1.05);
    }

    h1{margin:0 0 8px 0;font-size:28px;color:#07203b}
    p.lead{margin:0;color:var(--muted);font-size:15px}

    /* 右侧小块容器 */
    .side{
      display:flex;
      flex-direction:column;
      gap:18px;
      align-items:stretch;
    }

    .card{
      background: var(--card-bg);
      padding:18px;
      border-radius:12px;
      box-shadow: 0 6px 18px rgba(16,30,60,0.06);
      transition:transform .22s ease, box-shadow .22s ease;
      border: 1px solid rgba(11,105,255,0.06);
    }
    .card:hover{transform:translateY(-6px);box-shadow: 0 18px 40px rgba(11,105,255,0.08)}

    .card h3{margin:0 0 6px 0;font-size:16px;color:#06203a}
    .card p{margin:0;color:var(--muted);font-size:13px;line-height:1.45}

    /* 三个小块在手机下横排显示在 hero 下 */
    .blocks{
      display:flex;
      gap:14px;
      margin-top:18px;
      flex-wrap:wrap;
    }
    .block-small{flex:1 1 140px;padding:12px;border-radius:10px;background:linear-gradient(180deg,var(--glass),rgba(255,255,255,0.85));border:1px solid rgba(11,105,255,0.05)}
    .block-small h4{margin:0 0 6px 0;font-size:14px}
    .block-small p{margin:0;font-size:12px;color:var(--muted)}

    /* 响应式 */
    @media (max-width:960px){
      .wrap{grid-template-columns: 1fr;}
      body{padding:24px}
    }

  </style>
</head>
<body>
  <div class="wrap">
    <div class="hero">
      <h1>飞机背景示例页面</h1>
      <p class="lead">下面的三个小块分别展示了 Introduction、Activities 与 Benefits。页面使用飞机为主题的背景，适合用于航旅、培训或产品说明小组件。</p>

      <div class="blocks" aria-hidden="false">
        <div class="block-small" id="intro">
          <h4>Introduction</h4>
          <p>简要介绍：说明页面目的、背景或项目概况，让读者快速理解主题。</p>
        </div>
        <div class="block-small" id="activities">
          <h4>Activities</h4>
          <p>活动示例：列出相关活动、日程或操作步骤，如航班签到、登机流程或行前准备清单。</p>
        </div>
        <div class="block-small" id="benefits">
          <h4>Benefits</h4>
          <p>收益/优点：突出本服务或方案能为用户带来的好处，例如省时、可靠或舒适。</p>
        </div>
      </div>

      <p style="margin-top:18px;font-size:12px;color:var(--muted)">提示：你可以直接编辑文字内容、配色或将 SVG 背景替换为你的图片。</p>
    </div>

    <div class="side">
      <div class="card">
        <h3>Introduction</h3>
        <p>本部分用于介绍主题背景与目标受众，快速传达页面的核心信息与使用场景。</p>
      </div>

      <div class="card">
        <h3>Activities</h3>
        <p>列出关键活动或服务流程（例如：预订、值机、登机、行李托运），并可链接至更详细的步骤页面。</p>
      </div>

      <div class="card">
        <h3>Benefits</h3>
        <p>展示用户将获得的收益，如时间节省、行程保障、额外服务等，增强转换意愿。</p>
      </div>
    </div>
  </div>
</body>
</html>

<!DOCTYPE html>
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
