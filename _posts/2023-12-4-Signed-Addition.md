<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }
        .container {
            background-color: #3498db;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 400px; 
            margin: auto;
        }
        h1 {
            color: #001f3f; 
        }
        label {
            background-color: #3498db; 
            color: #fff; 
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            display: inline-block; 
            margin-bottom: 10px; 
        }
        label:hover {
            background-color: #2980b9; 
        }
        input {
            padding: 8px;
            margin-bottom: 10px;
        }
        button {
            background-color: #0000; 
            color: #fff; 
            padding: 10px 20px;
            border: #00008B;
            border-radius: 5px;
            cursor: pointer;
        }
        p {
            font-weight: bold;
            color: #008000;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Signed Addition</h1>
    <p>w/ Binary Output</p>
    <label for="num1">Enter the first number: </label>
    <input type="number" id="num1">
    <label for="num2">Enter the second number: </label>
    <input type="number" id="num2">
     <button onclick="performSignedAddition()" style="background-color: black; color: white;">Add</button>
    <p id="result">Result: </p>
</div>

<script>
    function performSignedAddition() {
        // gets the values from the input fields
        var num1 = parseInt(document.getElementById("num1").value);
        var num2 = parseInt(document.getElementById("num2").value);

        // performs signed addition
        var result = num1 + num2;

        // displays the result in binary
        var binaryResult = (result >>> 0).toString(2); // ensures positive conversion 
        document.getElementById("result").innerText = "Result (Binary): " + binaryResult;
    }
</script>

</body>
</html>