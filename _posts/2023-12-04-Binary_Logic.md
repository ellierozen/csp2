<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Binary Logic Gates</title>
    <style>
        input, select {
            margin: 10px;
        }
    </style>
</head>
<body>

<h1>Binary Logic Gates</h1>

<label for="inputA">Input A:</label>
<input type="checkbox" id="inputA">

<label for="inputB">Input B:</label>
<input type="checkbox" id="inputB">

<select id="gateType">
    <option value="and">AND Gate</option>
    <option value="or">OR Gate</option>
    <option value="not">NOT Gate</option>
</select>

<button onclick="calculate()">Calculate</button>

<h2>Output:</h2>
<div id="output"></div>

<script>
    function calculate() {
        const inputA = document.getElementById('inputA').checked;
        const inputB = document.getElementById('inputB').checked;
        const gateType = document.getElementById('gateType').value;
        let output;

        switch (gateType) {
            case 'and':
                output = inputA && inputB;
                break;
            case 'or':
                output = inputA || inputB;
                break;
            case 'not':
                output = !inputA;
                break;
            default:
                output = 'Invalid gate type';
        }

        document.getElementById('output').innerText = `Output: ${output}`;
    }
</script>

</body>
</html>
