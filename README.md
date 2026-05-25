# Tugas-Bayesian_Data-Inflasi-Indonesia
# Analisis Inflasi Bayesian - Indonesia 2025

Proyek ini menganalisis data inflasi bulanan month-to-month (M-to-M) 
38 provinsi Indonesia tahun 2025 menggunakan model hierarki Bayesian.

## Metode
- Model hierarki Bayesian dengan PyMC
- 6 skenario model (3 prior × 2 likelihood)
- Prior informatif dari data 2024 sebagai historical data

## File
- `Proyek_Bayessian_Inflasi_Indonesia_2025.ipynb` — kode analisis utama
- `Inflasi Bulanan... 2025.csv` — data inflasi 2025
- `Inflasi Bulanan... 2024.csv` — data inflasi 2024 (prior)

## Library
PyMC, ArviZ, Pandas, NumPy, Matplotlib, Seaborn, SciPy

## Hasil Utama
Model terbaik: M4 (Prior Informatif + Student-t likelihood)
berdasarkan LOO-CV (ELPD = -327.26)
