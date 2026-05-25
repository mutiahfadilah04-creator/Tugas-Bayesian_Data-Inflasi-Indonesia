# Analisis Inflasi Bayesian - Indonesia 2025

> Kode dan data pendukung artikel ilmiah:
> **"Evaluasi Kesesuaian dan Ketahanan Model Hierarki Bayesian pada Inflasi Bulanan di 38 Provinsi Indonesia Tahun 2025 melalui Posterior Predictive Check dan Analisis Sensitivitas"**
>
> Mutiah Fadilah Saputri, Ahmad Choiry, Abdul Taqwa

## Deskripsi

Proyek ini menganalisis data inflasi bulanan month-to-month (M-to-M) 38 provinsi Indonesia tahun 2025 menggunakan model hierarki Bayesian dua arah (provinsi × bulan) yang diimplementasikan dengan PyMC v5.

Model hierarki digunakan untuk memisahkan tiga sumber variasi secara simultan: rata-rata inflasi nasional, efek spesifik tiap provinsi, dan efek spesifik tiap bulan. Evaluasi dilakukan melalui Posterior Predictive Check (PPC) dan analisis sensitivitas terhadap spesifikasi prior dan likelihood.

## Struktur File
├── Proyek_Bayessian_Inflasi_Indonesia_2025.ipynb
│       Kode analisis utama (model, PPC, sensitivitas, LOO-CV)
├── Inflasi Bulanan (M-to-M) 38 Provinsi 2025.csv
│       Data inflasi 2025 — variabel respons (456 observasi)
├── Inflasi Bulanan (M-to-M) 38 Provinsi 2024.csv
│       Data inflasi 2024 — sumber prior informatif
├── requirements.txt
│       Daftar library Python yang digunakan
└── README.md
