# Hangbiao-Zhao.github.io

<p><a href="/BasicWebDev/Flexbox/CSS Grid Puzzle Assignment.html" target="black">Flexbox/CSS Grid Puzzle Assignment</a></p>
/* CSS Grid Layout */
.grid-container {
  display: grid;
  grid-template-areas:
    "header"
    "puzzle"
    "info";
  grid-gap: 30px;
  max-width: 1000px;
  margin: 0 auto;
  padding: 40px 20px;
  font-family: Arial, sans-serif;
  background-color: #f4fcff;
}

.header {
  grid-area: header;
  text-align: center;
  background-color: #c1e8f0;
  padding: 20px;
  border-radius: 8px;
}

.puzzle {
  grid-area: puzzle;
  text-align: center;
}

.puzzle-flex-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  gap: 10px;
  padding: 15px;
  background-color: #fff;
  border: 2px solid #cce;
  border-radius: 8px;
}

.puzzle-flex-container img {
  width: 100px;
  height: 100px;
  object-fit: cover;
  border: 1px solid #aaa;
  border-radius: 4px;
}

/* Hiding the faulty piece */
.hidden-piece {
  display: none;
}

.info {
  grid-area: info;
  background-color: #e6f7ff;
  padding: 20px;
  border-left: 5px solid #2ca0c8;
  border-radius: 5px;
}

ul {
  list-style-type: square;
  margin-top: 10px;
  padding-left: 20px;
}
