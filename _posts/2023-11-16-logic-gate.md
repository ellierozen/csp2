
<html lang="en">
<head>
  <!-- Set the character set for the document -->
  <meta charset="UTF-8">
  <!-- Define the viewport settings for responsive design -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- Add styles for the page layout and elements -->
  <style>
    body {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
      background-color: #B5CEFF; /* Set background color */
    }
    .container {
      display: flex;
      justify-content: space-between;
      margin-bottom: 20px;
    }
    .box {
      width: 50px;
      height: 50px;
      border: 1px solid #ccc;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
    }
    #output {
      width: 50px;
      height: 50px;
      border: 1px solid #000;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #ccc;
      margin-bottom: 20px;
    }
    #logicOptions {
      display: flex;
      justify-content: space-around;
      width: 100%;
      background-color: #90C3D4; /* Set logic options background color */
      padding: 10px;
      margin-bottom: 20px;
    }
    #logicOptions button {
      padding: 10px;
      cursor: pointer;
    }
  </style>
  <!-- Set the title of the HTML document -->
  <title>Logic Gates Demo</title>
</head>
<body>

<!-- Logic options at the top of the page -->
<div id="logicOptions">
  <button onclick="changeGate('AND')" style="background-color: #6F98A8;">AND Gate</button>
  <button onclick="changeGate('OR')" style="background-color: #587B8E;">OR Gate</button>
  <button onclick="changeGate('NOR')" style="background-color: #405E73;">NOR Gate</button>
  <button onclick="changeGate('XOR')" style="background-color: #284057;">XOR Gate</button>
  <button onclick="changeGate('NAND')" style="background-color: #12233E;">NAND Gate</button>
  <button onclick="changeGate('XNOR')" style="background-color: #001845;">XNOR Gate</button>
</div>

<!-- Container for input boxes -->
<div class="container">
  <!-- Input box 1 -->
  <div id="input1" class="box" onclick="toggleBox('input1')">0</div>
  <!-- Input box 2 -->
  <div id="input2" class="box" onclick="toggleBox('input2')">0</div>
</div>

<!-- Output box -->
<div id="output" onclick="calculateOutput()">0</div>

<div id="gateType" style="display: none;">AND</div>

<script>
  // Object to store input values
  let inputs = {
    input1: 0,
    input2: 0
  };

  // Function to toggle the state of an input box
  function toggleBox(input) {
    // Toggle the value (0 to 1, 1 to 0)
    inputs[input] = 1 - inputs[input];
    // Update the displayed value in the input box
    document.getElementById(input).innerText = inputs[input];
    console.log("Toggled", input, "to", inputs[input]);
    calculateOutput();
  }

  // Function to calculate the logic gate output based on input values
  function calculateOutput() {
    const gateType = document.getElementById("gateType").innerText.trim();
    const result = logicGate(inputs.input1, inputs.input2, gateType);
    console.log("Calculated output:", result);
    document.getElementById("output").innerText = result;

    // Change the color of the output box based on logic gate type
    const output = document.getElementById("output");
    if (result) {
      output.style.backgroundColor = "yellow";
    } else {
      output.style.backgroundColor = "#ccc"; // Reset the background color
    }
  }

  function logicGate(input1, input2, gateType) {
    switch (gateType) {
      case 'AND':
        return input1 && input2;
      case 'OR':
        return input1 || input2;
      case 'NOR':
        return !(input1 || input2);
      case 'XOR':
        return (input1 || input2) && !(input1 && input2);
      case 'NAND':
        return !(input1 && input2);
      case 'XNOR':
        return !(input1 || input2) || (input1 && input2);
      default:
        return 0;
    }
  }
</script>

<script>
  // Function to change the logic gate type
  function changeGate(gateType) {
    // Update the displayed gate type
    document.getElementById("gateType").innerText = gateType;
    // Reset inputs and output
    inputs = { input1: 0, input2: 0 };
    document.getElementById("input1").innerText = '0';
    document.getElementById("input2").innerText = '0';
    document.getElementById("output").innerText = '0';

    // Reset the background color of the output box
    document.getElementById("output").style.backgroundColor = "#ccc";
  }
</script>

</body>
</html>
