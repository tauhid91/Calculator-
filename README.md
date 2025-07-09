<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Basic Calculator</title>
  <style>
    body {
      background: #f0f0f0;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .calculator {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px #aaa;
      width: 260px;
    }
    .calculator input[type="text"] {
      width: 100%;
      font-size: 24px;
      padding: 10px;
      margin-bottom: 10px;
      text-align: right;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    .buttons button {
      padding: 15px;
      font-size: 18px;
      cursor: pointer;
    }
  </style>
</head>
<body>

<div class="calculator">
  <input type="text" id="display" readonly>
  <div class="buttons">
    <button onclick="clearDisplay()">C</button>
    <button onclick="appendValue('/')">÷</button>
    <button onclick="appendValue('*')">×</button>
    <button onclick="appendValue('-')">−</button>

    <button onclick="appendValue('7')">7</button>
    <button onclick="appendValue('8')">8</button>
    <button onclick="appendValue('9')">9</button>
    <button onclick="appendValue('+')">+</button>

    <button onclick="appendValue('4')">4</button>
    <button onclick="appendValue('5')">5</button>
    <button onclick="appendValue('6')">6</button>
    <button onclick="calculate()">=</button>

    <button onclick="appendValue('1')">1</button>
    <button onclick="appendValue('2')">2</button>
    <button onclick="appendValue('3')">3</button>
    <button onclick="appendValue('0')" style="grid-column: span 2;">0</button>
    <button onclick="appendValue('.')">.</button>
  </div>
</div>

<script>
  const display = document.getElementById('display');

  function appendValue(value) {
    display.value += value;
  }

  function clearDisplay() {
    display.value = '';
  }

  function calculate() {
    try {
      display.value = eval(display.value);
    } catch (e) {
      display.value = 'Error';
    }
  }
</script>

</body>
</html>
