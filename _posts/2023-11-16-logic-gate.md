
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Logic Gates Demo</title>
  <style>
    body {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
      background-color: #B5CEFF;
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
      background-color: #90C3D4;
      padding: 10px;
      margin-bottom: 20px;
    }
    #logicOptions button {
      padding: 10px;
      cursor: pointer;
      border: none;
      color: white;
      border-radius: 5px;
    }
    #logicOptions button:hover {
      opacity: 0.8;
    }
    /* Highlight the active button */
    #logicOptions button.active {
      background-color: #ADD8E6 !important;
    }
  </style>
</head>
<body>

<div id="logicOptions">
  <button onclick="changeGate('AND')" id="andButton" class="active" style="background-color: #6F98A8;">AND Gate</button>
  <button onclick="changeGate('OR')" id="orButton" style="background-color: #587B8E;">OR Gate</button>
  <button onclick="changeGate('NOR')" id="norButton" style="background-color: #405E73;">NOR Gate</button>
  <button onclick="changeGate('XOR')" id="xorButton" style="background-color: #284057;">XOR Gate</button>
  <button onclick="changeGate('NAND')" id="nandButton" style="background-color: #12233E;">NAND Gate</button>
  <button onclick="changeGate('XNOR')" id="xnorButton" style="background-color: #001845;">XNOR Gate</button>
</div>

<div class="container">
  <div id="input1" class="box" onclick="toggleBox('input1')">0</div>
  <div id="input2" class="box" onclick="toggleBox('input2')">0</div>
</div>

<div id="output" onclick="calculateOutput()">0</div>

<div id="gateType" style="display: none;">AND</div>

<script>
  let inputs = {
    input1: 0,
    input2: 0
  };

  function toggleBox(input) {
    inputs[input] = 1 - inputs[input];
    document.getElementById(input).innerText = inputs[input];
    console.log("Toggled", input, "to", inputs[input]);
    calculateOutput();
  }

  function calculateOutput() {
    const gateType = document.getElementById("gateType").innerText.trim();
    const result = logicGate(inputs.input1, inputs.input2, gateType);
    console.log("Calculated output:", result);
    document.getElementById("output").innerText = result;

    const output = document.getElementById("output");
    output.style.backgroundColor = result ? "yellow" : "#ccc";
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
  function changeGate(gateType) {
    // Remove the 'active' class from all buttons
    const buttons = document.querySelectorAll("#logicOptions button");
    buttons.forEach(button => button.classList.remove("active"));

    // Add the 'active' class to the clicked button
    const activeButton = document.getElementById(`${gateType.toLowerCase()}Button`);
    activeButton.classList.add("active");

    document.getElementById("gateType").innerText = gateType;
    inputs = { input1: 0, input2: 0 };
    document.getElementById("input1").innerText = '0';
    document.getElementById("input2").innerText = '0';
    document.getElementById("output").innerText = '0';
    document.getElementById("output").style.backgroundColor = "#ccc";
  }
</script>

</body>
</html>
