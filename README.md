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

        <div class="controls">
          <button id="restart" class="btn">重开局</button>
          <button id="resetScores" class="btn">清除分数</button>
        </div>

        <div class="small">提示：使用箭头键导航格子，Enter 或空格落子。获胜时连线格子会被高亮。</div>
      </aside>
    </main>

    <footer>制作：ChatGPT • 祝你游戏愉快！</footer>
  </div>

  <script>
    (function(){
      const boardEl = document.getElementById('board');
      const statusEl = document.getElementById('status');
      const turnEl = document.getElementById('turn');
      const scoreXEl = document.getElementById('score-x');
      const scoreOEl = document.getElementById('score-o');
      const scoreDEl = document.getElementById('score-d');
      const restartBtn = document.getElementById('restart');
      const resetBtn = document.getElementById('resetScores');

      let board = Array(9).fill(null);
      let xIsNext = true;
      let finished = false;
      let focusedIndex = 0;

      const scores = { X:0, O:0, D:0 };

      const WIN_COMBOS = [
        [0,1,2], [3,4,5], [6,7,8],
        [0,3,6], [1,4,7], [2,5,8],
        [0,4,8], [2,4,6]
      ];

      function createCells(){
        boardEl.innerHTML='';
        for(let i=0;i<9;i++){
          const cell = document.createElement('button');
          cell.className='cell';
          cell.setAttribute('role','gridcell');
          cell.setAttribute('aria-label',`格子 ${i+1}`);
          cell.setAttribute('data-index',i);
          cell.tabIndex = i===0?0:-1;
          cell.addEventListener('click', onCellClick);
          cell.addEventListener('keydown', onCellKeyDown);
          boardEl.appendChild(cell);
        }
      }

      function render(){
        const cells = boardEl.querySelectorAll('.cell');
        cells.forEach((c, i)=>{
          c.classList.remove('x','o','win','disabled');
          c.innerHTML='';
          if(board[i]){
            const span = document.createElement('span');
            span.className='mark ' + (board[i] === 'X' ? 'x' : 'o');
            span.textContent = board[i];
            c.appendChild(span);
            c.classList.add(board[i] === 'X' ? 'x' : 'o');
            c.classList.add('disabled');
            c.tabIndex = -1;
          } else {
            c.tabIndex = (i===focusedIndex) ? 0 : -1;
          }
        });

        const winner = calculateWinner();
        if(winner){
          finished = true;
          highlightWin(winner);
          statusEl.textContent = `胜者: ${winner.player}`;
          scores[winner.player]++;
          updateScores();
        } else if(board.every(Boolean)){
          finished = true;
          statusEl.textContent = '平局';
          scores.D++;
          updateScores();
        } else {
          finished = false;
          turnEl.textContent = xIsNext? 'X' : 'O';
          statusEl.innerHTML = `轮到: <strong id="turn">${xIsNext? 'X' : 'O'}</strong>`;
        }
      }

      function onCellClick(e){
        const i = Number(e.currentTarget.dataset.index);
        handleMove(i);
      }

      function onCellKeyDown(e){
        const i = Number(e.currentTarget.dataset.index);
        switch(e.key){
          case 'Enter': case ' ': e.preventDefault(); handleMove(i); break;
          case 'ArrowRight': e.preventDefault(); moveFocus((i+1)%9); break;
          case 'ArrowLeft': e.preventDefault(); moveFocus((i+8)%9); break;
          case 'ArrowDown': e.preventDefault(); moveFocus((i+3)%9); break;
          case 'ArrowUp': e.preventDefault(); moveFocus((i+6)%9); break;
        }
      }

      function moveFocus(i){
        focusedIndex = i;
        const cells = boardEl.querySelectorAll('.cell');
        cells.forEach((c, idx)=> c.tabIndex = (idx===i)?0:-1);
        cells[i].focus();
      }

      function handleMove(i){
        if(finished || board[i]) return;
        board[i] = xIsNext ? 'X' : 'O';
        xIsNext = !xIsNext;
        // update next focus to next empty cell (simple behavior)
        const nextEmpty = board.findIndex((v)=>v===null);
        focusedIndex = nextEmpty === -1 ? 0 : nextEmpty;
        render();
        // If finished, move focus back to board for screen readers
        if(finished){ boardEl.focus(); }
      }

      function calculateWinner(){
        for(const combo of WIN_COMBOS){
          const [a,b,c] = combo;
          if(board[a] && board[a] === board[b] && board[a] === board[c]){
            return { player: board[a], combo };
          }
        }
        return null;
      }

      function highlightWin(winner){
        const cells = boardEl.querySelectorAll('.cell');
        winner.combo.forEach(i=> cells[i].classList.add('win'));
        // disable remaining empty cells
        cells.forEach((c,i)=>{ if(!board[i]) c.classList.add('disabled'); c.tabIndex = -1; });
      }

      function updateScores(){
        scoreXEl.textContent = scores.X;
        scoreOEl.textContent = scores.O;
        scoreDEl.textContent = scores.D;
      }

      function restart(){
        board = Array(9).fill(null);
        xIsNext = true;
        finished = false;
        focusedIndex = 0;
        createCells();
        render();
        moveFocus(0);
      }

      restartBtn.addEventListener('click', restart);
      resetBtn.addEventListener('click', ()=>{ scores.X=0; scores.O=0; scores.D=0; updateScores(); });

      // init
      createCells(); render();

      // allow keyboard navigation from board container
      boardEl.addEventListener('keydown', (e)=>{
        // If focus is on board container, map arrow keys to move
        if(document.activeElement === boardEl){
          switch(e.key){
            case 'ArrowRight': e.preventDefault(); moveFocus(0); break;
            case 'ArrowLeft': e.preventDefault(); moveFocus(8); break;
            case 'ArrowDown': e.preventDefault(); moveFocus(3); break;
            case 'ArrowUp': e.preventDefault(); moveFocus(6); break;
          }
        }
      });

    })();
  </script>
</body>
</html>
