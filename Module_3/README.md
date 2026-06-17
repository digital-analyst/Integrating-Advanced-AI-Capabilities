# Paket Latihan Hands-On
## Pelatihan: Machine Learning and Data Analysis
Paket ini berisi dataset latihan dan contoh kode Python yang mengikuti urutan
materi training. Semua data bersifat **sintetis** (dibuat khusus untuk latihan,
bukan data asli perusahaan).

Kode tersedia dalam **dua format** dengan isi yang sama:
- `latihan_notebook/` — **Jupyter Notebook (.ipynb), format utama untuk pelatihan.**
  Sudah berisi penjelasan tiap langkah, contoh output, dan grafik.

---

## 1. Persiapan (sekali saja)

Pastikan Python 3.9+ sudah terpasang, lalu instal library yang dibutuhkan:

```bash
pip install pandas numpy scikit-learn matplotlib jupyter
```

Buka paket latihan dengan Jupyter:

```bash
jupyter notebook latihan_notebook
```

Lalu jalankan `00_generate_dataset.ipynb` **sekali** untuk membuat ulang dataset
(jalankan sel dari atas ke bawah dengan `Shift+Enter`).

> Alternatif tanpa Jupyter: `cd latihan_python && python 00_generate_dataset.py`

## 2. Struktur Folder

```
pelatihan/
├── dataset/                          <- data latihan (CSV)
│   ├── data_penjualan_motor.csv         53 bulan riwayat penjualan
│   ├── data_transaksi_sparepart.csv     1.218 transaksi (sengaja "kotor")
│   └── data_kredit_konsumen.csv         1.500 profil konsumen kredit
├── latihan_notebook/                 <- FORMAT UTAMA: buka berurutan 00 -> 05
│   ├── 00_generate_dataset.ipynb
│   ├── 01_pengolahan_data.ipynb
│   ├── 02_logika_ml_sederhana.ipynb
│   ├── 03_klasifikasi_dan_prediksi.ipynb
│   ├── 04_deteksi_anomali.ipynb
│   └── 05_interpretasi_bisnis.ipynb
├── latihan_python/                   <- versi script .py (isi sama)
└── output/                           <- grafik & laporan hasil latihan
```

## 3. Urutan Latihan (sesuai materi training)

| No | Notebook | Materi Training | Yang Dipelajari |
|----|--------|-----------------|-----------------|
| 1 | `01_pengolahan_data.ipynb` | Pemanfaatan algoritma AI untuk pengolahan data | Membaca, memeriksa, membersihkan, dan merangkum data dengan pandas |
| 2 | `02_logika_ml_sederhana.ipynb` | Logika Machine Learning secara sederhana | Fitur & target, data latih vs uji, `fit()` → `predict()` → evaluasi |
| 3 | `03_klasifikasi_dan_prediksi.ipynb` | Teknik klasifikasi dan prediksi | Klasifikasi risiko kredit (Lancar/Macet) + forecasting penjualan 6 bulan |
| 4 | `04_deteksi_anomali.ipynb` | Cara AI mendeteksi keanehan data | Z-score, IQR, dan Isolation Forest pada transaksi sparepart |
| 5 | `05_interpretasi_bisnis.ipynb` | Interpretasi hasil analisis AI untuk bisnis | Feature importance, konversi metrik → rupiah, ringkasan eksekutif |

Cara menjalankan: buka notebook-nya di Jupyter, lalu jalankan sel dari atas
ke bawah (`Shift+Enter`). Setiap notebook sudah berisi contoh output, sehingga
bisa juga dibaca dulu tanpa dijalankan.

Catatan: `04_deteksi_anomali.ipynb` memakai data bersih hasil modul 1, jadi
jalankan `01_pengolahan_data.ipynb` terlebih dahulu.

## 4. Ide Latihan Mandiri (setelah training)

1. **Modul 1** — Tambahkan ringkasan baru: part terlaris per dealer
   (petunjuk: `groupby(["dealer", "nama_part"])`).
2. **Modul 2** — Ubah jumlah bulan data uji dari 10 menjadi 6. Apakah MAE
   membaik atau memburuk? Mengapa?
3. **Modul 3** — Ubah skenario promo pada forecast (misal promo 3 bulan
   berturut-turut). Berapa tambahan unit yang diprediksi?
4. **Modul 4** — Turunkan `contamination` menjadi 0.005. Anomali mana yang
   hilang dari daftar? Apakah itu keputusan yang aman?
5. **Modul 5** — Ganti asumsi `KERUGIAN_PER_MACET` dan `MARGIN_PER_KONSUMEN`
   dengan angka yang menurut Anda realistis, lalu lihat perubahan
   rekomendasinya.
6. **Tantangan** — Terapkan pola modul 4 pada data dari area kerja Anda
   sendiri (klaim garansi, pemakaian part bengkel, jam lembur, dsb.).

## 5. Pemetaan ke Pekerjaan Sehari-hari

- **Forecasting** → perencanaan produksi, target penjualan, kebutuhan stok part.
- **Klasifikasi** → skrining kredit, prediksi konsumen berhenti servis (churn),
  prioritas leads.
- **Deteksi anomali** → audit transaksi, klaim garansi tidak wajar, kualitas
  hasil produksi, pemakaian sparepart bengkel.
- **Interpretasi** → bahan presentasi ke manajemen: faktor pendorong, dampak
  rupiah, rekomendasi, dan batasan analisis.
