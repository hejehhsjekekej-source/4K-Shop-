# 4K-Shop
<!DOCTYPE html>
<html lang="lo">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>4K Shop Demo</title>
  <style>
    body { font-family: Arial, sans-serif; background-color: #f2f2f2; padding: 20px; }
    .container { max-width: 400px; margin: auto; background: white; padding: 20px; border-radius: 10px; box-shadow: 0 0 10px rgba(0,0,0,0.1); }
    button { padding: 10px 20px; margin-top: 10px; border: none; background-color: #4CAF50; color: white; border-radius: 5px; cursor: pointer; }
    button:hover { background-color: #45a049; }
    select, input { width: 100%; padding: 10px; margin-top: 10px; }
    .message { margin-top: 20px; color: blue; font-weight: bold; }
  </style>
</head>
<body>
  <div class="container">
    <h2>4K Shop - ເລືອກແພັກເກມ</h2>
    <select id="gamePackage">
      <option value="package1">ແພັກ 1 - 10 ເງິນ</option>
      <option value="package2">ແພັກ 2 - 50 ເງິນ</option>
      <option value="package3">ແພັກ 3 - 100 ເງິນ</option>
    </select>

    <h3>ຢືນຢັນການເລືອກ</h3>
    <input type="text" id="userName" placeholder="ໃສ່ຊື່ຂອງທ່ານ">

    <button onclick="sendToWhatsApp()">ສົ່ງໄປ WhatsApp</button>
    <div class="message" id="message"></div>
  </div>

  <script>
    function sendToWhatsApp() {
      const packageSelected = document.getElementById('gamePackage').value;
      const name = document.getElementById('userName').value;
      if(name.trim() === '') {
        alert('ກະລຸນາໃສ່ຊື່ຂອງທ່ານ');
        return;
      }
      const message = `ຂໍ້ມູນຈາກ ${name}: ເລືອກແພັກ ${packageSelected}`;
      const phoneNumber = '2095570282';
      const url = `https://wa.me/${phoneNumber}?text=${encodeURIComponent(message)}`;
      window.open(url, '_blank');
      document.getElementById('message').innerText = 'ກຳລັງເປີດ WhatsApp...';
    }
  </script>
</body>
</html>
