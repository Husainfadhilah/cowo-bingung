# Tugas Mandiri 03b — Wireframe HTML/CSS Hitam-Putih

Nama: Aliffuddin Adilla Rafif

## 1. Kode HTML & CSS:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kartu Produk</title>

    <style>
        body {
            font-family: sans-serif;
            background-color: white;
            color: black;
            padding: 20px;
        }

        .container {
            display: flex;
            gap: 20px;
        }

        .kartu-produk {
            border: 1px solid black;
            padding: 15px;
            width: 200px;
        }

        .gambar {
            border: 1px solid black;
            height: 120px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        button {
            padding: 10px;
            width: 100%;
            border: 1px solid black;
        }

        .aktif {
            background-color: black;
            color: white;
            cursor: pointer;
        }

        .nonaktif {
            background-color: white;
            color: gray;
            cursor: not-allowed;
        }
    </style>
</head>

<body>

    <h2>Daftar Produk Futsalzone</h2>

    <div class="container">

        <!-- Produk Stok Tersedia -->
        <div class="kartu-produk">
            <div class="gambar">
                Gambar Produk
            </div>

            <h3>Specs Accelerator</h3>
            <p>Harga: Rp350.000</p>
            <p>Status: Stok Tersedia</p>

            <button class="aktif">
                Tambah ke Keranjang
            </button>
        </div>

        <!-- Produk Stok Habis -->
        <div class="kartu-produk">
            <div class="gambar">
                Gambar Produk
            </div>

            <h3>Ortuseight Catalyst</h3>
            <p>Harga: Rp400.000</p>
            <p>Status: Stok Habis</p>

            <button class="nonaktif" disabled>
                Stok Habis
            </button>
        </div>

    </div>

</body>
</html>
```

## 2. Refleksi Singkat:

Setelah mengubah wireframe menjadi HTML dan CSS, saya jadi lebih memahami cara membuat kartu produk menggunakan struktur HTML dan mengatur tampilannya menggunakan CSS. Saya juga belajar membedakan tombol aktif ketika produk tersedia dan tombol nonaktif ketika stok produk habis. Hal ini menjadi bekal untuk mempelajari React di Bulan 2.