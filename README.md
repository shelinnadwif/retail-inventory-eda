# 📦 Optimizing Retail Inventory: Preventing Stockouts using EDA in Python

Mini-project Exploratory Data Analysis (EDA) untuk membantu tim gudang retail memantau sisa stok dan tingkat perputaran produk, sebagai bagian dari tugas mata kuliah Sains Data.

## 🎯 Studi Kasus

Sebuah toko retail ingin mengetahui produk mana saja yang berisiko menumpuk (overstock) dan mana yang perputarannya cepat, agar proses pengadaan barang ke depan bisa lebih efisien dan tidak ada modal yang "tertahan" di gudang.

## 🗂️ Dataset

`mhs6_retail_inventory.csv` — 75 produk dari 4 kategori (Makanan, Minuman, ATK, Kosmetik) dengan kolom:

| Kolom | Deskripsi |
|---|---|
| ID_Produk | Kode unik produk |
| Kategori | Kategori barang |
| Stok_Awal | Jumlah stok di awal periode |
| Sisa_Stok | Jumlah stok yang tersisa (terdapat nilai kosong) |
| Unit_Terjual | Jumlah unit yang terjual |
| Harga_Satuan | Harga jual per unit (Rupiah) |

## 🔧 Tahapan Analisis

1. **Pemeriksaan struktur data** - `.info()` dan pemetaan tipe data ke skala statistik (nominal/rasio).
2. **Statistik deskriptif & distribusi awal** - `.describe()`, perbandingan mean vs median, histogram sisa stok sebelum dibersihkan.
3. **Data cleaning** - mengisi nilai kosong pada `Sisa_Stok` dengan 0 (mengindikasikan barang habis), bukan menghapus baris.
4. **Feature engineering** - membuat kolom `Status_Perputaran` (`Fast Moving` / `Slow Moving`) menggunakan `np.where()` berdasarkan ambang 500 unit terjual.
5. **Visualisasi & storytelling** - diagram batang total sisa stok per kategori, dilengkapi narasi insight dan rekomendasi bisnis untuk manajemen.

## 📊 Temuan Utama

- Distribusi sisa stok **right-skewed** (mean 128.0 > median 110.0) - sebagian kecil produk menumpuk stok dalam jumlah besar.
- **Kategori Kosmetik** memiliki total sisa stok tertinggi (2.563 unit), diikuti Makanan (2.281 unit).
- **Tidak ada produk yang mencapai status Fast Moving** (penjualan tertinggi 469 unit, masih di bawah ambang 500) - mengindikasikan masalah perputaran stok yang menyeluruh, bukan hanya pada kategori tertentu.

## 💡 Rekomendasi Bisnis

- Mengkaji ulang volume re-order, khususnya untuk kategori Kosmetik dan Makanan.
- Pertimbangkan promosi/bundling untuk mempercepat perputaran stok yang menumpuk.
- Tinjau kembali ambang batas "Fast Moving" agar lebih realistis dengan skala penjualan toko saat ini.

## 🛠️ Tools

Python, Pandas, NumPy, Matplotlib (Jupyter Notebook)

## 📁 Struktur Repository

```
├── retail_inventory_analysis.ipynb   # Notebook analisis utama
├── mhs6_retail_inventory.csv         # Dataset mentah
├── retail_inventory_clean.csv        # Dataset hasil cleaning & feature engineering
├── charts/                           # Hasil visualisasi (PNG)
└── README.md
```

## ✍️ Author

Shelinna Dwiforizqi Usti — Program Studi Teknik Informatika
Mini-Project Mata Kuliah Sains Data
