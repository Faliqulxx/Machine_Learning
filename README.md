Klasifikasi Polaritas Berita Ekonomi Indonesia (Detik.com)
----------------------------------------------------------

Proyek ini melakukan klasifikasi sentimen (Positif, Netral, Negatif) pada berita ekonomi Indonesia dari Detik.com. Pendekatan yang digunakan meliputi metode klasik (TF-IDF, BoW), deep learning (Word2Vec, FastText), dan transformer (IndoBERT, XLM-RoBERTa).

============================================================
1. Struktur Folder
============================================================

.
├── data/
│   ├── raw/              # Data hasil scraping
│   ├── processed/        # Data setelah preprocessing
├── models/
│   ├── classical/
│   ├── deep_learning/
│   ├── transformer/
├── notebooks/
│   ├── scraping.ipynb
│   ├── preprocessing.ipynb
│   ├── training.ipynb
├── utils/
│   ├── preprocessing.py
│   ├── train_utils.py
├── requirements.txt
└── README.txt


============================================================
2. Instalasi
============================================================

1. Clone repository:
   git clone https://github.com/username/nama-repo.git
   cd nama-repo

2. (Opsional) Buat virtual environment:
   python -m venv env
   source env/bin/activate        # Linux/Mac
   env\Scripts\activate           # Windows

3. Install dependencies:
   pip install -r requirements.txt


============================================================
3. Cara Menjalankan
============================================================

1. Menjalankan Web Scraper:
   python scraping.py
   atau buka notebook:
   notebooks/scraping.ipynb

2. Preprocessing Data:
   python preprocess.py

3. Training Model:
   a. Metode Klasik (TF-IDF / BoW)
      python train_classical.py

   b. Deep Learning (Word2Vec / FastText)
      python train_embeddings.py

   c. Transfer Learning (IndoBERT / XLM-RoBERTa)
      python train_transformer.py


============================================================
4. Hasil Ringkas
============================================================

Pendekatan - Model - Akurasi Tertinggi
--------------------------------------
Klasik: TF-IDF + Naive Bayes .......... 75.35%
Deep Learning: Word2Vec + SVM ......... 75.55%
Transformer: Embedding + Random Forest  71.75%

Deep Learning (Word2Vec / FastText) memberikan performa paling stabil.


============================================================
5. Teknologi
============================================================

- Python 3.x
- scikit-learn
- gensim
- transformers
- Sastrawi
- FastText
- Word2Vec
- IndoBERT
- XLM-RoBERTa


============================================================
6. Contributor
============================================================

- Faliqul Ishbah
- Tiko Dava
- Ganesha Mahardika Prasetya
