# Midterm Machine Learning – Tugas Regresi

## 📌 Deskripsi Singkat
Repositori ini berisi implementasi **pipeline regresi end-to-end** untuk memprediksi tahun rilis sebuah lagu berdasarkan fitur audio-nya. Tujuannya adalah melatih model machine learning yang mampu memperkirakan tahun rilis dari berbagai fitur numerik yang diekstraksi dari sinyal musik.

---

## 🗂 Dataset
- **File:** `midterm-regresi-dataset.csv`
- **Jumlah baris:** 515,344
- **Jumlah kolom:** 91 (1 target + 90 fitur numerik)
- **Target:** `year` (tahun rilis lagu)
- **Fitur:** Nilai numerik yang mendeskripsikan karakteristik audio (misal: timbre, pitch, dll)
- **Sumber:** Disediakan untuk UTS Machine Learning

---

## 🛠 Alur Kerja / Pipeline

### 1. Memuat Dataset
- Menggunakan `pandas` untuk membaca file CSV.
- Memeriksa dimensi, baris pertama, dan ukuran file.

### 2. Pembersihan Data
- Menghapus kolom tidak diperlukan seperti `Unnamed: 0`.
- Membersihkan spasi pada nama kolom.
- Menangani missing value dengan mengisi median kolom numerik.

### 3. Memisahkan Fitur dan Target
- Target: kolom `year`
- Fitur: semua kolom numerik lainnya.

### 4. Train-Test Split
- Membagi dataset 80% train dan 20% test menggunakan `train_test_split`.

### 5. Normalisasi / Scaling
- Menggunakan `StandardScaler` untuk menormalkan fitur.

### 6. Pelatihan Model
- **Model yang digunakan:**
  - Linear Regression (`sklearn.linear_model.LinearRegression`)
  - Random Forest Regressor (`sklearn.ensemble.RandomForestRegressor`)
- Model utama: Random Forest
  - `n_estimators = 200`
  - `max_depth = 15`
  - `random_state = 42`

### 7. Evaluasi Model
- Menggunakan metrik:
  - MAE (Mean Absolute Error)
  - RMSE (Root Mean Squared Error)
  - R² Score
- Evaluasi dilakukan pada test set.

### 8. Menyimpan Model
- Model disimpan menggunakan `joblib` ke folder `models/`:
  - `regression_model.pkl` → model terlatih
  - `scaler.pkl` → scaler untuk fitur

### 9. Menyimpan Prediksi (Opsional)
- Output prediksi vs nilai sebenarnya disimpan ke `prediction_output.csv`.
