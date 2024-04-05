<script>
    let firstOperand = '';
    let secondOperand = '';
    let operator = '';
    let result = '';
  
    function calculate() {
      const num1 = parseFloat(firstOperand);
      const num2 = parseFloat(secondOperand);
  
      switch (operator) {
        case '+':
          result = num1 + num2;
          break;
        case '-':
          result = num1 - num2;
          break;
        case '*':
          result = num1 * num2;
          break;
        case '/':
          result = num1 / num2;
          break;
        default:
          result = '';
      }
    }
  
    function clear() {
      firstOperand = '';
      secondOperand = '';
      operator = '';
      result = '';
    }
  </script>
  
  <style>
    .calculator-button {
      padding: 10px;
      margin: 5px;
      font-size: 16px;
      border: none;
      border-radius: 3px;
      cursor: pointer;
      width: 50px;
      height: 50px;
    }
  
    .button-add {
      background-color: #ff9ff3;
      color: white;
    }
  
    .button-subtract {
      background-color: #48dbfb;
      color: white;
    }
  
    .button-multiply {
      background-color: #1dd1a1;
      color: white;
    }
  
    .button-divide {
      background-color: #feca57;
      color: white;
    }
  
    .button-equals {
      background-color: #ff6b6b;
      color: white;
         font-size: 2em;
         width: 100px;
         height: 60px;

    }
  
    .button-clear {
      background-color: #576574;
      color: white;
      font-size: 2em;
         width: 200px;
         height: 60px;

    }
    .result {
  font-size: 2em;
  border: 2px solid #ccc;
  padding: 10px;
  margin-top: 10px;
}

  </style>
  
  <div>
    <input type="text" bind:value={firstOperand}>
    <input type="text" bind:value={secondOperand}>
    <button class="calculator-button button-add" on:click={() => { operator = '+' }}>+</button>
    <button class="calculator-button button-subtract" on:click={() => { operator = '-' }}>-</button>
    <button class="calculator-button button-multiply" on:click={() => { operator = '*' }}>*</button>
    <button class="calculator-button button-divide" on:click={() => { operator = '/' }}>/</button>
    <button class="calculator-button button-equals" on:click={calculate}>=</button>
    <button class="calculator-button button-clear" on:click={clear}>Стереть</button>
  </div>
  
   <div class="result">
    {result}
  </div>
  