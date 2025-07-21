
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Daily Menus</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f3f3f3;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 30px;
      padding: 30px;
    }

    .menu {
      width: 400px;
      height: 550px;
      padding: 20px;
      margin: 20px;
      border: 3px solid #444;
      border-radius: 10px;
      color: #fff;
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }

    .breakfast {
      background-image: url('https://images.unsplash.com/photo-1506084868230-bb9d95c24759'); /* breakfast bg */
    }

    .lunch {
      background-image: url('https://images.unsplash.com/photo-1517248135467-4c7edcad34c4'); /* lunch bg */
      background-position: top;
    }

    .dinner {
      background-image: url('https://images.unsplash.com/photo-1543353071-873f17a7a088'); /* dinner bg */
      background-repeat: no-repeat;
      background-position: bottom;
    }

    h2 {
      text-align: center;
      text-shadow: 1px 1px 3px #000;
    }

    ul {
      list-style-type: square;
      margin-top: 20px;
    }

    li {
      margin-bottom: 10px;
    }
  </style>
</head>
<body>

  <div class="menu breakfast">
    <h2>Breakfast Menu</h2>
    <ul>
      <li>Pancakes with syrup</li>
      <li>Scrambled eggs & toast</li>
      <li>Orange juice or coffee</li>
    </ul>
  </div>

  <div class="menu lunch">
    <h2>Lunch Menu</h2>
    <ul>
      <li>Grilled chicken sandwich</li>
      <li>Caesar salad</li>
      <li>Lemon iced tea</li>
    </ul>
  </div>

  <div class="menu dinner">
    <h2>Dinner Menu</h2>
    <ul>
      <li>Spaghetti Bolognese</li>
      <li>Garlic bread</li>
      <li>Red wine or water</li>
    </ul>
  </div>

</body>
</html>
