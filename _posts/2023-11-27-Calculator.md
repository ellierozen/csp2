<style>
  .calculator-output {
    grid-column: span 4;
    grid-row: span 1;
    padding: 0.25em;
    font-size: 20px;
    border: 5px solid black;
    display: flex;
    align-items: center;
  }
</style>

<div id="animation">
  <div class="calculator-container">
    <div class="calculator-output" id="output">0</div>
    <div class="calculator-number" data-value="1">1</div>
    <div class="calculator-number" data-value="0">0</div>
    <div class="calculator-operation">+</div>
    <div class="calculator-number" data-value="1">1</div>
    <div class="calculator-number" data-value="0">0</div>
    <div class="calculator-operation">-</div>
    <div class="calculator-number" data-value="1">1</div>
    <div class="calculator-number" data-value="0">0</div>
    <div class="calculator-operation">*</div>
    <div class="calculator-clear">A/C</div>
    <div class="calculator-number" data-value="0">0</div>
    <div class="calculator-number" data-value=".">.</div>
    <div class="calculator-equals">=</div>
  </div>
</div>

<script>
  var firstNumber = null;
  var operator = null;
  var nextReady = true;
  const output = document.getElementById("output");
  const numbers = document.querySelectorAll(".calculator-number");
  const operations = document.querySelectorAll(".calculator-operation");
  const clear = document.querySelectorAll(".calculator-clear");
  const equals = document.querySelectorAll(".calculator-equals");

  numbers.forEach(button => {
    button.addEventListener("click", function() {
      number(button.getAttribute("data-value"));
    });
  });

  function number(value) {
    if (value !== ".") {
      if (nextReady) {
        output.innerHTML = value;
        if (value !== "0") {
          nextReady = false;
        }
      } else {
        output.innerHTML += value;
      }
    } else {
      if (output.innerHTML.indexOf(".") === -1) {
        output.innerHTML += value;
        nextReady = false;
      }
    }
  }

  operations.forEach(button => {
    button.addEventListener("click", function() {
      operation(button.textContent);
    });
  });

  function operation(choice) {
    if (firstNumber === null) {
      firstNumber = parseInt(output.innerHTML, 2);
      nextReady = true;
      operator = choice;
      return;
    }
    firstNumber = calculate(firstNumber, parseInt(output.innerHTML, 2));
    operator = choice;
    output.innerHTML = firstNumber.toString(2);
    nextReady = true;
  }

  function calculate(first, second) {
    let result = 0;
    switch (operator) {
      case "+":
        result = first + second;
        break;
      case "-":
        result = first - second;
        break;
      case "*":
        result = first * second;
        break;
      case "/":
        result = first / second;
        break;
      default:
        break;
    }
    return result;
  }

  equals.forEach(button => {
    button.addEventListener("click", function() {
      equal();
    });
  });

  function equal() {
    firstNumber = calculate(firstNumber, parseInt(output.innerHTML, 2));
    output.innerHTML = firstNumber.toString(2);
    nextReady = true;
  }

  clear.forEach(button => {
    button.addEventListener("click", function() {
      clearCalc();
    });
  });

  function clearCalc() {
    firstNumber = null;
    output.innerHTML = "0";
    nextReady = true;
  }
</script>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r119/three.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/vanta@0.5.5/dist/vanta.halo.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/vanta@0.5.5/dist/vanta.birds.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/vanta@0.5.5/dist/vanta.net.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/vanta@0.5.5/dist/vanta.rings.min.js"></script>

<script>
  var vantaInstances = {
    halo: VANTA.HALO,
    birds: VANTA.BIRDS,
    net: VANTA.NET,
    rings: VANTA.RINGS
  };

  var vantaInstance = vantaInstances[Object.keys(vantaInstances)[Math.floor(Math.random() * Object.keys(vantaInstances).length)]];

  vantaInstance({
    el: "#animation",
    mouseControls: true,
    touchControls: true,
    gyroControls: false
  });
</script>

