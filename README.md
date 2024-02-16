<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>UPI Payment</title>
<style>
  body {
    font-family: Arial, sans-serif;
    text-align: center;
  }
  #scanner-img {
    width: 200px; /* Adjust the size as needed */
    height: auto;
  }
  #timer {
    font-size: 18px;
    margin-top: 10px;
  }
</style>
</head>
<body>
  <h1>UPI Payment</h1>
  <button id="scanner-btn" onclick="startScanner()">Scan QR Code</button>
  <br>
  <img src="C:\Users\vedbh\Downloads\payment.jpg" id="scanner-img" style="display: none;">
  <div id="timer"></div>

<script>
  function startScanner() {
    document.getElementById('scanner-img').style.display = 'inline';
    document.getElementById('scanner-btn').style.display = 'none';
    var timer = 600; // 10 minutes in seconds
    var countdown = setInterval(function() {
      timer--;
      var minutes = Math.floor(timer / 60);
      var seconds = timer % 60;
      document.getElementById('timer').innerHTML = 'Scanner available for ' + minutes + ' minutes and ' + seconds + ' seconds.';
      if (timer <= 0) {
        clearInterval(countdown);
        document.getElementById('scanner-img').style.display = 'none';
        document.getElementById('scanner-btn').style.display = 'inline';
        document.getElementById('timer').innerHTML = 'Scanner session expired. Please click to regenerate.';
      }
    }, 1000);
  }
</script>

</body>
</html>
