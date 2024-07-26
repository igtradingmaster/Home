
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Compact Calculator</title>
  <link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
  <style>
    h1{
      display: none;
      }
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #333;
    }
    .calculator-container {
      display: flex;
      width: 100vw;
      height: 100vh;
      background-color: #333;
      box-sizing: border-box;
    }
    .calculator {
      width: 50%;
      border-right: 1px solid #ced4da;
      padding: 20px;
      box-sizing: border-box;
      background-color: #000;
      color: white;
    }
    .calculator .form-control {
      text-align: right;
      font-size: 24px;
      border: 1px solid #ced4da;
      border-radius: 5px;
      margin-bottom: 20px;
    }
    .calculator button {
      width: 100%;
      height: 50px;
      font-size: 18px;
      padding: 0;
    }
    .saved-calculations {
      width: 50%;
      padding: 20px;
      box-sizing: border-box;
      background-color: #222;
      color: white;
      overflow-y: auto;
    }
    .saved-calculations h5 {
      font-size: 24px;
    }
    .saved-calculations .row {
      margin-bottom: 10px;
    }
    .modal-content {
      text-align: right;
    }
    .loader {
      border: 4px solid #f3f3f3;
      border-top: 4px solid #3498db;
      border-radius: 50%;
      width: 20px;
      height: 20px;
      animation: spin 1s linear infinite;
      display: inline-block;
      margin-left: 10px;
    }
    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }
    .delete-btn {
      cursor: pointer;
      color: red;
      margin-right: 10px;
    }
    .edit-btn {
      cursor: pointer;
      color: blue;
      margin-right: 10px;
    }
    .col-item {
      flex: 1;
      min-width: 100%;
      box-sizing: border-box;
      padding: 5px;
      border: 1px solid #ddd;
      border-radius: 4px;
      margin: 5px 0;
    }
    .col-item h6 {
      margin: 0;
      font-size: 18px;
    }

    /* Ensure layout only works on PC and laptops */
    @media (min-width: 1024px) {
      .calculator-container {
        display: flex;
      }
      .mobile-message {
        display: none;
      }
    }

    /* Show full screen message on mobile and tablets */
    @media (max-width: 1024px) {
      .calculator-container {
        display: none; /* Hide calculator layout on mobile and tablets */
      }
      .mobile-message {
        display: block;
        width: 100vw;
        height: 100vh;
        text-align: center;
        line-height: 100vh;
        background: #fff;
        font-size: 24px;
        color: #333;
      }
    }
    .block {
      display: block;
      -webkit-user-select: none; /* Chrome, Safari */
      -moz-user-select: none;    /* Firefox */
      -ms-user-select: none;     /* Internet Explorer/Edge */
      user-select: none;         /* Non-prefixed version, currently supported by Opera */
    }
    * {
      -webkit-user-select: none; /* Chrome, Safari */
      -moz-user-select: none;    /* Firefox */
      -ms-user-select: none;     /* Internet Explorer/Edge */
      user-select: none;         /* Non-prefixed version, currently supported by Opera */
    }
  </style>
</head>
<body>

  <div class="mobile-message">This website is optimized for PC and laptops only.</div>

  <div class="calculator-container">
    <!-- Calculator Section -->
    <div class="calculator">
      <input type="text" class="form-control" id="display" disabled>
      <div class="row">
        <div class="col-3 mb-1"><button class="btn btn-secondary" onclick="clearDisplay()">C</button></div>
        <div class="col-3 mb-1"><button class="btn btn-secondary" onclick="deleteLast()">DEL</button></div>
        <div class="col-3 mb-1"><button class="btn btn-secondary" onclick="appendToDisplay('%')">%</button></div>
        <div class="col-3 mb-1"><button class="btn btn-secondary" onclick="appendToDisplay('/')">/</button></div>

        <div class="col-3 mb-1"><button class="btn btn-light" onclick="appendToDisplay('7')">7</button></div>
        <div class="col-3 mb-1"><button class="btn btn-light" onclick="appendToDisplay('8')">8</button></div>
        <div class="col-3 mb-1"><button class="btn btn-light" onclick="appendToDisplay('9')">9</button></div>
        <div class="col-3 mb-1"><button class="btn btn-secondary" onclick="appendToDisplay('*')">*</button></div>

        <div class="col-3 mb-1"><button class="btn btn-light" onclick="appendToDisplay('4')">4</button></div>
        <div class="col-3 mb-1"><button class="btn btn-light" onclick="appendToDisplay('5')">5</button></div>
        <div class="col-3 mb-1"><button class="btn btn-light" onclick="appendToDisplay('6')">6</button></div>
        <div class="col-3 mb-1"><button class="btn btn-secondary" onclick="appendToDisplay('-')">-</button></div>

        <div class="col-3 mb-1"><button class="btn btn-light" onclick="appendToDisplay('1')">1</button></div>
        <div class="col-3 mb-1"><button class="btn btn-light" onclick="appendToDisplay('2')">2</button></div>
        <div class="col-3 mb-1"><button class="btn btn-light" onclick="appendToDisplay('3')">3</button></div>
        <div class="col-3 mb-1"><button class="btn btn-secondary" onclick="appendToDisplay('+')">+</button></div>

        <div class="col-6 mb-1"><button class="btn btn-light" onclick="appendToDisplay('0')">0</button></div>
        <div class="col-3 mb-1"><button class="btn btn-light" onclick="appendToDisplay('.')">.</button></div>
        <div class="col-3 mb-1"><button class="btn btn-primary" onclick="calculate()">=</button></div>
      </div>
    </div>

    <!-- Saved Calculations Section -->
    <div class="saved-calculations">
      <h5>Save Calculation</h5>
      <input type="text" class="form-control mb-2" id="nameInput" placeholder="Enter name">
      <button class="btn btn-success btn-block mb-2" onclick="saveCalculation()">Save</button>
      <h5>Saved Calculations</h5>
      <div class="row" id="savedList"></div>
      <h5>Total Calculations: <span id="totalCount">0</span></h5>
    </div>
  </div>

  <script>
    const display = document.getElementById('display');
    const nameInput = document.getElementById('nameInput');
    const savedList = document.getElementById('savedList');
    const totalCountElem = document.getElementById('totalCount');

    function appendToDisplay(value) {
      display.value += value;
    }

    function clearDisplay() {
      display.value = '';
    }

    function deleteLast() {
      display.value = display.value.slice(0, -1);
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch (e) {
        display.value = 'Error';
      }
    }

    function saveCalculation() {
      const name = nameInput.value.trim();
      const total = display.value;
      if (name && total !== 'Error') {
        const savedCalculations = JSON.parse(localStorage.getItem('savedCalculations')) || [];
        savedCalculations.push({ name, total });
        localStorage.setItem('savedCalculations', JSON.stringify(savedCalculations));
        nameInput.value = '';
        display.value = '';
        updateSavedList();
      }
    }

    function updateSavedList() {
      savedList.innerHTML = '';
      const savedCalculations = JSON.parse(localStorage.getItem('savedCalculations')) || [];
      savedCalculations.forEach((calc, index) => {
        savedList.innerHTML += `
          <div class="col-item">
            <h6>${calc.name} - ${calc.total}</h6>
            <span class="edit-btn" onclick="editCalculation(${index})">Edit</span>
            <span class="delete-btn" onclick="deleteCalculation(${index})">Delete</span>
          </div>
        `;
      });
      totalCountElem.textContent = savedCalculations.length;
    }

    function editCalculation(index) {
      const savedCalculations = JSON.parse(localStorage.getItem('savedCalculations')) || [];
      const name = prompt('Enter new name:', savedCalculations[index].name);
      if (name !== null) {
        savedCalculations[index].name = name;
        localStorage.setItem('savedCalculations', JSON.stringify(savedCalculations));
        updateSavedList();
      }
    }

    function deleteCalculation(index) {
      const savedCalculations = JSON.parse(localStorage.getItem('savedCalculations')) || [];
      savedCalculations.splice(index, 1);
      localStorage.setItem('savedCalculations', JSON.stringify(savedCalculations));
      updateSavedList();
    }

    // Initial load
    updateSavedList();
  </script>
</body>
