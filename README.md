# 📰 Klasifikasi Polaritas Berita Ekonomi Indonesia Terkait Kebijakan Pemerintah pada Detik

**Penulis:**  
Faliqul Ishbah (202210370311148)
Tiko Dava (202210370311149)
Ganesha Mahardika Prasetya (202210370311156)

**Jurusan Informatika, Fakultas Teknik, Universitas Muhammadiyah Malang**  
Jl. Raya Tlogomas, Tegalgondo, Kec. Lowokwaru, Malang, Jawa Timur, Indonesia, 65144  

---

## 📘 Deskripsi Proyek

Proyek ini berfokus pada **analisis sentimen berita ekonomi Indonesia** yang dipublikasikan oleh **Detik.com**, khususnya yang membahas **kebijakan pemerintah**. Tujuannya adalah untuk **mengklasifikasikan polaritas berita** ke dalam tiga kategori utama:

- 🟢 **Positif** — Berita bernada optimistis, mendukung, atau memberikan dampak positif terhadap kebijakan.  
- ⚪ **Netral** — Berita bersifat informatif tanpa kecenderungan sentimen tertentu.  
- 🔴 **Negatif** — Berita yang menunjukkan kritik, pesimisme, atau dampak negatif terhadap kebijakan.

Pendekatan ini dilakukan melalui **pemodelan teks** menggunakan berbagai metode mulai dari *classical machine learning*, *deep learning embeddings*, hingga *transformer-based transfer learning*.

---

## 🎯 Tujuan Penelitian

1. Mengembangkan model klasifikasi teks untuk menentukan polaritas berita ekonomi.  
2. Membandingkan performa antara tiga pendekatan utama:
   - Pendekatan Klasik (BoW, TF-IDF)
   - Pendekatan Deep Learning (Word2Vec, FastText)
   - Pendekatan Transfer Learning (IndoBERT, XLM-RoBERTa)
3. Menentukan metode representasi teks terbaik berdasarkan tingkat akurasi dan stabilitas model.

---

## 🧾 Sumber dan Pengolahan Data

### 🔹 Sumber Data
Data dikumpulkan melalui proses **web scraping** dari situs **Detik.com** pada kategori berita *Ekonomi dan Kebijakan Pemerintah*.

Contoh atribut hasil scraping:
- **Judul Berita**  
- **Tanggal Publikasi**  
- **Isi Berita**  
- **URL Sumber**

### 🔹 Pra-pemrosesan Teks
Tahapan pembersihan dan normalisasi data meliputi:
- Menghapus karakter non-alfabet.  
- Mengonversi teks ke huruf kecil.  
- Menghapus stopwords Bahasa Indonesia.  
- Melakukan tokenisasi.  
- Melakukan lemmatisasi/stemming dengan library seperti `Sastrawi`.

---

## 🎯 Target Data

Tidak semua atribut hasil scraping digunakan dalam proses analisis. Hanya dua atribut utama yang dijadikan target utama:

| Atribut | Keterangan |
|----------|-------------|
| **Isi Berita** | Sumber teks utama untuk analisis sentimen. |
| **Label Sentimen** | Kelas target hasil klasifikasi (*Positif*, *Netral*, *Negatif*). |

### 🧩 Contoh Data

| Isi | Label |
|-----|--------|
| Menteri Koordinator Bidang Perekonomian Airlangga Hartarto soroti potensi artificial intelligence (AI) | Positif |
| Pemerintah Provinsi Jawa Tengah memberikan insentif pajak kendaraan bermotor... | Positif |
| Prasasti Center for Policy Studies menilai langkah Menteri Keuangan... | Netral |
| Anggota MPR RI dari Fraksi Partai Golkar, Ahmad Labib menyampaikan pentingnya... | Negatif |

---

## ⚙️ Metodologi

Penelitian ini membandingkan **tiga pendekatan utama**:

### 1️⃣ Pendekatan Klasik
Menggunakan representasi **Bag-of-Words (BoW)** dan **TF-IDF**.  
Model yang diuji:
- Naive Bayes
- Support Vector Machine (SVM)
- Random Forest

### 2️⃣ Pendekatan Deep Learning
Menggunakan representasi berbasis **Word Embedding**:
- **Word2Vec** — menangkap hubungan semantik antar kata.
- **FastText** — mampu memproses kata baru melalui *subword information*.

### 3️⃣ Pendekatan Transfer Learning
Menggunakan model pra-latih berbasis transformer:
- **IndoBERT**
- **XLM-RoBERTa**

---

## 📊 Evaluasi Model

Evaluasi dilakukan menggunakan metrik berikut:
- **Akurasi (Accuracy)**
- **Precision**
- **Recall**
- **F1-Score**
- **Cross Validation (k=5)**

Selain itu dilakukan juga **analisis kesalahan (error analysis)** untuk memahami performa tiap pendekatan.

---

## 🧩 Error Analysis

Tahap *error analysis* bertujuan untuk mengidentifikasi serta memahami pola kesalahan yang dilakukan oleh model dalam proses prediksi. Analisis ini membantu mengetahui jenis data yang salah diklasifikasi serta alasan di balik terjadinya kesalahan tersebut.

### 🔍 Langkah Analisis
1. Membandingkan antara label asli dan hasil prediksi model.  
2. Menghitung jumlah prediksi benar dan salah per model dan representasi fitur.  
3. Menganalisis penyebab kesalahan seperti ambiguitas kata, konteks kompleks, dan keterbatasan semantik model.

---

### 📊 Perbandingan Hasil Error Analysis

| Pendekatan | Representasi | Model | Akurasi (%) | Prediksi Benar | Prediksi Salah |
|-------------|---------------|--------|--------------|----------------|----------------|
| **Klasik** | BoW | Naive Bayes | 49.95 | 527 | 528 |
|  |  | SVM | 59.33 | 626 | 429 |
|  |  | Random Forest | 72.41 | 764 | 291 |
|  | TF-IDF | Naive Bayes | 75.35 | 795 | 260 |
|  |  | SVM | 70.14 | 740 | 315 |
|  |  | Random Forest | 72.51 | 765 | 290 |
| **Deep Learning** | FastText | Naive Bayes | 62.09 | 655 | 400 |
|  |  | SVM | 75.45 | 796 | 259 |
|  |  | Random Forest | 72.61 | 766 | 199 |
|  | Word2Vec | Naive Bayes | 64.08 | 676 | 395 |
|  |  | SVM | 75.55 | 797 | 258 |
|  |  | Random Forest | 72.61 | 766 | 289 |
| **Transfer Learning** | IndoBERT | Naive Bayes | 35.26 | 372 | 683 |
|  |  | SVM | 45.21 | 477 | 578 |
|  |  | Random Forest | 71.75 | 757 | 298 |
|  | XLM-RoBERTa | Naive Bayes | 42.46 | 448 | 607 |
|  |  | SVM | 38.01 | 401 | 654 |
|  |  | Random Forest | 71.37 | 753 | 302 |

---

### ⚖️ Analisis Perbandingan Antar Pendekatan

#### 🔹 Pendekatan Klasik
- TF-IDF menghasilkan performa lebih tinggi dibandingkan BoW.  
- **Naive Bayes + TF-IDF** mencapai akurasi 75.35%.  
- Model BoW lebih rentan terhadap kata umum dan ambiguitas.

#### 🔹 Pendekatan Deep Learning
- **SVM + Word2Vec** memberikan hasil terbaik (75.55%).  
- FastText mampu menangani kata baru dengan baik melalui *subword embeddings*.  
- Kesalahan klasifikasi berkurang dibanding pendekatan klasik.

#### 🔹 Pendekatan Transfer Learning
- IndoBERT dan XLM-RoBERTa belum optimal dengan model klasik.  
- Performa meningkat signifikan saat dipasangkan dengan **Random Forest**.  
- Diperlukan model klasifikasi lebih kompleks agar embedding kontekstual dimanfaatkan sepenuhnya.

---

### 🧠 Kesimpulan Error Analysis
- **Deep Learning (Word2Vec, FastText)** memberikan hasil paling stabil dan akurat.  
- **Klasik (TF-IDF)** tetap kompetitif, tetapi kurang adaptif terhadap konteks.  
- **Transfer Learning** berpotensi tinggi, namun butuh sumber daya komputasi dan tuning lanjutan.  

Dengan demikian, pendekatan **Deep Learning berbasis Word2Vec dan FastText** menjadi pilihan paling seimbang antara kompleksitas dan performa.

---

## 📈 Kesimpulan Akhir

- Pendekatan **Deep Learning** memberikan akurasi tertinggi dan konsistensi terbaik.  
- Pendekatan **Klasik** efektif untuk baseline dan analisis sederhana.  
- Pendekatan **Transfer Learning** menjanjikan hasil lebih baik bila menggunakan arsitektur end-to-end (misal fine-tuning full IndoBERT).  

---

## 💻 Teknologi yang Digunakan

- Python 3.x  
- Libraries: `scikit-learn`, `gensim`, `transformers`, `Sastrawi`, `pandas`, `numpy`, `matplotlib`  
- Model Pra-latih: **FastText (Bahasa Indonesia)**, **Word2Vec**, **IndoBERT**, **XLM-RoBERTa**

