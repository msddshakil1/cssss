<!DOCTYPE html>
<html>
  <head>
    <title>BMI CALCULATOR</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background-color: #1e1c2575;
      }
      
      h1 {
        text-align: center;
        color: #000000;
      }
      
      form {
        width: 300px;
        margin: 0 auto;
        background-color: #fffdfd;
        border: 1px solid #000000;
        padding: 20px;
        box-shadow: 2px 2px 5px #ececec;
      }
      
      label {
        display: inline-block;
        width: 100px;
        text-align: right;
        margin-right: 10px;
        color: #333;
      }
      
      input[type="number"] {
        width: 150px;
        padding: 5px;
        border: 1px solid #000000;
        border-radius: 3px;
        box-sizing: border-box;
        margin-bottom: 10px;
      }
      
      button {
        background-color: #6b0909;
        color: #fff;
        border: none;
        padding: 10px;
        border-radius: 3px;
        cursor: pointer;
        width: 100%;
      }
      
      button:hover {
        background-color: #6d0000;
      }
      
      .result {
        display: block;
        margin-top: 10px;
        font-weight: bold;
        font-size: 18px;
        color: #020101;
      }
      
      .reminder {
        display: block;
        margin-top: 10px;
        font-size: 16px;
        color: #333;
      }
      
      .good {
        color: green;
      }
      
      .bad {
        color: red;
      }
    </style>
    <script>
      function calculateBMI() {
        var weight = parseFloat(document.getElementById('weight').value);
        var height = parseFloat(document.getElementById('height').value);
        var bmi = weight / (height * height);
        document.getElementById('result').innerHTML = bmi.toFixed(2);
        var reminder = document.getElementById('reminder');
        if (bmi < 25) {
          reminder.className = 'reminder good';
          reminder.innerHTML = 'Your BMI is good! work hard to fit';
        } else {
          reminder.className = 'reminder bad';
          reminder.innerHTML = 'Your BMI is too high. You should try to lose weight.';
        }
      }
    </script>
  </head>
  <body>
    <h1>BMI Calculator</h1>
    <form>
      <p>
        <label>Weight (kg):</label>
        <input type="number" id="weight">
      </p>
      <p>
        <label>Height (m):</label>
        <input type="number" id="height">
      </p>
      <button type="button" onclick="calculateBMI()">Calculate BMI</button>
      <p class="result">Your BMI is: <span id="result"></span></p>
      <p id="reminder" class="reminder"></p>
    </form>
  </body>
</html>
