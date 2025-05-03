<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>ليدر دو كم - شحن ببجي</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #121212;
      color: #fff;
      padding: 20px;
      direction: rtl;
    }
    .container {
      max-width: 400px;
      margin: auto;
      background: #1e1e1e;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 0 10px #333;
    }
    input, select, button {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 8px;
      border: none;
      font-size: 16px;
    }
    button {
      background-color: #ffcc00;
      color: #000;
      font-weight: bold;
      cursor: pointer;
    }
    .discount {
      color: #0f0;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>شحن شدات ببجي - ليدر دو كم</h2>

    <label for="pubgId">ID اللاعب:</label>
    <input type="text" id="pubgId" placeholder="مثال: 123456789" />

    <label for="amount">عدد الشدات:</label>
    <select id="amount">
      <option value="1.99">60 شدة - $1.99</option>
      <option value="9.99">660 شدة - $9.99</option>
      <option value="24.99">1800 شدة - $24.99</option>
    </select>

    <label for="code">كود الخصم:</label>
    <input type="text" id="code" placeholder="أدخل كود الخصم" />

    <p id="discountInfo" class="discount"></p>

    <label for="payment">طريقة الدفع:</label>
    <select id="payment">
      <option value="libyana">رصيد لبيانا</option>
      <option value="madar">رصيد المدار</option>
    </select>

    <button onclick="calculate()">شحن الآن</button>
  </div>

  <script>
    function calculate() {
      const amount = parseFloat(document.getElementById("amount").value);
      const code = document.getElementById("code").value.trim().toUpperCase();
      const discountInfo = document.getElementById("discountInfo");

      let finalPrice = amount;
      if (code === "CJ") {
        finalPrice = amount * 0.9;
        discountInfo.innerText = `تم تطبيق كود الخصم CJ - السعر بعد الخصم: $${finalPrice.toFixed(2)}`;
      } else if (code) {
        discountInfo.innerText = "كود الخصم غير صالح";
      } else {
        discountInfo.innerText = "";
      }
    }
  </script>
</body>
</html>
