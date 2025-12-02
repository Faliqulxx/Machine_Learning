# 📰 Klasifikasi Polaritas Berita Ekonomi Indonesia (Detik.com)

Proyek ini melakukan analisis sentimen pada berita ekonomi Indonesia dari Detik.com dan mengklasifikasikan polaritas berita menjadi **Positif**, **Netral**, dan **Negatif**.  
Pendekatan yang diuji meliputi:

- **Metode Klasik:** Bag-of-Words, TF-IDF  
- **Deep Learning Embeddings:** Gru, LSTM 
- **Transfer Learning:** IndoBERT 

Tujuan penelitian adalah membandingkan performa model dari berbagai pendekatan representasi teks dan algoritma klasifikasi.

---

## 📁 Struktur Folder

```
.
├── Dataset/
│   ├── raw.csv                         # Data hasil scraping dari Detik
│   ├── berita_detik_news_label.csv     # Data setelah di label    
|   ├── berita_detik_news_processed.csv # Data setelah preprocessing
├── Notebooks/
│   ├── scraping.ipynb
│   ├── preprocessing.ipynb
│   ├── trainer/
|       ├── classical.ipynb
|       ├── depp_learning.ipynb
|       ├── transfer_learning.ipynb
├── requirements.txt
└── README.md
```

---

## ⚙️ Instalasi

### 1️⃣ Clone Repository
```bash
git clone https://github.com/Faliqulxx/Machine_Learning
cd nama-repo
```

### 2️⃣ Buat Virtual Environment (Opsional)
Linux/Mac:
```bash
python -m venv env
source env/bin/activate
```

Windows:
```bash
python -m venv env
env\Scripts\activate
```

### 3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

---

## ▶️ Cara Menjalankan

### 1. Menjalankan Web Scraper
```bash
notebooks/scraping.ipynb
```

### 2. Preprocessing Data
```bash
notebooks/preprocessing.ipynb
```

### 3. Training Model
```bash
notebooks/trainer/...

```

## 📊 Ringkasan Hasil

| Pendekatan               | Model                  | Akurasi    |
|--------------------------|------------------------|------------|
| **Klasik**               | TF-IDF + Naive Bayes   | **75.35%** |
| **Deep Learning**        | Gru + LSTM             | **59,71%** |
| **Transfer Learning**    | indoBERT               | **52,89%** |

---

## 🧠 Insight Penelitian

- Metode klasik (TF-IDF) memberikan baseline kuat, namun kurang menangkap konteks.  
- Gru & LSTM menangani semantik lebih baik sehingga performanya stabil.  
- Embedding IndoBERT belum optimal saat diklasifikasi dengan model klasik—perlu fine-tuning full model agar lebih maksimal.

---

## 🛠 Teknologi yang Digunakan

- Python 3.x  
- scikit-learn  
- gensim  
- transformers (HuggingFace)  
- Sastrawi  
- FastText  
- Word2Vec  
- IndoBERT, XLM-RoBERTa  

---

## 👨‍💻 Contributor

- **Faliqul Ishbah**  
- **Tiko Dava**  
- **Ganesha Mahardika Prasetya**

---

