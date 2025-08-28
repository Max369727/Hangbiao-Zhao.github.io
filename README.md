<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8">
  <title>扫雷游戏</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
    }
    h1 {
      margin-top: 20px;
    }
    #board {
      display: grid;
      grid-template-columns: repeat(10, 30px);
      grid-template-rows: repeat(10, 30px);
      margin: 20px auto;
      width: max-content;
      user-select: none;
    }
    .cell {
      width: 30px;
      height: 30px;
      border: 1px solid #888;
      line-height: 30px;
      text-align: center;
      font-size: 16px;
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
          // 右键标记
          cell.addEventListener("contextmenu", (e) => {
            e.preventDefault();
            handleFlag(i, j);
          });
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
