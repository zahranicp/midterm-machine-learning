```md
# 📊 Midterm Machine Learning — Customer Clustering  
UTS Machine Learning • Telkom University  
By **Zahrani Cahya Priesa**

---

## 📌 Overview

Repository ini berisi implementasi end-to-end untuk **tugas UTS Machine Learning**, dengan fokus pada **Customer Clustering (Unsupervised Learning)**.  
Pada tugas ini, dilakukan proses lengkap mulai dari eksplorasi data, preprocessing, penerapan model clustering, hingga interpretasi hasil cluster.

Tujuan utama dari proyek ini adalah melakukan segmentasi customer berdasarkan perilaku penggunaan kartu kredit, sehingga dapat dimanfaatkan untuk analisis bisnis atau strategi marketing.

---

## 🧠 Project Objectives

- Melakukan eksplorasi data (EDA) untuk memahami pola data customer.
- Melakukan preprocessing:
  - Penanganan missing values
  - Penanganan outliers
  - Normalisasi fitur
- Menerapkan algoritma clustering:
  - **K-Means** (metode utama)
  - Opsional: DBSCAN / Hierarchical
- Menentukan jumlah cluster optimal menggunakan:
  - **Elbow Method**
  - **Silhouette Score**
- Menginterpretasi karakteristik tiap cluster secara jelas.

---

## 📁 Repository Structure

```

midterm-machine-learning/
│
├── clustering.ipynb                # Notebook utama clustering
├── data/
│   └── clusteringmidterm.csv       # Dataset UTS
│
├── models/                         # (Opsional) Simpan model
│
└── README.md                       # Dokumentasi proyek

````

---

## 🔍 Pipeline Ringkas

### **1. Exploratory Data Analysis (EDA)**
- Menampilkan struktur dan tipe data
- Distribusi variabel penting
- Korelasi antar fitur
- Deteksi fitur-fitur dominan

### **2. Data Preprocessing**
- Menghapus kolom ID (`CUST_ID`)
- Mengisi missing values dengan median
- Standardisasi menggunakan `StandardScaler`
- Analisis outliers menggunakan IQR

### **3. Clustering**
Menggunakan algoritma:
- **K-Means (main model)**  
Dengan proses:
- Mencoba beberapa nilai `k`
- Mencari optimal cluster menggunakan Elbow Curve
- Menghitung Silhouette Score

### **4. Evaluasi**
- Inertia (SSE)
- Silhouette Score
- Visualisasi:
  - Elbow Plot
  - Cluster Distribution
  - Scatter Plots (post-scaling)

### **5. Interpretasi Cluster**
Setiap cluster dianalisis berdasarkan:
- Tingkat spending customer
- Penggunaan limit kredit
- Frekuensi transaksi / cash advance
- Kebiasaan pembayaran

Output berupa insight seperti:
- **High Spender**
- **Low Activity Customer**
- **Risky User**
- **Installment-heavy User**

---

## 🚀 Cara Menjalankan

1. Clone repository:
```bash
git clone https://github.com/username/midterm-machine-learning.git
````

2. Masuk folder project:

```bash
cd midterm-machine-learning
```

3. Install package yang dibutuhkan:

```bash
pip install numpy pandas scikit-learn matplotlib seaborn
```

4. Jalankan notebook:

```bash
jupyter notebook
```

---

## 👤 Author

**Nama:** Zahrani Cahya Priesa
**NIM:** 1103223074
**Program Studi:** S1 Teknik Komputer
**Universitas:** Telkom University

---

## ⭐ Catatan

Proyek ini dibuat sebagai pemenuhan **UTS Machine Learning** dengan standar:

* End-to-end pipeline
* Dokumentasi jelas
* Struktur rapi sesuai ketentuan dosen
  Notebook ini dapat dijadikan referensi untuk pengembangan lebih lanjut pada studi clustering dan data mining.

---

Terima kasih telah mengunjungi repository ini!
Jika ingin meminta versi README untuk **Fraud Detection** atau **Regression**, tinggal bilang.
