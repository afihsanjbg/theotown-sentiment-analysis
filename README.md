# Analisis Sentimen Ulasan Game Theo Town di Google Play Store

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-lightgrey.svg)](https://scikit-learn.org/)
[![NLTK & Sastrawi](https://img.shields.io/badge/NLP-NLTK%20%7C%20Sastrawi-green.svg)]()

Repositori ini berisi proyek **Analisis Sentimen (Sentiment Analysis)** pada ulasan pengguna untuk game **Theo Town** yang diunduh dari Google Play Store. Proyek ini mencakup seluruh siklus *machine learning*, mulai dari pengumpulan data (scraping), pemrosesan teks bahasa Indonesia, ekstraksi fitur, hingga pelatihan dan pengujian berbagai model klasifikasi.

---

## 🎯 Gambaran Proyek
Tujuan utama dari proyek ini adalah untuk memahami sentimen pemain (positif, negatif, atau netral) terhadap game Theo Town berdasarkan ulasan mereka di Play Store. Model *machine learning* dilatih untuk secara otomatis mengklasifikasikan sentimen dari ulasan baru yang masuk.

---

## 📊 Dataset
Dataset yang digunakan dalam proyek ini dikumpulkan secara langsung (scraping) dari halaman aplikasi Theo Town di Google Play Store region Indonesia menggunakan library `google-play-scraper`.
- **Jumlah Data Awal**: ~15.000 ulasan (dapat disesuaikan)
- **Fitur Utama**: Teks ulasan pengguna (`content`) dan Skor (`score`)

---

## ⚙️ Alur Kerja (Workflow)

Proyek ini dijalankan melalui Jupyter Notebook (`Proyek Analisis Sentimen Game Theo Town.ipynb`) dengan tahapan sistematis berikut:

1. **Scraping Data**: Mengambil data ulasan dari Google Play Store.
2. **Pembersihan Data (Data Cleaning)**: Menghapus nilai kosong (*missing values*) dan baris duplikat.
3. **Data Pre-processing (NLP)**:
   - *Cleaning Text* (Menghapus mention, hashtag, link, angka, dan tanda baca)
   - *Case Folding* (Mengubah teks menjadi huruf kecil)
   - *Normalisasi Slangwords* (Memperbaiki singkatan dan bahasa gaul ke bentuk baku)
   - *Tokenizing* (Memecah teks menjadi kata)
   - *Stopword Removal* (Menghapus kata-kata tidak penting menggunakan NLTK)
   - *Stemming* (Mengembalikan kata ke bentuk dasar menggunakan Sastrawi)
4. **Pelabelan Sentimen**: Memberikan label kelas pada teks berdasarkan metrik tertentu.
5. **Eksplorasi Data (EDA)**: Visualisasi data teks menggunakan *WordCloud*.
6. **Ekstraksi Fitur & Pemisahan Data**:
   - **TF-IDF** (Term Frequency-Inverse Document Frequency)
   - **N-Gram**
   - **BoW** (Bag of Words)
7. **Pemodelan Machine Learning**:
   Tiga algoritma berbeda dilatih menggunakan metode ekstraksi fitur yang berbeda untuk membandingkan performanya:
   - **Support Vector Machine (SVM)** (Menggunakan TF-IDF)
   - **Random Forest** (Menggunakan N-Gram)
   - **Logistic Regression** (Menggunakan BoW)
8. **Inference (Pengujian)**: Melakukan prediksi pada teks atau kalimat ulasan baru yang belum pernah dilihat model sebelumnya.

---

## 🛠️ Teknologi & Library

Proyek ini dibangun menggunakan Python dengan dukungan library berikut:
- **Pengumpulan Data**: `google-play-scraper`
- **Manipulasi & Analisis Data**: `pandas`, `numpy`
- **Pemrosesan Bahasa Alami (NLP)**: `nltk`, `Sastrawi`, `re`
- **Machine Learning**: `scikit-learn` (`imbalanced-learn` untuk *oversampling* dengan SMOTE)
- **Visualisasi**: `matplotlib`, `seaborn`, `wordcloud`

---

## 🚀 Cara Penggunaan

1. **Clone repositori ini** ke dalam mesin lokal Anda:
   ```bash
   git clone https://github.com/username-anda/nama-repositori.git
   cd nama-repositori
   ```

2. **Instalasi library prasyarat**:
   Pastikan Anda telah menginstal semua *dependencies*. Anda bisa menginstalnya langsung di dalam environment Anda dengan menjalankan *cell* instalasi yang ada di awal notebook, atau menggunakan command berikut:
   ```bash
   pip install pandas numpy scikit-learn nltk Sastrawi google-play-scraper wordcloud imbalanced-learn matplotlib seaborn
   ```
   *(Jangan lupa untuk mendownload corpus NLTK yang dibutuhkan seperti `punkt` dan `stopwords`)*

3. **Jalankan Jupyter Notebook**:
   ```bash
   jupyter notebook "Proyek Analisis Sentimen Game Theo Town.ipynb"
   ```
   Atau Anda dapat mengimpor file `.ipynb` tersebut ke **Google Colab** untuk eksekusi yang lebih mudah menggunakan *Cloud Runtime*.

4. **Ikuti alur notebook** dari atas ke bawah untuk melihat proses scraping, pembersihan, pelatihan, hingga pengujian model.

---

*Dibuat untuk keperluan Analisis Data dan Pembelajaran Machine Learning.*
