# Hangbiao-Zhao.github.io

<p><a href="/BasicWebDev/Team Page Assignment.html" target="black">Team Page Assignment</a></p>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Our Team - Creative Co.</title>
  <style>
    /* Reset & base styling */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #f5f5f5;
      line-height: 1.6;
      padding-top: 60px; /* space for fixed nav */
    }

    /* Navigation Bar */
    nav {
      background-color: #333;
      color: white;
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 1000;
    }

    nav ul {
      list-style: none;
      display: flex;
      justify-content: center;
      padding: 15px 0;
    }

    nav ul li {
      margin: 0 20px;
    }

    nav ul li a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      transition: color 0.3s ease;
    }

    nav ul li a:hover {
      color: #ff9800;
    }

    /* Page Header */
    header {
      text-align: center;
      padding: 40px 20px 20px;
    }

    header h1 {
      color: #333;
    }

    /* Team Section */
    .team-container {
      width: 90%;
      max-width: 1100px;
      margin: 30px auto;
      overflow: hidden;
    }

    .team-member {
      float: left;
      width: 45%;
      margin: 2.5%;
      background-color: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }

    .team-member img {
      width: 100%;
      height: auto;
      border-radius: 6px;
    }

    .team-member h2 {
      margin-top: 15px;
      color: #222;
    }

    .team-member p {
      color: #555;
      margin-top: 10px;
    }

    /* Clearfix */
    .team-container::after {
      content: "";
      display: table;
      clear: both;
    }

    /* Footer positioned absolutely inside container */
    .footer {
      position: relative;
      margin-top: 40px;
      text-align: center;
      font-size: 14px;
      color: #888;
    }

    .footer::before {
      content: '';
      position: absolute;
      top: -20px;
      left: 50%;
      transform: translateX(-50%);
      width: 50px;
      height: 2px;
      background-color: #ccc;
    }
  </style>
</head>
<body>

  <!-- Navigation -->
  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">Our Team</a></li>
      <li><a href="#">Projects</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>

  <!-- Header -->
  <header>
    <h1>Meet Our Team</h1>
    <p>The passionate people behind Creative Co.</p>
  </header>

  <!-- Team Section -->
  <div class="team-container">
    <div class="team-member">
      <img src="https://via.placeholder.com/400x250" alt="Alex - Team Lead">
      <h2>Alex Rivera</h2>
      <p>Team Lead with 10+ years of experience managing creative and development projects. Alex ensures everything runs smoothly and on time.</p>
    </div>
    <div class="team-member">
      <img src="https://via.placeholder.com/400x250" alt="Jordan - Designer">
      <h2>Jordan Chen</h2>
      <p>Visual Designer with an eye for color and clean UI. Jordan crafts compelling visual experiences that speak volumes without words.</p>
    </div>
    <div class="team-member">
      <img src="https://via.placeholder.com/400x250" alt="Riley - Developer">
      <h2>Riley Thompson</h2>
      <p>Full-stack Developer who transforms design into fast, functional web applications. Riley writes code like a poet writes verse.</p>
    </div>
    <div class="team-member">
      <img src="https://via.placeholder.com/400x250" alt="Sam - Marketing">
      <h2>Sam Patel</h2>
      <p>Marketing strategist and content wizard. Sam knows how to reach audiences and build brands through storytelling and data.</p>
    </div>

    <!-- Positioned Footer -->
    <div class="footer">
      &copy; 2025 Creative Co. All rights reserved.
    </div>
  </div>

</body>
</html>
