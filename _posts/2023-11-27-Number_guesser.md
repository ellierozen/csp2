<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Binary Number Guesser</title>
    <style>
        /* Your existing CSS styles */
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
    function generateRandomBinaryNumber() {
        // Generate a random binary number of length 6 (you can change the length as needed)
        return Math.floor(Math.random() * (Math.pow(2, 6))).toString(2).padStart(6, '0');
    }

    function checkNumber() {
        const guessInput = document.getElementById('guessInput');
        const resultMessage = document.getElementById('resultMessage');

        const guess = guessInput.value;
        const correctNumber = generateRandomBinaryNumber();

        if (guess === correctNumber) {
            resultMessage.textContent = `Congratulations! You guessed the correct binary number: ${correctNumber}`;
        } else {
            resultMessage.textContent = `Wrong Answer! The correct binary number was: ${correctNumber}`;
        }
    }
</script>

</body>
</html>
