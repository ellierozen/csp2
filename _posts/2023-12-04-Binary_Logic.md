
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cool Binary Logic Gates</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            text-align: center;
            margin-top: 50px;
        }

        h1 {
            color: #ffe79b;
        }

        label {
            display: block;
            margin-top: 20px;
        }

        #gate-container {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-top: 20px;
        }

        .gate {
            margin: 0 20px;
        }

        #output {
            margin-top: 20px;
            font-size: 18px;
            color: #333;
        }

        button {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 16px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<h1>Cool Binary Logic Gates</h1>

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

<div id="output"></div>

<div id="gate-container">
    <div id="and-gate" class="gate"></div>
    <div id="or-gate" class="gate"></div>
    <div id="not-gate" class="gate"></div>
</div>

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

        // Update gate graphics
        document.getElementById('and-gate').innerHTML = getAndGateSVG(inputA, inputB, output);
        document.getElementById('or-gate').innerHTML = getOrGateSVG(inputA, inputB, output);
        document.getElementById('not-gate').innerHTML = getNotGateSVG(inputA, output);
    }

    function getAndGateSVG(inputA, inputB, output) {
        return `
            <svg height="100" width="100">
                <circle cx="50" cy="30" r="20" stroke="#333" stroke-width="2" fill="#fff"/>
                <line x1="30" y1="10" x2="30" y2="50" style="stroke:#333;stroke-width:2"/>
                <line x1="30" y1="50" x2="70" y2="50" style="stroke:#333;stroke-width:2"/>
                <line x1="70" y1="50" x2="70" y2="10" style="stroke:#333;stroke-width:2"/>
                <line x1="70" y1="10" x2="30" y2="10" style="stroke:#333;stroke-width:2"/>
                <text x="50" y="25" font-size="14" text-anchor="middle" fill="#333">${inputA ? '1' : '0'}</text>
                <text x="50" y="45" font-size="14" text-anchor="middle" fill="#333">${inputB ? '1' : '0'}</text>
                <text x="50" y="75" font-size="14" text-anchor="middle" fill="#333">${output ? '1' : '0'}</text>
            </svg>
        `;
    }

    function getOrGateSVG(inputA, inputB, output) {
        return `
            <svg height="100" width="100">
                <circle cx="50" cy="30" r="20" stroke="#333" stroke-width="2" fill="#fff"/>
                <line x1="30" y1="10" x2="30" y2="50" style="stroke:#333;stroke-width:2"/>
                <line x1="30" y1="50" x2="70" y2="50" style="stroke:#333;stroke-width:2"/>
                <line x1="70" y1="50" x2="70" y2="10" style="stroke:#333;stroke-width:2"/>
                <line x1="70" y1="10" x2="30" y2="10" style="stroke:#333;stroke-width:2"/>
                <text x="50" y="25" font-size="14" text-anchor="middle" fill="#333">${inputA ? '1' : '0'}</text>
                <text x="50" y="45" font-size="14" text-anchor="middle" fill="#333">${inputB ? '1' : '0'}</text>
                <text x="50" y="75" font-size="14" text-anchor="middle" fill="#333">${output ? '1' : '0'}</text>
            </svg>
        `;
    }

    function getNotGateSVG(inputA, output) {
        return `
            <svg height="100" width="100">
                <circle cx="50" cy="30" r="20" stroke="#333" stroke-width="2" fill="#fff"/>
                <line x1="30" y1="10" x2="30" y2="50" style="stroke:#333;stroke-width:2"/>
                <line x1="30" y1="50" x2="70" y2="50" style="stroke:#333;stroke-width:2"/>
                <line x1="70" y1="50" x2="70" y2="10" style="stroke:#333;stroke-width:2"/>
                <line x1="70" y1="10" x2="30" y2="10" style="stroke:#333;stroke-width:2"/>
                <text x="50" y="25" font-size="14" text-anchor="middle"

