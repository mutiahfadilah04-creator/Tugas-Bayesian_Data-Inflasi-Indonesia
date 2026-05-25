# Analisis Inflasi Bayesian - Indonesia 2025

> Kode dan data pendukung artikel ilmiah:
> **"Evaluasi Kesesuaian dan Ketahanan Model Hierarki Bayesian pada Inflasi Bulanan di 38 Provinsi Indonesia Tahun 2025 melalui Posterior Predictive Check dan Analisis Sensitivitas"**
>
> Mutiah Fadilah Saputri, Ahmad Choiry, Abdul Taqwa

## Deskripsi

Proyek ini menganalisis data inflasi bulanan month-to-month (M-to-M) 38 provinsi Indonesia tahun 2025 menggunakan model hierarki Bayesian dua arah (provinsi × bulan) yang diimplementasikan dengan PyMC v5.

Model hierarki digunakan untuk memisahkan tiga sumber variasi secara simultan: rata-rata inflasi nasional, efek spesifik tiap provinsi, dan efek spesifik tiap bulan. Evaluasi dilakukan melalui Posterior Predictive Check (PPC) dan analisis sensitivitas terhadap spesifikasi prior dan likelihood.

## Metode

### Model
- Model hierarki Bayesian dua arah: efek provinsi + efek bulan
- Distribusi likelihood: Normal dan Student-t (robust terhadap outlier)
- Estimasi posterior via NUTS (No-U-Turn Sampler) dengan PyMC v5
- Non-centered parameterization untuk efisiensi sampling

### Skenario Model (6 total)

| Model | Prior | Likelihood |
|-------|-------|------------|
| M1 | Non-informatif | Normal |
| M2 | Weakly Informative | Normal |
| M3 | Informatif (data 2024) | Normal |
| M4 | Non-informatif | Student-t |
| M5 | Weakly Informative | Student-t |
| M6 | Informatif (data 2024) | Student-t |

### Evaluasi

- **PPC**: density overlay, Q-Q Plot Bayesian, rootogram, posterior predictive p-value (PPP)
- **Seleksi model**: LOO-CV (Leave-One-Out Cross-Validation) via ArviZ
- **Sensitivitas**: power-scaling prior dan likelihood (Kallioinen et al., 2024)

## Hasil Utama

Model terbaik: **M6 — Prior Informatif + Student-t likelihood**
ELPD LOO-CV = **-327.26**

Kesimpulan utama:
- Distribusi Student-t secara konsisten lebih baik dari Normal karena data inflasi memiliki ekor tebal akibat outlier musiman seperti Ramadan
- Prior informatif dari data 2024 meningkatkan presisi estimasi
- Analisis sensitivitas menunjukkan kesimpulan robust terhadap perubahan spesifikasi prior

## Library yang Digunakan

- PyMC >= 5.0
- ArviZ >= 0.17
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy

## Sumber Data

- **Data inflasi 2025**: Badan Pusat Statistik (BPS RI)
  https://www.bps.go.id/id/statistics-table/2/MjI2MiMy/inflasi-month-to-month--november-2025.html
- **Referensi definisi inflasi**: Bank Indonesia
  https://www.bi.go.id/id/fungsi-utama/moneter/inflasi/default.aspx
