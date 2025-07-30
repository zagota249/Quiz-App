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
 <style>
  *{
    padding: 0;
    margin: 0;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
body{
    background-color: rgb(76, 206, 119);
}
h1{
    text-align: center;
}
h2{
    margin: 30px;
    text-align: center;
}

.options{
     display: flex;
    background-color: transparent;
    justify-content: center;
    cursor: pointer;
}
 .options button{
    margin: 10px;
    width: 100%;
    height: 100%;
    background-color: transparent;
    border: transparent;
}
.options button:hover{
    transition: 1s ease-in-out;
    color: aquamarine;
}

.submit{
    display: flex;
    justify-content: center;

}
#submit{
    margin: 20px;
    box-shadow:
    inset 2px 2px 8px #00f0ff,
    inset 2px 2px 16px #00f0ff,
    inset 8px 8px 24px #00f0ff;
    transition: transform 0.3s ease-in-out;
    /* animation: move 3s infinite; */
}
#submit:hover{
    transform: scale(1.3);
    color: rgb(29, 55, 56);
}
/* @keyframes move {
    
    0%{ transform: scale(1);}
    25%{transform: scale(1.5);}
    50%{transform: scale(2);}
    75%{transform: scale(2.5);}
    100%{transform: scale(3);}
} */


p{
    text-align: center;
}
 </style>
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

  <script>


   const question1 = document.getElementById("question");
const option1 = document.getElementById("option1");
const option2 = document.getElementById("option2");
const option3 = document.getElementById("option3");
const option4 = document.getElementById("option4");
const submit = document.getElementById("submit");
const result = document.getElementById("result");

let currentquestion = 0;
let score = 0;
let selected = null;

const quizQuestions = [
  {
    question: "What does HTML stand for?",
    options: [
      "Hyper Trainer Marking Language",
      "HyperText Markup Language",
      "HyperText Markdown Language",
      "HyperLoop Markup Language"
    ],
    correctAnswer: "HyperText Markup Language"
  },
  {
    question: "Which JavaScript method is used to select an element by ID?",
    options: [
      "getElementByClassName",
      "querySelectorAll",
      "getElementById",
      "querySelector"
    ],
    correctAnswer: "getElementById"
  },
  {
    question: "Which CSS property controls the text size?",
    options: [
      "font-style",
      "text-size",
      "font-size",
      "text-style"
    ],
    correctAnswer: "font-size"
  },
  {
    question: "What does the 'const' keyword do in JavaScript?",
    options: [
      "Declares a constant variable that can be reassigned",
      "Declares a constant variable that cannot be reassigned",
      "Creates a function",
      "Defines a loop"
    ],
    correctAnswer: "Declares a constant variable that cannot be reassigned"
  },
  {
    question: "Which of the following is NOT a JavaScript data type?",
    options: [
      "String",
      "Number",
      "Boolean",
      "Float"
    ],
    correctAnswer: "Float"
  }
];

function loadquestion() {
  const q = quizQuestions[currentquestion];
  question1.textContent = q.question;
  option1.textContent = q.options[0];
  option2.textContent = q.options[1];
  option3.textContent = q.options[2];
  option4.textContent = q.options[3];

  [option1, option2, option3, option4].forEach(btn => {
    btn.classList.remove("selected");
  });
  selected = null;
}

function selectedAns(btn) {
  [option1, option2, option3, option4].forEach(b => b.classList.remove("selected"));
  btn.classList.add("selected");
  selected = btn.textContent;
}

option1.onclick = () => selectedAns(option1);
option2.onclick = () => selectedAns(option2);
option3.onclick = () => selectedAns(option3);
option4.onclick = () => selectedAns(option4);

submit.onclick = function () {
  if (!selected) {
    alert("Please select an option");
    return;
  }

  if (selected === quizQuestions[currentquestion].correctAnswer) {
    score++;
  }
  currentquestion++;

  if (currentquestion < quizQuestions.length) {
    loadquestion();
  } else {
    showresult();
  }
};

function showresult() {
  question1.textContent = "Quiz Finished!";
  document.querySelector(".options").style.display = "none";
  submit.style.display = "none";
  result.textContent = `Your score is ${score} out of ${quizQuestions.length}`;
}

loadquestion();

  </script>
</body>
</html>
