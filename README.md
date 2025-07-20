# Hangbiao-Zhao.github.io

<p><a href="/BasicWebDev/Math Test Form Assignment.html" target="black">Math Test Form Assignment</a></p>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Math and Logic Quiz</title>
</head>
<body>

    <!-- Start of Test -->
    <h1>Math & Logic Quiz</h1>

    <form action="/submit" method="post">

        <label for="username">Enter your name:</label><br>
        <input type="text" id="username" name="username" required><br><br>

        <!-- Question 1 -->
        <p>
            1. What is the result of 5 &lt; 8?
        </p>
        <input type="radio" id="q1a" name="q1" value="True">
        <label for="q1a">True</label><br>
        <input type="radio" id="q1b" name="q1" value="False">
        <label for="q1b">False</label><br><br>

        <!-- Question 2 -->
        <p>
            2. Which of the following is a prime number?
        </p>
        <input type="radio" id="q2a" name="q2" value="12">
        <label for="q2a">12</label><br>
        <input type="radio" id="q2b" name="q2" value="7">
        <label for="q2b">7</label><br>
        <input type="radio" id="q2c" name="q2" value="15">
        <label for="q2c">15</label><br><br>

        <!-- Question 3 -->
        <p>
            3. Which symbol means "not equal to"?
        </p>
        <input type="radio" id="q3a" name="q3" value="&ne;">
        <label for="q3a">&ne;</label><br>
        <input type="radio" id="q3b" name="q3" value="&gt;">
        <label for="q3b">&gt;</label><br>
        <input type="radio" id="q3c" name="q3" value="&lt;">
        <label for="q3c">&lt;</label><br><br>

        <!-- Word Problem -->
        <p>
            4. Word Problem:<br>
            Sarah has 3 apples. She gives 1 apple to Tom and buys 2 more.
            How many apples does she have now?
        </p>
        <textarea name="word_problem" rows="4" cols="50" placeholder="Type your answer here..."></textarea><br><br>

        <!-- Submit -->
        <input type="submit" value="Submit Quiz">

    </form>
    <!-- End of Test -->

</body>
</html>

</body>
</html>
