# Analisis Regresi Nonlinear pada Concrete Compressive Strength

Repositori ini berisi sintaks R untuk menganalisis hubungan antara umur beton (`age`) dan kuat tekan beton (`strength`) pada dataset **Concrete Compressive Strength**.

## Cakupan analisis

- Pemeriksaan struktur data dan ringkasan statistik.
- Exploratory Data Analysis (EDA) dan korelasi Pearson/Spearman.
- Model pembanding: regresi linear dan regresi logaritmik.
- Model nonlinear: power, hiperbolik, dan saturating exponential.
- Perbandingan model menggunakan R², AIC, dan BIC.
- Diagnostik residual, Shapiro–Wilk, Cook's distance, studentized residual, dan leverage.
- Evaluasi prediksi dengan train-test 75:25 dan Random Forest.
- Evaluasi Random Forest menggunakan 10-fold cross-validation.
- Penyimpanan tabel hasil dan grafik.

## Struktur repositori

```text
.
├── README.md
├── .gitignore
├── scripts/
│   └── analisis_regresi_non_linear.R
└── docs/
    └── panduan_penggunaan.md
```

## Persiapan

1. Pasang R dan RStudio.
2. Siapkan dataset Concrete Compressive Strength dalam format Excel.
3. Buka `scripts/analisis_regresi_non_linear.R`.
4. Ubah argumen pada `read_excel()` agar sesuai dengan lokasi file dataset di komputer Anda. Sintaks asal menggunakan path lokal Windows, sehingga path tersebut tidak akan otomatis berfungsi pada komputer lain.
5. Jalankan skrip dari atas ke bawah.

Paket yang diperlukan akan dipasang otomatis jika belum tersedia: `readxl`, `dplyr`, `ggplot2`, `minpack.lm`, `Metrics`, `randomForest`, `caret`, dan `broom`.

## Catatan metodologis

- Pastikan urutan kolom pada dataset benar sebelum baris `names(df) <- ...` dijalankan. Penamaan ulang berdasarkan posisi kolom dapat menghasilkan label yang salah jika susunan dataset berbeda.
- Pada sintaks ini, diagnostik Cook's distance, leverage, dan studentized residual dihitung dari model linear `strength ~ age`, bukan langsung dari model nonlinear hiperbolik. Interpretasikan diagnostik sesuai model yang benar-benar digunakan.
- Pemilihan model akhir sebaiknya didasarkan pada tujuan analisis, diagnostik, dan kinerja data uji, bukan R² saja.
- Hasil numerik belum disertakan karena skrip perlu dijalankan pada dataset yang digunakan dalam penelitian.

## Lisensi

Belum ada lisensi yang ditetapkan. Tambahkan file lisensi jika Anda ingin mengizinkan penggunaan ulang secara eksplisit.
