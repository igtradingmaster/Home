<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Stock Market Website</title>
  <!-- Chart.js -->
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    body {
      background-color: silver;
      font-family: Arial, sans-serif;
    }

    .container {
      max-width: 800px;
      margin: 0 auto;
      padding: 20px;
    }

    .trade-prices {
      border: 1px solid #ccc;
      border-radius: 5px;
      background-color: #f9f9f9;
      padding: 10px;
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }

    .trade-price {
      flex: 1 1 200px; /* Adjust this value as needed */
      border: 1px solid #ccc;
      border-radius: 5px;
      padding: 10px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .trade-price strong {
      margin-bottom: 5px;
    }

    .btn {
      padding: 6px 10px;
      font-size: 14px;
      cursor: pointer;
      border: none;
      border-radius: 4px;
      background-color: #007bff;
      color: #fff;
      margin-top: 5px;
    }

    .btn:hover {
      background-color: #0056b3;
    }

    .profit {
      color: green;
    }

    .loss {
      color: red;
    }

    .modal {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.5);
      display: none;
      justify-content: center;
      align-items: center;
    }

    .modal-content {
      background-color: #fff;
      border-radius: 5px;
      padding: 20px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
    }

    .modal-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid #ccc;
      padding-bottom: 10px;
      margin-bottom: 10px;
    }

    .modal-header h5 {
      margin: 0;
    }

    .modal-footer {
      display: flex;
      justify-content: flex-end;
      border-top: 1px solid #ccc;
      padding-top: 10px;
      margin-top: 10px;
    }

    .close {
      cursor: pointer;
    }

    .popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: #fff;
      padding: 20px;
      border-radius: 5px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
    }
  </style>
</head>
<body>
    
<div class="container">
  <center><h1> CHART</h1></center>
  <div class="row mt-3">
    <div class="col-md-6">
      <canvas id="lineChart"></canvas>
    </div>
    <div class="col-md-6">
      <canvas id="barChart"></canvas>
    </div>
  </div>
  <div class="row mt-3">
    <div class="col-md-12">
      <center><h2> TRADE PRICES</h2></center>
      <div id="tradePrices" class="trade-prices"></div>
    </div>
  </div>
  <div class="row mt-3">
    <div class="col-md-12">
      <center><button class="btn" id="portfolioBtn">Portfolio</button></center>
    </div>
  </div>
</div>

<!-- Portfolio Modal -->
<div id="portfolioModal" class="modal">
  <div class="modal-content">
    <div class="modal-header">
      <h5 class="modal-title">User Portfolio</h5>
      <button type="button" class="close" onclick="closePortfolioModal()">&times;</button>
    </div>
    <div class="modal-body" id="portfolioContent">
      <!-- Portfolio content will be added here -->
    </div>
    <div class="modal-footer">
      <button type="button" class="btn" onclick="closePortfolioModal()">Close</button>
    </div>
  </div>
</div>

<!-- Popup -->
<div id="popup" class="popup">
  <p id="popupMessage">Hey Welcome Friends...!!</p>
  <button class="btn" onclick="closePopup()">Close</button>
</div>

<script>
  // Initial account balance for the user
  let userBalance = 10000;
  let userPortfolio = []; // Array to store user's bought stocks

  // Companies and their initial trade prices
  let companies = ['TATA', 'Reliance', 'ONGC', 'Coal India', 'Tata Motors', 'Bajaj Auto', 'HCL Technologies', 'TCS', 'Cipla', 'Bajaj Finance', 'BPCL', 'ICICI Bank', 'Infosys', 'UPL', 'Adani Ports'];
  let tradePrices = [600, 2200, 120, 150, 300, 4000, 900, 3200, 800, 5000, 250, 700, 2100, 400, 600]; // Sample trade prices

  const lineChartCanvas = document.getElementById('lineChart').getContext('2d');
  const barChartCanvas = document.getElementById('barChart').getContext('2d');

  const lineChart = new Chart(lineChartCanvas, {
    type: 'line',
    data: {
      labels: companies,
      datasets: [{
        label: 'Stock Price',
        backgroundColor: 'rgba(255, 99, 132, 0.2)',
        borderColor: 'rgba(255, 99, 132, 1)',
        borderWidth: 1,
        data: tradePrices,
      }]
    },
    options: {
      responsive: true,
      plugins: {
        title: {
          display: true,
          text: 'Line Chart'
        }
      }
    }
  });

  const barChart = new Chart(barChartCanvas, {
    type: 'bar',
    data: {
      labels: companies,
      datasets: [{
        label: 'Stock Volume',
        backgroundColor: 'rgba(54, 162, 235, 0.2)',
        borderColor: 'rgba(54, 162, 235, 1)',
        borderWidth: 1,
        data: tradePrices, // You can update this with appropriate volume data if available
      }]
    },
    options: {
      responsive: true,
      plugins: {
        title: {
          display: true,
          text: 'Bar Chart'
        }
      }
    }
  });

  /// Function to update trade prices with random colors
function updateTradePrices() {
  let tradePricesHtml = '';
  for (let i = 0; i < companies.length; i++) {
    let stockIndex = userPortfolio.findIndex(item => item.company === companies[i]);
    let profitLoss = stockIndex !== -1 ? userPortfolio[stockIndex].price - tradePrices[i] : 0;
    let profitLossClass = profitLoss >= 0 ? 'profit' : 'loss';

    // Generating random color
    let randomColor = '#' + Math.floor(Math.random()*16777215).toString(16);

    tradePricesHtml += `<div class="trade-price" style="border-color: ${randomColor};">
                          <strong>${companies[i]}</strong>
                          <p>${tradePrices[i]}</p>
                          <span class="${profitLossClass}" style="color: ${randomColor};">${profitLoss}</span>
                          <button class="btn btn-buy" onclick="buyStock(${i})">Buy</button>`;
    if (stockIndex !== -1) {
      tradePricesHtml += `<button class="btn btn-sell" onclick="sellStock(${i})">Sell</button>`;
    }
    tradePricesHtml += `</div>`;
  }
  document.getElementById('tradePrices').innerHTML = tradePricesHtml;
}

// Update trade prices with random colors every second
setInterval(updateTradePrices, 1000);


  // Function to update chart data (simulated for demonstration)
  function updateChartData() {
    // Update trade prices with random values
    for (let i = 0; i < tradePrices.length; i++) {
      tradePrices[i] = Math.floor(Math.random() * 5000);
    }
    // Update the charts
    lineChart.data.datasets[0].data = tradePrices;
    barChart.data.datasets[0].data = tradePrices;
    lineChart.update();
    barChart.update();

    // Update trade prices display
    updateTradePrices();
  }

  // Function to buy stock
  function buyStock(index) {
    if (userBalance >= tradePrices[index]) {
      userBalance -= tradePrices[index];
      userPortfolio.push({company: companies[index], price: tradePrices[index], time: new Date().toLocaleString()});
      updateLocalStorage();
      updateTradePrices();
      alert(`You bought ${companies[index]} stock for ${tradePrices[index]}. Your remaining balance is ${userBalance}`);
    } else {
      alert('Insufficient balance to buy this stock.');
    }
  }

  // Function to sell stock
  function sellStock(index) {
    let stockIndex = userPortfolio.findIndex(item => item.company === companies[index]);
    if (stockIndex !== -1) {
      let profitLoss = tradePrices[index] - userPortfolio[stockIndex].price;
      if (profitLoss >= 0) {
        userBalance += tradePrices[index];
        userPortfolio.splice(stockIndex, 1);
        updateLocalStorage();
        updateTradePrices();
        alert(`You sold ${companies[index]} stock for ${tradePrices[index]}. Your remaining balance is ${userBalance}. Profit/Loss: ${profitLoss}`);
      } else {
        alert(`You can't sell ${companies[index]} stock at a loss.`);
      }
    }
  }

  // Function to exit trade
  function exitTrade(index) {
    let stockIndex = userPortfolio.findIndex(item => item.company === companies[index]);
    if (stockIndex !== -1) {
      let profitLoss = tradePrices[index] - userPortfolio[stockIndex].price;
      if (profitLoss >= 0) {
        userBalance += tradePrices[index];
        userPortfolio.splice(stockIndex, 1);
        updateLocalStorage();
        updateTradePrices();
        alert(`You exited ${companies[index]} trade. Your remaining balance is ${userBalance}. Profit: ${profitLoss}`);
      } else {
        alert(`You can't exit ${companies[index]} trade at a loss.`);
      }
    }
  }

  // Function to update local storage with user portfolio data
  function updateLocalStorage() {
    localStorage.setItem('userPortfolio', JSON.stringify(userPortfolio));
    localStorage.setItem('userBalance', userBalance);
  }

  // Function to display user portfolio
  function displayPortfolio() {
    const storedPortfolio = JSON.parse(localStorage.getItem('userPortfolio'));
    const storedBalance = localStorage.getItem('userBalance');
    if (storedPortfolio && storedBalance) {
      userPortfolio = storedPortfolio;
      userBalance = parseFloat(storedBalance);
      let portfolioHtml = '';
      let lossHistory = 0;
      let profitHistory = 0;
      userPortfolio.forEach(stock => {
        let profitLoss = tradePrices[companies.indexOf(stock.company)] - stock.price;
        if (profitLoss >= 0) {
          profitHistory += profitLoss;
        } else {
          lossHistory += profitLoss;
        }
        portfolioHtml += `<div><strong>${stock.company} (${stock.time}):</strong> ${stock.price}</div>`;
        portfolioHtml += `<div>Exit: <button class="btn btn-exit" onclick="exitTrade(${companies.indexOf(stock.company)})">Exit</button></div>`;
      });
      portfolioHtml += `<p>Available Balance: ${userBalance.toFixed(2)}</p>`;
      portfolioHtml += `<p>Loss History: ${lossHistory}</p>`;
      portfolioHtml += `<p>Profit History: ${profitHistory}</p>`;
      document.getElementById('portfolioContent').innerHTML = portfolioHtml;
      document.getElementById('portfolioModal').style.display = 'flex';
    } else {
      alert('No portfolio data found.');
    }
  }

  // Function to close portfolio modal
  function closePortfolioModal() {
    document.getElementById('portfolioModal').style.display = 'none';
  }

  // Function to show popup message
  function showPopup(message) {
    document.getElementById('popupMessage').innerText = message;
    document.getElementById('popup').style.display = 'block';
  }

  // Function to close popup
  function closePopup() {
    document.getElementById('popup').style.display = 'none';
  }

  // Event listener for portfolio button
  document.getElementById('portfolioBtn').addEventListener('click', displayPortfolio);

  // Update chart data every 3 seconds
  setInterval(updateChartData, 3000);

  // Initial update
  updateTradePrices();
</script>

</body>
</html>
