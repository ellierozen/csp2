---
hide: true
---
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
      background-color: #43719E!important;
    }
   .container {
      display: flex;
      justify-content: space-between; /* Adjust to space-around if needed */
      width: 80%; /* Adjust the width as needed */
      margin: auto; /* Center the container horizontally */
      margin-bottom: 20px;
    }
    .input-container {
      text-align: center; /* Center text within the container */
    }  
    #input1Container {
      margin-right: auto; /* Push Input 1 to the left */
    }
    #input2Container {
      margin-left: auto; /* Push Input 2 to the right */
    }
     .box {
      width: 70px;
      height: 70px;
      border: 1px solid #ccc;
      display: flex;
      align-items: center;
      justify-content: center;``
      cursor: pointer;
      margin-bottom: 5px; /* Add margin between input boxes */
    }
    #inputLabels {
      display: flex;
      flex-direction: row;
      justify-content: space-around;
      width: 100%;
      margin-bottom: 10px; /* Add margin between labels and input boxes */
    }
    #input1Label,
    #input2Label {
      text-align: center; /* Center text within the label */
    }
    #output {
      width: 70px;
      height: 70px;
      border: 1px solid #43719E;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #43719E;
      margin-bottom: 20px;
      /* Center the button horizontally and vertically */
      margin: auto;
    }
    #output img {
      width: 70px;
      height: 70px;
    }
    #logicOptions {
      display: flex;
      justify-content: space-around;
      width: 100%;
      background-color: #90C3D4;
      padding: 10px;
      margin-bottom: 20px;
    }
    #logicOptions {
      display: flex;
      justify-content: space-around;
      width: 100%;
      background-color: #90C3D4!important;
      padding: 30px;
      margin-bottom: 20px;
       font-size: 16px; 
    }
    #logicOptions button {
      padding: 30px;
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
  <div class="input-container" id="input1Container">
    <div id="input1Label">Input 1</div>
    <div id="input1" class="box" onclick="toggleBox('input1')">0</div>
  </div>
  <div class="input-container" id="input2Container">
    <div id="input2Label">Input 2</div>
    <div id="input2" class="box" onclick="toggleBox('input2')">0</div>
  </div>
</div>

<div id="output">
  <img id="outputImg" src="off.png" >
</div>

<div id="gateType" style="display: none;">AND</div>

<script>
const IMAGE_ON = "{{site.baseurl}}/images/on.png";
const IMAGE_OFF = "{{site.baseurl}}/images/off.png";

  let inputs = {
    input1: 0,
    input2: 0
  };

  // Define outputImg as a global variable
  let outputImg = document.getElementById("outputImg");

  function toggleBox(input) {
    inputs[input] = 1 - inputs[input];
    document.getElementById(input).innerText = inputs[input];
    console.log("Toggled", input, "to", inputs[input]);
    calculateOutput();
  }

    function calculateOutput() {
  // Get the selected logic gate type from the HTML element
    const gateType = document.getElementById("gateType").innerText.trim();

    // Call the logicGate function with inputs and gateType to get the result
    const result = logicGate(inputs.input1, inputs.input2, gateType);

    // Log the calculated output to the console
    console.log("Calculated output:", result);
    
    // Change the source of the image based on the logic gate result
    outputImg.src = result ? IMAGE_ON : IMAGE_OFF;

    // Update the input boxes to display '0' or '1'
    document.getElementById("input1").innerText = inputs.input1.toString();
    document.getElementById("input2").innerText = inputs.input2.toString();
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
        return false;
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
    calculateOutput(); // Trigger output calculation to update the image
  }
</script>

</body>
</html>