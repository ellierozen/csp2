<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Binary Number Guesser</title>
    <style>
        body {
            font-family: 'Courier New', Courier, monospace;
            text-align: center;
            margin: 20px;
            background-color: #f5f5f5;
        }
        h1 {
            color: #333;
            margin-bottom: 20px;
        }
        #game-container {
            background-color: #fff;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 400px;
            margin: 0 auto;
        }
        label {
            display: block;
            margin-bottom: 10px;
        }
        input {
            padding: 10px;
            margin-bottom: 20px;
            width: 100%;
            box-sizing: border-box;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
            width: 100%;
            border-radius: 5px;
        }
        button:hover {
            background-color: #45a049;
        }
        #resultMessage {
            margin-top: 20px;
            font-weight: bold;
            color: #000000
        }
    </style>
</head>
<body>

<div id="game-container">
    <label for="guessInput">Enter your guess (a binary number):</label>
    <input type="text" id="guessInput" placeholder="Enter binary number" autocomplete="off">
    <button onclick="checkNumber()">Check Number</button>
    <p id="resultMessage"></p>
</div>

<script>
    function checkNumber() {
        const guessInput = document.getElementById('guessInput');
        const resultMessage = document.getElementById('resultMessage');

        const guess = guessInput.value;
        if (guess === '100101') {
            resultMessage.textContent = 'Congratulations! You guessed the correct binary number: 100101';
        } else {
            resultMessage.textContent = 'Wrong Answer!';
        }
    }
</script>

</body>
</html>
