# Home Credit Default Risk - Final Project Data Mining

## Deskripsi Final Project

Final project ini merupakan Final Project mata kuliah **Data Mining** yang bertujuan untuk melakukan **Data Exploration**, **Data Aggregation**, **Exploratory Data Analysis (EDA)**, **preprocessing**, **pemodelan machine learning**, dan **evaluasi dan analisis hasil** untuk memprediksi apakah seorang nasabah akan mengalami kesulitan pembayaran (default).

Dataset yang digunakan berasal dari kompetisi Kaggle:  
[Home Credit Default Risk](https://www.kaggle.com/c/home-credit-default-risk)

Final project ini menyajikan pipeline lengkap mulai dari:

- Pemahaman dataset
- Agregasi dan merging data multi-file
- Exploratory Data Analysis (EDA)
- Preprocessing data
- Modeling dengan multiple algorithms
- Stacking Ensemble
- Evaluasi performa
- **Perbandingan baseline vs full pipeline** untuk menunjukkan value dari data aggregation

---

## Anggota Tim

- **Thariq Agfi Hermawan** | 5025211215
- **Achmad Fajri Sudrajab** | 5025221104
- **Gayu Baruwa** | 5025221247

---

## Struktur Folder

```
fp-datmin/
│
├── datasets/                         # Dataset asli dari Kaggle
│   ├── application_train.csv
│   ├── application_test.csv
│   ├── bureau.csv
│   ├── bureau_balance.csv
│   ├── credit_card_balance.csv
│   ├── installments_payments.csv
│   ├── POS_CASH_balance.csv
│   └── previous_application.csv
│
├── processed/                        # Data hasil preprocessing (optional)
│   └── train_processed.csv          # Output dari main.ipynb
│
├── models/                           # Model trained dari full pipeline (optional)
│   ├── random_forest_model.pkl
│   ├── xgboost_model.pkl
│   ├── tabnet_model.zip
│   ├── scaler.pkl
│   ├── meta_model.pkl
│   └── model_comparison_results.csv
│
├── baseline_models/                  # Model trained dari baseline
│   ├── baseline_model_results.csv
│   └── baseline_features.csv
│
├── image/                            # Visualisasi
│
├── main.ipynb                        # Aggregation & EDA
├── preprocessing_and_modeling.ipynb  # Full Pipeline (Aggregated Data)
├── baseline_modeling.ipynb           # Baseline (Raw Data Only)
├── requirements.txt                  # Dependencies
└── README.md
```

---

## Cara Menjalankan

### 1. Clone Repository

```bash
git clone git@github.com:thoriqagfi/fp-datmin.git
cd fp-datmin
```

### 2. Download Dataset

Download dataset dari Kaggle:  
https://www.kaggle.com/c/home-credit-default-risk

Ekstrak dan masukkan semua file CSV ke folder `datasets/`

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

**Requirements:**

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- imbalanced-learn
- xgboost
- pytorch-tabnet

### 4. Jalankan Bagian 1 (jika belum)

- Buka `main.ipynb`
- Run All Cells
- Output: `processed/train_processed.csv`

### 5. Jalankan Bagian 2A - Baseline Modeling (Raw Data)

- Buka `baseline_modeling.ipynb`
- Run All Cells
- Waktu eksekusi: ~15-30 menit
- Output: Results di folder `baseline_models/`

**Tujuan:** Model baseline menggunakan `application_train.csv` saja (tanpa agregasi)

### 6. Jalankan Bagian 2B - Full Pipeline (Aggregated Data)

- Buka `preprocessing_and_modeling.ipynb`
- Run All Cells (sequential execution)
- Waktu eksekusi: ~15-30 menit
- Output: Semua models di folder `models/`

**Tujuan:** Model dengan data agregasi dari 7 tabel untuk perbandingan

### 7. Hasil

Setelah selesai, Anda akan memiliki:

- Baseline results di `baseline_models/` (raw dataset)
- Full pipeline results di `models/` (aggregated dataset)
- Model comparison untuk menunjukkan improvement dari aggregation
- Feature importance analysis
- Visualisasi ROC curves dan metrics

---

## Model Performance

Models yang telah dilatih dan dievaluasi:

| Model             | Task                                       |
| ----------------- | ------------------------------------------ |
| Random Forest     | Ensemble learning dengan decision trees    |
| XGBoost           | Gradient boosting untuk high performance   |
| TabNet            | Deep learning untuk tabular data           |
| Stacking Ensemble | Kombinasi ketiga model dengan meta-learner |

**Metrics yang dievaluasi:**

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC

### Hasil Baseline (Raw Dataset)

Model dilatih hanya dengan `application_train.csv` (**133 features**):

| Model             | Accuracy | Precision | Recall | F1-Score | ROC-AUC    |
| ----------------- | -------- | --------- | ------ | -------- | ---------- |
| Random Forest     | 0.7787   | 0.1911    | 0.5316 | 0.2812   | **0.7424** |
| XGBoost           | 0.8779   | 0.2741    | 0.3030 | 0.2879   | **0.7499** |
| TabNet            | 0.4899   | 0.1208    | 0.8386 | 0.2112   | **0.7279** |
| Stacking Ensemble | 0.7949   | 0.1928    | 0.4766 | 0.2746   | **0.6984** |

**Best Baseline Model:** XGBoost dengan ROC-AUC = **0.7499**

### Hasil Full Pipeline (Aggregated Dataset)

_Lihat file `models/model_comparison_results.csv` untuk hasil lengkap dengan data agregasi dari 7 tabel_

**Expected:** Performa lebih tinggi karena menggunakan informasi dari bureau, previous_application, credit_card_balance, dll.

### Key Insight

Perbandingan baseline vs full pipeline menunjukkan **value dari data aggregation** - model dengan data agregasi memiliki performa lebih baik karena:

- Lebih banyak features (dari 7 tabel vs 1 tabel)
- Informasi historis kredit dari bureau
- Riwayat aplikasi sebelumnya
- Pola pembayaran dari multiple sources

---

## Teknologi & Library

- **Python 3.8+**
- **Pandas & NumPy** - Data manipulation
- **Scikit-learn** - Machine learning algorithms
- **XGBoost** - Gradient boosting
- **PyTorch-TabNet** - Deep learning
- **Imbalanced-learn** - SMOTE-ENN
- **Matplotlib & Seaborn** - Visualisasi
- **Jupyter Notebook** - Development environment

---

## Notes

- **Bagian 1, 2A, dan 2B** sudah terpisah dalam notebook berbeda untuk kemudahan kolaborasi
- `main.ipynb`: Data Aggregation & EDA
- `baseline_modeling.ipynb`: Baseline model dengan raw data saja
- `preprocessing_and_modeling.ipynb`: Full pipeline dengan data agregasi
- Pastikan folder `processed/`, `models/`, dan `baseline_models/` tercipta otomatis saat running
- Model TabNet memerlukan PyTorch
- **Jalankan baseline_modeling.ipynb terlebih dahulu** untuk mendapatkan baseline comparison

---

## Referensi

- [Home Credit Default Risk Competition](https://www.kaggle.com/c/home-credit-default-risk)
- [Scikit-learn Documentation](https://scikit-learn.org/)
- [XGBoost Documentation](https://xgboost.readthedocs.io/)
- [TabNet Paper](https://arxiv.org/abs/1908.07442)
- [SMOTE-ENN for Imbalanced Data](https://imbalanced-learn.org/)
