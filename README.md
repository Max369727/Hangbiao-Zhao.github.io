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
    <meta charset="UTF-8">
    <title>Scorecard 2</title>
    <style>
        table {
            width: 70%;
            border: 2px solid #000;
            margin: 30px auto;
            border-collapse: collapse;
        }
        th, td {
            padding: 12px;
            border: 1px solid #888;
        }
        th:hover {
            background-color: #d1e7dd;
        }
        caption {
            font-weight: bold;
            font-size: 1.2em;
        }
    </style>
</head>
<body>
    <table>
        <caption>Round 2 - Team C vs Team D</caption>
        <tr>
            <th>Player</th>
            <th>Score</th>
        </tr>
        <tr>
            <td>Player 3</td>
            <td>10</td>
        </tr>
        <tr>
            <td>Player 4</td>
            <td>25</td>
        </tr>
    </table>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Scorecard 1</title>
  <style>
    table {
      width: 60%;
      border-collapse: collapse;
      margin: 20px auto;
    }
    th, td {
      border: 1px solid #444;
      padding: 10px;
      text-align: center;
    }
    tr:hover {
      background-color: #f0f0f0;
    }
    caption {
      font-size: 1.5em;
      margin-bottom: 10px;
    }
  </style>
</head>
<body>
  <table>
    <caption>Round 1 - Team A vs Team B</caption>
    <tr>
      <th>Player</th>
      <th>Score</th>
    </tr>
    <tr>
      <td>Player 1</td>
      <td>15</td>
    </tr>
    <tr>
      <td>Player 2</td>
      <td>20</td>
    </tr>
  </table>
</body>
</html>
