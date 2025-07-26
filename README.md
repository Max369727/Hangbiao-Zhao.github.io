# Hangbiao-Zhao.github.io

<p><a href="/BasicWebDev/Scorecards Assignment.html" target="black">Scorecards Assignment</a></p>
<!DOCTYPE html>
<html>
<head>
    <title>Golf Scorecard</title>
    <style>
        table {
            border-collapse: collapse;
            width: 80%;
            margin: 20px auto;
            font-family: Arial, sans-serif;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: center;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
        tr:nth-child(even) {
            background-color: #f2f2f2;
        }
        tr:hover {
            background-color: #e6f7e6;
        }
        input {
            width: 50px;
            text-align: center;
        }
    </style>
</head>
<body>
    <h1>Golf Scorecard</h1>
    <table>
        <tr>
            <th>Hole</th>
            <th>1</th>
            <th>2</th>
            <th>3</th>
            <th>4</th>
            <th>5</th>
            <th>6</th>
            <th>7</th>
            <th>8</th>
            <th>9</th>
            <th>Total</th>
        </tr>
        <tr>
            <td>Par</td>
            <td>4</td>
            <td>3</td>
            <td>5</td>
            <td>4</td>
            <td>4</td>
            <td>3</td>
            <td>4</td>
            <td>5</td>
            <td>4</td>
            <td>36</td>
        </tr>
        <tr>
            <td><input type="text" placeholder="Player"></td>
            <td><input type="number"></td>
            <td><input type="number"></td>
            <td><input type="number"></td>
            <td><input type="number"></td>
            <td><input type="number"></td>
            <td><input type="number"></td>
            <td><input type="number"></td>
            <td><input type="number"></td>
            <td><input type="number"></td>
            <td></td>
        </tr>
    </table>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Bowling Scorecard</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <table>
    <caption>Bowling League - Game 5</caption>
    <tr>
      <th>Player</th>
      <th>Frame 1</th>
      <th>Frame 2</th>
      <th>Frame 3</th>
      <th>Total</th>
    </tr>
    <tr>
      <td>Charlie</td>
      <td>9</td>
      <td>8</td>
      <td>10</td>
      <td>27</td>
    </tr>
    <tr>
      <td>Dana</td>
      <td>7</td>
      <td>10</td>
      <td>9</td>
      <td>26</td>
    </tr>
  </table>
</body>
</html>


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Baseball Scorecard</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <table>
    <caption>Baseball Game - Innings</caption>
    <tr>
      <th>Team</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>4</th>
      <th>Total</th>
    </tr>
    <tr>
      <td>Tigers</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>4</td>
    </tr>
    <tr>
      <td>Lions</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>3</td>
    </tr>
  </table>
</body>
</html>
