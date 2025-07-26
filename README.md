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
  <title>Scorecard 3</title>
  <style>
    table {
      margin: 20px auto;
      width: 80%;
      border-collapse: collapse;
      font-family: Arial, sans-serif;
    }
    th, td {
      border: 1px solid #ccc;
      padding: 8px 12px;
    }
    td:hover {
      background-color: #ffebcd;
    }
    caption {
      font-size: 1.3em;
      color: #333;
    }
  </style>
</head>
<body>
  <table>
    <caption>Round 3 - Team E vs Team F</caption>
    <tr>
      <th>Player</th>
      <th>Score</th>
    </tr>
    <tr>
      <td>Player 5</td>
      <td>18</td>
    </tr>
    <tr>
      <td>Player 6</td>
      <td>22</td>
    </tr>
  </table>
</body>
</html>
