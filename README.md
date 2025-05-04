# Build-a-calculator-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Simple Calculator</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #f3f3f3;
      font-family: Arial, sans-serif;
    }
    .calculator {
      border: 2px solid #ccc;
      border-radius: 10px;
      padding: 20px;
      background-color: white;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    }
    #display {
      width: 100%;
      height: 50px;
      font-size: 24px;
      text-align: right;
      margin-bottom: 10px;
      padding-right: 10px;
      box-sizing: border-box;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
    }
    button {
      height: 50px;
      font-size: 18px;
      cursor: pointer;
      border: none;
      border-radius: 5px;
      background-color: #eee;
      transition: background-color 0.2s;
    }
    button:hover {
      background-color: #ddd;
    }
    button:active {
      background-color: #ccc;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled>
    <div class="buttons">
      <button onclick="clearDisplay()">C</button>
      <button onclick="appendValue('/')">/</button>
      <button onclick="appendValue('*')">*</button>
      <button onclick="deleteLast()">DEL</button>

      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('-')">-</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('+')">+</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="calculateResult()">=</button>

      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
    </div>
  </div>

  <script>
    function appendValue(val) {
      document.getElementById('display').value += val;
    }

    function clearDisplay() {
      document.getElementById('display').value = '';
    }

    function deleteLast() {
      let display = document.getElementById('display');
      display.value = display.value.slice(0, -1);
    }

    function calculateResult() {
      let display = document.getElementById('display');
      try {
        display.value = eval(display.value);
      } catch {
        display.value = 'Error';
      }
    }
  </script>
</body>
</html>
