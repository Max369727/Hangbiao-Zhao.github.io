<!doctype html>
<html lang="zh-CN">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>井字棋 (Tic‑Tac‑Toe)</title>
<style>
:root{
--bg:#0f1724; --card:#0b1220; --accent:#7c3aed; --muted:#94a3b8; --cell:#0f1724;
--x-color:#f97316; --o-color:#60a5fa; --win:#10b981;
font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
}
*{box-sizing:border-box}
html,body{height:100%;}
body{margin:0; background:linear-gradient(180deg,#071029 0%, #071827 100%); color:#e6eef8; display:flex; align-items:center; justify-content:center; padding:24px}

.container{width:100%; max-width:760px; background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border-radius:14px; padding:20px; box-shadow:0 8px 30px rgba(2,6,23,0.6)}

header{display:flex; align-items:center; justify-content:space-between; gap:12px; margin-bottom:16px}
h1{font-size:1.25rem; margin:0}
.subtitle{color:var(--muted); font-size:0.9rem}

.board-wrap{display:grid; grid-template-columns:1fr 300px; gap:18px}
@media (max-width:760px){.board-wrap{grid-template-columns:1fr;}}

.board{background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.02)); padding:16px; border-radius:10px; display:grid; grid-template-columns:repeat(3, 1fr); gap:10px}
.cell{background:var(--cell); border-radius:8px; aspect-ratio:1/1; display:flex; align-items:center; justify-content:center; font-size:3.2rem; cursor:pointer; user-select:none; transition:transform .12s ease, box-shadow .12s ease; color:var(--muted); position:relative}
.cell:focus{outline:3px solid rgba(124,58,237,0.18); transform:translateY(-2px)}
.cell:hover{transform:translateY(-4px); box-shadow:0 8px 20px rgba(2,6,23,0.5)}
.cell.disabled{cursor:not-allowed; opacity:0.9}

.x{color:var(--x-color);}
.o{color:var(--o-color)}
.win{background:linear-gradient(90deg, rgba(16,185,129,0.06), rgba(124,58,237,0.03)); box-shadow:0 8px 30px rgba(16,185,129,0.06) inset}

.side{background:rgba(255,255,255,0.02); padding:12px; border-radius:10px; display:flex; flex-direction:column; gap:12px}
.status{font-weight:600}
.controls{display:flex; gap:8px;}
.btn{background:transparent; border:1px solid rgba(255,255,255,0.06); padding:8px 12px; border-radius:8px; cursor:pointer; color:inherit}
.btn.primary{background:linear-gradient(90deg,var(--accent), #5eead4); color:#071827; border:0}

.score{display:flex; gap:8px; justify-content:space-between; background:rgba(255,255,255,0.01); padding:8px; border-radius:8px}
.small{font-size:0.9rem; color:var(--muted)}

footer{margin-top:12px; text-align:center; color:var(--muted); font-size:0.85rem}

/* simple animations for marks */
.mark{transform:scale(0); animation:pop .14s ease forwards}
@keyframes pop{to{transform:scale(1)}}

</style>
</head>
<body>
<div class="container" role="application" aria-label="井字棋游戏">
<header>
<div>
<h1>井字棋 • Tic‑Tac‑Toe</h1>
<div class="subtitle">按顺序点击或用键盘选择格子 - X 先手</div>
</div>
<div class="small">简单、可访问、响应式</div>
</header>

<main class="board-wrap">
<section>
<div id="board" class="board" role="grid" aria-label="井字棋棋盘" tabindex="0">
<!-- 9 cells injected by script -->
</div>
</section>

<aside class="side" aria-labelledby="status">
<div class="status" id="status">轮到: <span id="turn">X</span></div>
<div class="score" aria-live="polite">
<div><strong>X</strong><div class="small" id="score-x">0</div></div>
<div><strong>平局</strong><div class="small" id="score-d">0</div></div>
<div><strong>O</strong><div class="small" id="score-o">0</div></div>
</div>

</html>
