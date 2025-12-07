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

---

## Anggota Tim

- **Thariq Agfi Hermawan** | 5025211215
- **Gayu Baruwa** | 5025221104
- **Achmad Fajri Sudrajab** | 5025221247

---

## Struktur Folder

```
fp-datmin/
│
├── datasets/                         # Dataset asli dari Kaggle
├── image/                            # Visualisasi
├── main.ipynb                        # BAGIAN 1: Data Aggregation & EDA
├── preprocessing_and_modeling.ipynb  # BAGIAN 2: Preprocessing & Modeling
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

### 5. Jalankan Bagian 2

- Buka `preprocessing_and_modeling.ipynb`
- Run All Cells (sequential execution)
- Waktu eksekusi: ~15-30 menit (tergantung spesifikasi)
- Output: Semua models di folder `models/`

### 6. Hasil

Setelah selesai, Anda akan memiliki:

- Trained models di `models/`
- Model comparison results (CSV)
- Feature importance analysis (CSV)
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

_Lihat file `models/model_comparison_results.csv` untuk hasil lengkap_

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

- **Bagian 1 dan 2** sudah terpisah dalam notebook berbeda untuk kemudahan kolaborasi
- File `main.ipynb` hanya berisi Data Aggregation & EDA
- File `preprocessing_and_modeling.ipynb` berisi semua preprocessing dan modeling
- Pastikan folder `processed/` dan `models/` tercipta otomatis saat running
- Model TabNet memerlukan PyTorch

---

## Referensi

- [Home Credit Default Risk Competition](https://www.kaggle.com/c/home-credit-default-risk)
- [Scikit-learn Documentation](https://scikit-learn.org/)
- [XGBoost Documentation](https://xgboost.readthedocs.io/)
- [TabNet Paper](https://arxiv.org/abs/1908.07442)
- [SMOTE-ENN for Imbalanced Data](https://imbalanced-learn.org/)
