# Home Credit Default Risk --- Final Project Data Mining

## 📌 Deskripsi Proyek

Proyek ini merupakan Final Project mata kuliah **Data Mining** yang bertujuan untuk melakukan **Data Exploration**, **Data Aggregation**, **Exploratory Data Analysis (EDA)**, **preprocessing**, **pemodelan machine learning**, dan **evaluasi dan analisis hasil** untuk memprediksi apakah seorang nasabah akan mengalami kesulitan pembayaran (default).

Dataset yang digunakan berasal dari kompetisi Kaggle:\
👉 *Home Credit Default Risk* ---
https://www.kaggle.com/c/home-credit-default-risk

Proyek ini menyajikan pipeline lengkap mulai dari:
- pemahaman dataset,
- aggregat dan merging data multi-file,
- EDA,
- preprocessing data,
- modeling,
- evaluasi performa.

------------------------------------------------------------------------

## 👥 Anggota Tim

  Nama                        NRP
  --------------------------- ------------
  **Thariq Agfi Hermawan**    5025211215
  **Gayu Baruwa**             5025221253
  **Achmad Fajri Sudrajab**   5025221254

------------------------------------------------------------------------

## Struktur Folder

    project/
    │
    ├── dataset/                # berisi seluruh file CSV dari Kaggle
    ├── main.ipynb # script utama
    ├── image/
    └── README.md

------------------------------------------------------------------------

## Dataset yang Digunakan

Setelah download dari Kaggle, masukkan semua file ke folder:

    dataset/

File penting:
- application_train.csv
- application_test.csv
- bureau.csv
- bureau_balance.csv
- previous_application.csv
- POS_CASH_balance.csv
- credit_card_balance.csv
- installments_payments.csv

------------------------------------------------------------------------

## Cara Menjalankan File ipynb

1.  Clone repository / download project:

        `git clone git@github.com:thoriqagfi/fp-datmin.git`
        `cd fp-datmin

2.  Download dataset Kaggle\
    https://www.kaggle.com/c/home-credit-default-risk

3.  Masukkan seluruh dataset ke folder:

        dataset/

4.  Install dependencies

5.  Jalankan notebook

------------------------------------------------------------------------

## 📊 Hasil Analisis & Model

Notebook mencakup: - EDA lengkap\
- Pembersihan data\
- Feature engineering\
- Modeling (Logistic Regression, Random Forest, LightGBM/XGBoost)\
- Evaluasi (ROC-AUC, F1-score, confusion matrix)

------------------------------------------------------------------------

## 📚 Teknologi

-   Python
-   Pandas, NumPy
-   Scikit-learn
-   Seaborn & Matplotlib
-   Jupyter Notebook