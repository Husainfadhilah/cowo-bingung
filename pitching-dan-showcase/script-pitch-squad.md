# WIREFRAME KATALOG APLIKASI
[ini link wireframenya](https://www.figma.com/design/bNUu4FjZ4p5limjOiRrCOh/Untitled?node-id=0-1&t=XyBcg9B2FzgGGLvU-1)

# FLOWCHARTNYA

#### A. Flowchart Pembeli

```mermaid
flowchart TD
    A([Mulai]) --> B[Membuka Katalog Produk]
    B --> C[Melihat Daftar Produk]
    C --> D{Memilih Fitur}

    D -->|Pencarian| E[Memasukkan Kata Kunci]
    E --> F[Menampilkan Hasil Pencarian]
    F --> C

    D -->|Kategori| G[Memilih Kategori Produk]
    G --> H[Menampilkan Produk Sesuai Kategori]
    H --> C

    D -->|Pilih Produk| I[Melihat Detail Produk]
    I --> J{Produk Tersedia?}

    J -->|Ya| K[Menampilkan Tombol Pesan]
    K --> L[Melakukan Pemesanan]
    L --> M([Selesai])

    J -->|Tidak| N[Menampilkan Status Produk Habis]
    N --> O[Kembali ke Katalog]
    O --> C
```

#### B. Flowchart Pedagang

```mermaid
flowchart TD
    A([Mulai]) --> B[Membuka Halaman Produk Saya]
    B --> C[Melihat Ringkasan Produk dan Stok]
    C --> D{Memilih Menu}

    D -->|Tambah Produk| E[Mengisi Data Produk]
    E --> F[Menambahkan Foto Produk]
    F --> G[Menyimpan Produk]
    G --> H[Data Produk Tersimpan]

    D -->|Edit Produk| I[Memilih Produk]
    I --> J[Mengubah Data Produk]
    J --> G

    D -->|Kelola Stok| K[Memilih Produk]
    K --> L[Mengubah Jumlah Stok]
    L --> M[Menyimpan Perubahan]
    M --> H

    H --> N[Memperbarui Daftar Produk]
    N --> O{Ingin Membagikan Katalog?}

    O -->|Ya| P[Membuka Menu Bagikan Katalog]
    P --> Q[Menampilkan QR Code dan Tautan]
    Q --> R[Menyalin atau Membagikan Katalog]
    R --> S([Selesai])

    O -->|Tidak| C
```


# ERD KATALOG

```mermaid
erDiagram
    TOKO ||--o{ PRODUK : memiliki
    KATEGORI ||--o{ PRODUK : mengelompokkan
    PRODUK ||--o{ FOTO_PRODUK : memiliki
    TOKO ||--o{ KATALOG_QR : membagikan

    TOKO {
        int id_toko PK
        string nama_toko
        string deskripsi
        string foto_toko
        string alamat
        string nomor_telepon
    }

    KATEGORI {
        int id_kategori PK
        string nama_kategori
    }

    PRODUK {
        int id_produk PK
        int id_toko FK
        int id_kategori FK
        string nama_produk
        string deskripsi
        decimal harga
        int jumlah_stok
        string status_produk
    }

    FOTO_PRODUK {
        int id_foto PK
        int id_produk FK
        string url_foto
    }

    KATALOG_QR {
        int id_qr PK
        int id_toko FK
        string kode_qr
        string tautan_katalog
        datetime tanggal_dibuat
    }
```

#### B. Penjelasan Entitas

| Entitas | Fungsi |
|---|---|
| TOKO | Menyimpan informasi identitas toko UMKM. |
| KATEGORI | Menyimpan kategori produk seperti panci, wajan, piring, dan gelas. |
| PRODUK | Menyimpan nama, harga, deskripsi, jumlah stok, dan status produk. |
| FOTO_PRODUK | Menyimpan foto produk yang dapat ditampilkan pada katalog dan detail produk. |
| KATALOG_QR | Menyimpan informasi QR Code dan tautan untuk membagikan katalog toko. |

#### C. Penjelasan Relasi

1. **TOKO - PRODUK (1:N)**

   Satu toko dapat memiliki banyak produk, tetapi satu produk hanya dimiliki oleh satu toko.

2. **KATEGORI - PRODUK (1:N)**

   Satu kategori dapat memiliki banyak produk, tetapi satu produk hanya memiliki satu kategori.

3. **PRODUK - FOTO_PRODUK (1:N)**

   Satu produk dapat memiliki beberapa foto, tetapi satu foto hanya dimiliki oleh satu produk.

4. **TOKO - KATALOG_QR (1:N)**

   Satu toko dapat memiliki beberapa data QR Code atau tautan katalog.

---

### 3. KETERANGAN TAMBAHAN

**Aturan status produk:**

- Jika `jumlah_stok > 0`, maka status produk adalah `Tersedia`.
- Jika `jumlah_stok = 0`, maka status produk adalah `Habis`.

**Primary Key (PK):**

Merupakan identitas unik untuk setiap data dalam tabel.

**Foreign Key (FK):**

Merupakan kolom yang menghubungkan satu tabel dengan tabel lainnya.

**Catatan:**

ERD ini disusun berdasarkan fitur yang terlihat pada wireframe. Fitur login, pembayaran, keranjang belanja, dan riwayat transaksi belum dimasukkan karena belum terlihat pada rancangan halaman aplikasi.


# BACKLOG KATALOG

# RENCANA FITUR BACKLOG
## Aplikasi Katalog Produk UMKM – Ida Leman Collection

### 1. Tujuan Backlog

Rencana fitur backlog dibuat untuk menentukan fitur apa saja yang akan dikembangkan dalam aplikasi katalog produk UMKM. Fitur disusun berdasarkan kebutuhan pedagang dan pembeli agar proses pembuatan aplikasi lebih terarah.

### 2. Daftar Prioritas Fitur

| No. | Nama Fitur | Prioritas | Alasan |
|---|---|---|---|
| 1 | Katalog Produk | Wajib Ada | Pembeli dapat melihat daftar produk yang dijual. |
| 2 | Tambah dan Edit Produk | Wajib Ada | Pedagang dapat menambahkan dan memperbarui informasi produk. |
| 3 | Manajemen Stok | Wajib Ada | Pedagang dapat mengatur jumlah stok barang. |
| 4 | Pencarian Produk | Penting | Memudahkan pembeli menemukan produk yang dicari. |
| 5 | Kategori Produk | Penting | Memudahkan pembeli mencari produk berdasarkan jenisnya. |
| 6 | Pemesanan WhatsApp | Penting | Memudahkan pembeli melakukan pemesanan melalui WhatsApp. |
| 7 | Status Ketersediaan | Penting | Pembeli dapat mengetahui produk yang tersedia atau habis. |
| 8 | QR Code Katalog | Pelengkap | Memudahkan pedagang membagikan katalog kepada pembeli. |
| 9 | Banyak Foto Produk | Pelengkap | Memberikan gambaran produk yang lebih jelas kepada pembeli. |
| 10 | Laporan Penjualan | Nanti Dulu | Belum menjadi kebutuhan utama pada tahap awal pengembangan. |

### 3. Rencana Pengerjaan

**Tahap 1 – Fitur Utama**
- Membuat halaman katalog produk.
- Membuat fitur tambah dan edit produk.
- Membuat fitur manajemen stok.

**Tahap 2 – Fitur Pendukung**
- Membuat pencarian produk.
- Membuat kategori produk.
- Membuat pemesanan melalui WhatsApp.
- Menampilkan status ketersediaan produk.

**Tahap 3 – Fitur Pelengkap**
- Membuat QR Code katalog.
- Menambahkan beberapa foto produk.

**Tahap 4 – Pengembangan Selanjutnya**
- Membuat laporan penjualan.

### 4. Kesimpulan

Pengembangan aplikasi akan dimulai dari fitur utama yang paling dibutuhkan oleh pedagang dan pembeli. Setelah fitur utama selesai, pengembangan dilanjutkan ke fitur pendukung dan pelengkap. Dengan adanya backlog, proses pengerjaan aplikasi menjadi lebih terarah dan sesuai kebutuhan UMKM.

