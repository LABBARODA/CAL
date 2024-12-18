<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portable Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f4;
        }
        .calculator {
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
        }
        .screen {
            width: 240px;
            height: 40px;
            text-align: right;
            font-size: 24px;
            margin-bottom: 10px;
            padding: 10px;
            border-radius: 5px;
            border: 1px solid #ccc;
            background-color: #f0f0f0;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }
        .buttons button {
            font-size: 20px;
            padding: 20px;
            border: none;
            background-color: #f0f0f0;
            cursor: pointer;
            border-radius: 5px;
            transition: background-color 0.2s ease;
        }
        .buttons button:hover {
            background-color: #e0e0e0;
        }
        .buttons button:active {
            background-color: #d0d0d0;
        }
        .buttons button.operator {
            background-color: #f7bc00;
        }
        .buttons button.operator:hover {
            background-color: #e0a700;
        }
        .buttons button.equal {
            background-color: #4CAF50;
            color: white;
        }
        .buttons button.equal:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

<div class="calculator">
    <input id="screen" class="screen" type="text" readonly>

    <div class="buttons">
        <button onclick="clearScreen()">C</button>
        <button onclick="appendToScreen('7')">7</button>
        <button onclick="appendToScreen('8')">8</button>
        <button onclick="appendToScreen('9')">9</button>
        <button class="operator" onclick="appendToScreen('+')">+</button>

        <button onclick="appendToScreen('4')">4</button>
        <button onclick="appendToScreen('5')">5</button>
        <button onclick="appendToScreen('6')">6</button>
        <button class="operator" onclick="appendToScreen('-')">-</button>

        <button onclick="appendToScreen('1')">1</button>
        <button onclick="appendToScreen('2')">2</button>
        <button onclick="appendToScreen('3')">3</button>
        <button class="operator" onclick="appendToScreen('*')">*</button>

        <button onclick="appendToScreen('0')">0</button>
        <button onclick="appendToScreen('.')">.</button>
        <button class="equal" onclick="calculateResult()">=</button>
        <button class="operator" onclick="appendToScreen('/')">/</button>
    </div>
</div>

<script>
    function appendToScreen(value) {
        document.getElementById('screen').value += value;
    }

    function clearScreen() {
        document.getElementById('screen').value = '';
    }

    function calculateResult() {
        let screen = document.getElementById('screen');
        try {
            screen.value = eval(screen.value);
        } catch (error) {
            screen.value = 'Error';
        }
    }
</script>

</body>
</html>
