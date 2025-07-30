# Quiz-App
A simple Quiz Application built using HTML, CSS, and JavaScript It allows users to answer multiple-choice questions and get their final score at the end.

 Features

- Multiple-choice questions
- Final score display after submission

Technologies Used

- HTML5
- CSS3
- JavaScript
-----------------------------------------------------------
start




<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Quiz App</title>
  <link rel="stylesheet" href="style.css"/>
</head>
<body>

  <h1>Quiz App</h1>

  <div class="quiz-box">
    <h2 id="question">Question text</h2>

    <div class="options">
      <button id="option1" class="option"></button>
      <button id="option2" class="option"></button>
      <button id="option3" class="option"></button>
      <button id="option4" class="option"></button>
    </div>

    <div class="submit">
      <button id="submit">Submit</button>
    </div>

    <p id="result"></p>
  </div>

  <script src="script.js"></script>
</body>
</html>
