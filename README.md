<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Tanaman</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #fffacd;
      margin: 20px;
    }

    h1 {
      text-align: center;
      color: #333;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      background-color: #fff8b5;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    th, td {
      border: 1px solid #ccc;
      padding: 12px;
      text-align: center;
    }

    th {
      background-color: #f1c40f;
      color: white;
    }

    input[type="text"], input[type="number"] {
      width: 90%;
      padding: 5px;
    }

    input[type="file"] {
      width: 100%;
    }

    img {
      max-width: 100px;
      max-height: 100px;
      margin-top: 5px;
    }
  </style>
</head>
<body>

  <h1>Tanaman (7 Hari)</h1>

  <table>
    <thead>
      <tr>
        <th>Hari</th>
        <th>Panjang (cm)</th>
        <th>Keterangan</th>
        <th>Foto</th>
      </tr>
    </thead>
    <tbody>
      <!-- Generate 7 rows -->
      <script>
        for (let i = 1; i <= 7; i++) {
          document.write(`
            <tr>
              <td>Hari ${i}</td>
              <td><input type="number" placeholder="Contoh: 12.5"></td>
              <td><input type="text" placeholder="Contoh: Daun mulai tumbuh"></td>
              <td>
                <input type="file" accept="image/*" onchange="previewImage(event, 'img${i}')">
                <br><img id="img${i}" alt="Belum ada foto">
              </td>
            </tr>
          `);
        }
      </script>
    </tbody>
  </table>

  <script>
    function previewImage(event, imgId) {
      const file = event.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function(e) {
          document.getElementById(imgId).src = e.target.result;
        };
        reader.readAsDataURL(file);
      }
    }
  </script>
  <footer>
    <p>Yaa gitulah ges</p><br>
    <img src="https://cdn.cdnstep.com/HieDalxjCdPp0OkMgQzc/cover.thumb256.webp">
    <p>Cafek wak</p>
  </footer>
</body>
</html>
