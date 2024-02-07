---
hide: true
---
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Signed Binary Addition</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }
        .container {
            background-color: #3498db; /* Blue color for the container */
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 400px; /* Adjust the width as needed */
            margin: auto;
        }
        h1 {
            color: #001f3f; /* Dark blue color for the title */
        }
        label {
            background-color: #3498db; /* Blue color for labels */
            color: #fff; /* Text color */
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            display: inline-block; /* Make labels inline-block to align properly */
            margin-bottom: 10px; /* Add margin between labels and input fields */
        }
        label:hover {
            background-color: #2980b9; /* Darker blue on hover */
        }
        input {
            padding: 8px;
            margin-bottom: 10px;
        }
        button {
            background-color: #3498db; /* Blue color for the button */
            color: #fff; /* Text color */
            padding: 10px 20px;
            border: #00008B;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Signed Binary Addition</h1>
    <label for="num1">Enter the first binary number: </label>
    <input type="text" id="num1" placeholder="Enter binary number">
    <label for="num2">Enter the second binary number: </label>
    <input type="text" id="num2" placeholder="Enter binary number">
    <button onclick="performBinaryAddition()">Add</button>
    <p id="result">Result: </p>
</div>

<script>
    function performBinaryAddition() {
        // Get the values from the input fields
        var num1 = document.getElementById("num1").value;
        var num2 = document.getElementById("num2").value;

        // Validate binary input
        if (!/^[01]+$/.test(num1) || !/^[01]+$/.test(num2)) {
            alert("Please enter valid binary numbers.");
            return;
        }

        // Perform binary addition
        var decimalResult = parseInt(num1, 2) + parseInt(num2, 2);
        var binaryResult = decimalResult.toString(2);

        // Display the result
        document.getElementById("result").innerText = "Result: " + binaryResult;
    }
</script>

</body>
</html>