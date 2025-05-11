<!DOCTYPE html><html>
<head>
  <title>Crystal Game Predictor</title>
  <style>
    body { font-family: Arial; padding: 20px; background: #f4f4f4; }
    h2 { color: #333; }
    input, button { padding: 10px; margin: 10px 0; width: 100%; }
    #result { font-size: 18px; font-weight: bold; color: #005500; margin-top: 20px; }
  </style>
</head>
<body>
  <h2>Crystal Crystal - Player Win Predictor</h2>
  <label>Enter last results (e.g., P1,P2,P1,P2,P2):</label>
  <input type="text" id="historyInput" placeholder="P1,P2,P2,P1">
  <button onclick="predictWinner()">Predict</button>
  <div id="result"></div>  <script>
    function predictWinner() {
      let input = document.getElementById('historyInput').value.trim().toUpperCase();
      if (!input) return document.getElementById('result').innerText = 'Please enter some data!';

      let history = input.split(',').map(s => s.trim());
      let last3 = history.slice(-3);
      let p1 = last3.filter(p => p === 'P1').length;
      let p2 = last3.filter(p => p === 'P2').length;

      let result = '';
      if (p1 > p2) result = 'Prediction
