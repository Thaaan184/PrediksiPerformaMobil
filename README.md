# 🚗 Prediksi Performa & Klasifikasi Mobil (Car Performance Prediction)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

Repository ini berisi proyek Machine Learning *end-to-end* untuk mengelompokkan dan memprediksi kategori mobil berdasarkan spesifikasi teknisnya (Horsepower, Harga, Kecepatan, Akselerasi, dll). Project ini digunakan untuk menyelesaikan UAS Machine Learning, dan mempelajari dunia machine leaarning.

---

## 👥 Authors

Project ini disusun oleh Mahasiswa **UPN "Veteran" Jakarta**:

| Nama | NIM | Email |
| :--- | :--- | :--- |
| **Muhammad Fathan Abriyanto** | 2210511164 | [2210511164@mahasiswa.upnvj.ac.id](mailto:2210511164@mahasiswa.upnvj.ac.id) |
| **Rachva Aryanjaya** | 2210511152 | [2210511152@mahasiswa.upnvj.ac.id](mailto:2210511152@mahasiswa.upnvj.ac.id) |

---
## 📋 Daftar Isi
1. [Tentang Proyek](#-tentang-proyek)
2. [Alur Kerja (Workflow)](#-alur-kerja-workflow)
3. [Teknologi yang Digunakan](#-teknologi-yang-digunakan)
4. [Struktur Folder](#-struktur-folder)
5. [Instalasi & Cara Penggunaan](#-instalasi--cara-penggunaan)
6. [Hasil Analisis](#-hasil-analisis)

---

## 📖 Tentang Proyek

Proyek ini bertujuan untuk menyelesaikan masalah segmentasi pasar mobil secara otomatis. Seringkali, kategori mobil ("Sports", "Hypercar", dll) bersifat subjektif. Proyek ini menggunakan pendekatan berbasis data untuk:
1. **Clustering (Labeling):** Mengelompokkan mobil secara otomatis menggunakan algoritma K-Means tanpa label sebelumnya.
2. **Klasifikasi:** Melatih model Random Forest untuk memprediksi kategori mobil baru berdasarkan pola yang ditemukan saat clustering.

---

## 🔄 Alur Kerja (Workflow)

Proyek ini dibagi menjadi dua tahap utama yang direpresentasikan oleh dua Jupyter Notebook:

### 1. Tahap Clustering (`Labeling.ipynb`)
Tahap *Unsupervised Learning* untuk memberikan label pada data mentah.
* **Data Cleaning:** Pembersihan format mata uang, satuan unit (hp, cc, km/h), dan penanganan *missing values*.
* **Scaling:** Standardisasi data menggunakan `StandardScaler` (Z-Score).
* **Feature Selection:** Menggunakan **PCA (Principal Component Analysis)** untuk memilih fitur yang paling berkontribusi dan mereduksi dimensi data.
* **Modeling:** Menggunakan **K-Means Clustering**.
* **Optimasi K:** Penentuan jumlah cluster optimal menggunakan **Elbow Method** (deteksi otomatis jarak terjauh).
* **Profiling:** Memberikan nama segmen (Economy, Sports, Supercar, Hypercar).

### 2. Tahap Klasifikasi & Prediksi (`Klasifikasi.ipynb`)
Tahap *Supervised Learning* untuk membuat model prediksi.
* **Preprocessing:** Memuat data hasil clustering.
* **Handling Imbalanced Data:** Menggunakan **SMOTE (Synthetic Minority Over-sampling Technique)** untuk menyeimbangkan kelas minoritas (khususnya kelas *Hypercar* yang datanya sedikit).
* **Model Training:** Menggunakan algoritma **Random Forest Classifier**.
* **Evaluasi:** Menggunakan **Stratified K-Fold Cross Validation** (5 Folds) untuk memastikan model stabil.
* **Minigame:** Widget interaktif untuk pengguna memasukkan spesifikasi mobil dan mendapatkan prediksi real-time.

---

## 🛠 Teknologi yang Digunakan

* **Bahasa:** Python
* **Data Manipulation:** Pandas, NumPy, Regular Expressions (Regex)
* **Visualisasi:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (KMeans, PCA, Random Forest), Imbalanced-Learn (SMOTE)
* **UI Interaktif:** Ipywidgets

---

## 📂 Struktur Folder

```bash
PrediksiPerformaMobil/
├── Dataset/
│   └── CarsDataset2025.csv       # Data mentah (Raw Data)
├── Hasil/
│   └── Clustered_CarsDataset.csv # Data yang sudah dilabeli (Hasil Labeling.ipynb)
├── Labeling.ipynb                # Notebook 1: Proses Clustering & PCA
├── Klasifikasi.ipynb             # Notebook 2: Proses Random Forest & Minigame
└── README.md                     # Dokumentasi Proyek


