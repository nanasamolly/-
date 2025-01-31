<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Quiz</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 20px;
    }
    .quiz-container {
      max-width: 600px;
      margin: auto;
      padding: 20px;
      border: 1px solid #ddd;
      border-radius: 10px;
      box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
    }
    .question {
      font-size: 18px;
      margin-bottom: 10px;
    }
    .options label {
      display: block;
      margin: 5px 0;
    }
    .result {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="quiz-container">
    <h1>Simple Quiz</h1>
    <div class="question">What is 2 + 2?</div>
    <div class="options">
      <input type="radio" id="opt1" name="answer" value="3">
      <label for="opt1">3</label>
      <input type="radio" id="opt2" name="answer" value="4">
      <label for="opt2">4</label>
      <input type="radio" id="opt3" name="answer" value="5">
      <label for="opt3">5</label>
    </div>
    <button onclick="checkAnswer()">Submit</button>
    <div id="result" class="result"></div>
  </div>

  <script>
    function checkAnswer() {
      const selected = document.querySelector('input[name="answer"]:checked');
      const result = document.getElementById('result');
      if (!selected) {
        result.textContent = "Please select an answer.";
        result.style.color = "red";
        return;
      }
      const answer = selected.value;
      if (answer === "4") {
        result.textContent = "Correct! Well done.";
        result.style.color = "green";
      } else {
        result.textContent = "Incorrect. Try again.";
        result.style.color = "red";
      }
    }
  </script>
</body>
</html>
