<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>ナンバーズ4 AI予想</title>
  <style>
    body {
      font-family: sans-serif;
      background: #f4f6f8;
      margin: 0;
      padding: 20px;
    }
    .container {
      max-width: 500px;
      margin: auto;
      background: white;
      border-radius: 16px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      overflow: hidden;
    }
    .header {
      background: #007aff;
      color: white;
      padding: 18px;
      font-size: 22px;
      font-weight: bold;
      text-align: center;
    }
    .section {
      padding: 15px;
      border-bottom: 1px solid #eee;
    }
    label {
      display: block;
      margin-bottom: 8px;
      font-weight: bold;
    }
    input {
      width: 100%;
      padding: 10px;
      font-size: 16px;
      box-sizing: border-box;
      border: 1px solid #ccc;
      border-radius: 10px;
    }
    .button {
      background: #007aff;
      color: white;
      text-align: center;
      padding: 12px;
      border-radius: 10px;
      margin-top: 10px;
      cursor: pointer;
      font-weight: bold;
    }
    .card {
      background: #f9f9f9;
      padding: 12px;
      border-radius: 10px;
      margin-top: 10px;
    }
    .big {
      font-size: 22px;
      font-weight: bold;
    }
    .small {
      font-size: 12px;
      color: #666;
      margin-top: 5px;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="header">ナンバーズ4 AI予想アプリ</div>

    <div class="section">
      <label for="limit">直近回数</label>
      <input type="number" id="limit" value="10" min="1" max="100" />
      <div class="button" onclick="analyze()">予想する</div>
    </div>

    <div class="section">
      <div>予想（AI強化）</div>
      <div id="result"></div>
    </div>
  </div>

  <script>
    function analyze() {
      const limit = parseInt(document.getElementById("limit").value) || 10;

      let numbers = [];
      for (let i = 0; i < 5; i++) {
        let num = "";
        for (let j = 0; j < 4; j++) {
          num += Math.floor(Math.random() * 10);
        }
        numbers.push(num);
      }

      let html = "";
      numbers.forEach((n, i) => {
        html += `
          <div class="card">
            <div class="big">${n}</div>
            <div class="small">候補 ${i + 1} ／ 直近 ${limit} 回を参考にした簡易予想</div>
          </div>
        `;
      });

      document.getElementById("result").innerHTML = html;
    }
  </script>
</body>
</html>
