<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>扫雷游戏</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
    }
    h1 {
      margin: 20px 0;
    }
    #board {
      display: grid;
      grid-template-columns: repeat(10, 1fr);
      grid-template-rows: repeat(10, 1fr);
      margin: 20px auto;
      width: 90vw; /* 适配手机屏幕 */
      height: 90vw;
      max-width: 400px; /* 最大宽度 */
      max-height: 400px;
      user-select: none;
    }
    .cell {
      width: 100%;
      height: 100%;
      border: 1px solid #888;
      line-height: 30px;
      text-align: center;
      font-size: 18px;
      background-color: #ccc;
      cursor: pointer;
    }
    .cell.revealed {
      background-color: #eee;
      cursor: default;
    }
    .cell.bomb {
      background-color: red;
      color: white;
    }
    .cell.flagged {
      background-color: yellow;
    }
    /* 优化响应式布局 */
    @media (max-width: 600px) {
      .cell {
        font-size: 14px;
      }
    }
  </style>
</head>
<body>
  <h1>扫雷</h1>
  <div id="board"></div>
  <script>
    const boardSize = 10;
    const bombCount = 10;
    const board = document.getElementById("board");
    let cells = [];
    const longPressTime = 1000;  // 长按时间设置为 1 秒
    let pressTimer;

    function createBoard() {
      // 初始化
      cells = [];
      board.innerHTML = "";

      // 创建所有格子对象
      for (let i = 0; i < boardSize; i++) {
        cells[i] = [];
        for (let j = 0; j < boardSize; j++) {
          const cell = document.createElement("div");
          cell.classList.add("cell");
          cell.dataset.row = i;
          cell.dataset.col = j;
          board.appendChild(cell);
          cells[i][j] = {
            element: cell,
            hasBomb: false,
            revealed: false,
            flagged: false,
            adjacentBombs: 0,
          };

          // 左键点击
          cell.addEventListener("click", () => handleClick(i, j));

          // 长按标记
          cell.addEventListener("mousedown", (e) => startPress(i, j, e));
          cell.addEventListener("touchstart", (e) => startPress(i, j, e));
          
          // 释放时清除计时器
          cell.addEventListener("mouseup", () => cancelPress());
          cell.addEventListener("touchend", () => cancelPress());
          cell.addEventListener("mouseleave", () => cancelPress());
          cell.addEventListener("touchleave", () => cancelPress());
        }
      }

      placeBombs();
      countAdjacentBombs();
    }

    function placeBombs() {
      let bombsPlaced = 0;
      while (bombsPlaced < bombCount) {
        let row = Math.floor(Math.random() * boardSize);
        let col = Math.floor(Math.random() * boardSize);
        if (!cells[row][col].hasBomb) {
          cells[row][col].hasBomb = true;
          bombsPlaced++;
        }
      }
    }

    function countAdjacentBombs() {
      for (let i = 0; i < boardSize; i++) {
        for (let j = 0; j < boardSize; j++) {
          let count = 0;
          for (let dx = -1; dx <= 1; dx++) {
            for (let dy = -1; dy <= 1; dy++) {
              if (
                i + dx >= 0 && i + dx < boardSize &&
                j + dy >= 0 && j + dy < boardSize &&
                cells[i + dx][j + dy].hasBomb
              ) {
                count++;
              }
            }
          }
          cells[i][j].adjacentBombs = count;
        }
      }
    }

    function handleClick(row, col) {
      const cell = cells[row][col];
      if (cell.revealed || cell.flagged) return;

      cell.revealed = true;
      cell.element.classList.add("revealed");

      if (cell.hasBomb) {
        cell.element.classList.add("bomb");
        cell.element.textContent = "💣";
        revealAll();
        alert("💥 游戏结束！");
      } else if (cell.adjacentBombs > 0) {
        cell.element.textContent = cell.adjacentBombs;
      } else {
        // 自动展开周围区域
        for (let dx = -1; dx <= 1; dx++) {
          for (let dy = -1; dy <= 1; dy++) {
            let newRow = row + dx;
            let newCol = col + dy;
            if (
              newRow >= 0 && newRow < boardSize &&
              newCol >= 0 && newCol < boardSize
            ) {
              handleClick(newRow, newCol);
            }
          }
        }
      }
    }

    function startPress(row, col, e) {
      pressTimer = setTimeout(() => {
        handleFlag(row, col);
      }, longPressTime);
    }

    function cancelPress() {
      clearTimeout(pressTimer);
    }

    function handleFlag(row, col) {
      const cell = cells[row][col];
      if (cell.revealed) return;
      cell.flagged = !cell.flagged;
      cell.element.classList.toggle("flagged");
      cell.element.textContent = cell.flagged ? "🚩" : "";
    }

    function revealAll() {
      for (let i = 0; i < boardSize; i++) {
        for (let j = 0; j < boardSize; j++) {
          const cell = cells[i][j];
          if (!cell.revealed) {
            cell.revealed = true;
            cell.element.classList.add("revealed");
            if (cell.hasBomb) {
              cell.element.textContent = "💣";
              cell.element.classList.add("bomb");
            } else if (cell.adjacentBombs > 0) {
              cell.element.textContent = cell.adjacentBombs;
            }
          }
        }
      }
    }

    createBoard();
  </script>
</body>
</html>
