# Tugas Mandiri Wireframe HTML/CSS Hitam-Putih 
Nama: [Hanif Abdurrahman Arrifa'i]
## 1. Kode HTML & CSS:

<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Wireframe Produk</title>
  <style>
    body {
      font-family: sans-serif;
      background: white;
      padding: 20px;
    }

    .produk {
      border: 2px solid black;
      padding: 15px;
      margin-bottom: 15px;
      width: 250px;
    }

    .foto {
      height: 120px;
      border: 1px solid black;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    button {
      padding: 10px;
      border: 1px solid black;
      background: black;
      color: white;
    }

    button:disabled {
      background: #ccc;
      color: black;
      cursor: not-allowed;
    }
  </style>
</head>
<body>

  <h2>Katalog Produk UMKM</h2>

  <div class="produk">
    <div class="foto">X</div>
    <h3>Kopi Susu</h3>
    <p>Harga: Rp15.000</p>
    <p>Stok: Tersedia</p>
    <button>Pesan Sekarang</button>
  </div>

  <div class="produk">
    <div class="foto">X</div>
    <h3>Roti Bakar</h3>
    <p>Harga: Rp12.000</p>
    <p>Stok: Habis</p>
    <button disabled>Stok Habis</button>
  </div>

</body>
</html>
