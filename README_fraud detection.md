# 💳 Deteksi Penipuan Transaksi (Fraud Detection) menggunakan LightGBM

## 🌟 Deskripsi Proyek

Proyek ini bertujuan untuk membangun model machine learning yang efektif untuk **mengidentifikasi transaksi penipuan (`isFraud`)** berdasarkan data transaksi yang kaya fitur. Pendekatan yang digunakan adalah **klasifikasi biner** dengan menggunakan algoritma *Gradient Boosting Decision Tree* yang sangat efisien, yaitu **LightGBM**.

Pipeline yang dikembangkan mencakup seluruh proses Data Science, mulai dari *Feature Engineering* berbasis waktu, penanganan nilai hilang (missing values), pra-pemrosesan data, hingga *scaling* dan pelatihan model.

## 🚀 Struktur Kode dan File

Repositori ini berisi file-file utama berikut:

| File | Deskripsi |
| :--- | :--- |
| `fraud_detection_lgbm.py` | Skrip Python lengkap yang berisi seluruh *pipeline* pra-pemrosesan data, pelatihan model LightGBM, dan evaluasi. |
| `train_transaction.csv` | Data transaksi pelatihan (Asumsi file ini ada di direktori kerja). |
| `test_transaction.csv` | Data transaksi pengujian (Asumsi file ini ada di direktori kerja). |
| `test_prediction.csv` | **Output** prediksi probabilitas pada data pengujian. |
| `README.md` | Dokumen ini. |

## ⚙️ Persyaratan (Installation)

Untuk menjalankan skrip ini secara lokal, Anda memerlukan beberapa pustaka Python. Anda dapat menginstal semua yang dibutuhkan menggunakan `pip`:

```bash
pip install pandas numpy scikit-learn lightgbm

Versi Pustaka Utama

    Python: 3.8+

    pandas: 1.3.0+

    lightgbm: 3.3.0+

    scikit-learn: 1.0.0+

📊 Pipeline Pemrosesan Data

Skrip fraud_detection_lgbm.py menjalankan langkah-langkah berikut secara berurutan:

    Pemuatan Data: Memuat train_transaction.csv dan test_transaction.csv.

    Feature Engineering Waktu: Membuat fitur Transaction_Hour dan Transaction_Day dari TransactionDT.

    Penanganan Nilai Hilang Tinggi: Menghapus kolom dengan proporsi missing values lebih dari 50%.

    Imputasi: Mengisi nilai hilang numerik dengan Median dan nilai hilang kategorikal dengan Mode.

    Grouping Kategori Langka: Mengelompokkan kategori yang frekuensinya di bawah 1% menjadi "RARE".

    Encoding: Mengubah fitur kategorikal (object) menjadi numerik menggunakan Label Encoding.

    Scaling: Menormalkan fitur numerik menggunakan StandardScaler untuk melatih model yang stabil.

    Split Data: Memisahkan data train menjadi Training Set dan Validation Set (80/20) secara stratified.

🧠 Konfigurasi Model LightGBM

Model dilatih menggunakan konfigurasi berikut (diambil dari params skrip):
Parameter	Nilai	Tujuan
objective	binary	Masalah Klasifikasi Biner.
metric	auc	Metrik utama untuk mengukur performa (Area Under ROC Curve).
num_leaves	64	Kapasitas model.
learning_rate	0.02	Ukuran langkah (step size) untuk setiap booster.
n_estimators	500	Jumlah maksimum tree.
callbacks	early_stopping(100)	Menghentikan pelatihan jika metrik validasi tidak meningkat selama 100 iterasi.
🔬 Hasil dan Evaluasi

Setelah pelatihan, model dievaluasi pada Validation Set (20% dari data training).
Metrik Utama (Contoh Output)
Metrik	Nilai	Catatan
Validation AUC	0.9XX	Metrik kompetisi utama; nilai yang lebih tinggi lebih baik.
Akurasi	0.9XX	Proporsi prediksi yang benar.
Recall (Kelas 1 / Fraud)	0.XX	Kemampuan model mendeteksi penipuan yang sebenarnya.
Confusion Matrix (Contoh Format)

[[TN FP]
 [FN TP]]

Model LightGBM menunjukkan kinerja yang kuat dalam mendeteksi penipuan, ditunjukkan oleh nilai AUC yang tinggi. Fokus evaluasi berada pada metrik Recall untuk kelas penipuan, untuk meminimalkan False Negatives (penipuan lolos).
▶️ Cara Menjalankan

    Pastikan Anda telah mengunduh train_transaction.csv dan test_transaction.csv dan menempatkannya dalam direktori yang sama dengan skrip Python.

    Jalankan skrip dari terminal:

Bash

python fraud_detection_lgbm.py

    Hasil prediksi akan disimpan dalam file test_prediction.csv.
