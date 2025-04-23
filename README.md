# 🍊 Oranges vs Grapefruit Classification using Decision Tree

Proyek ini bertujuan untuk mengklasifikasikan buah jeruk (orange) dan jeruk bali (grapefruit) menggunakan algoritma **Decision Tree**. Dataset yang digunakan mengandung fitur numerik seperti `diameter` dan `weight`, dengan label target berupa `name`.

---

## 📁 Dataset
Oranges vs. Grapefruit merupakan dataset klasifikasi biner yang berisi data buatan (simulasi) tentang dua jenis buah: jeruk dan anggur bali (grapefruit). Dataset ini mencakup fitur seperti warna (RGB), berat, dan diameter untuk merepresentasikan karakteristik rata-rata masing-masing buah.

<br>Catatan: Dataset ini sebagian besar fiktif, namun didasarkan pada pengamatan terhadap buah asli dan dimodifikasi untuk memperluas variasi data.

<br>Tujuan Dataset: Digunakan untuk latihan klasifikasi biner dalam konteks pembelajaran atau eksperimen model sederhana.

Label target:
- **Orange** (0)
- **Grapefruit** (1)

---

## 🔍 Exploratory Data Analysis (EDA)

EDA dilakukan untuk memahami distribusi fitur dan hubungan antar variabel:
- Visualisasi distribusi diameter dan berat
- Distribusi kelas (label)
- Korelasi antar fitur numerik
- Pengecekan missing values dan duplikasi

---

## 🧹 Preprocessing

Langkah-langkah preprocessing:
1. Encoding label (orange → 0, grapefruit → 1)
2. Split data (80% train, 20% test)
3. Standardisasi fitur numerik menggunakan `StandardScaler`

---

## 🤖 Model Training (Baseline)

Model awal dilatih menggunakan `DecisionTreeClassifier` tanpa tuning:
- Evaluasi menggunakan `classification_report` dan confusion matrix
- Akurasi awal sudah sangat baik (sekitar 95%)

---

## ⚙️ Hyperparameter Tuning

Model dioptimalkan menggunakan `GridSearchCV` dengan parameter grid:
- `criterion`: `gini`, `entropy`
- `max_depth`: `3`, `5`, `7`, `10`, `None`
- `min_samples_split`: `2`, `5`, `10`, `20`
- `min_samples_leaf`: `1`, `2`, `4`
- `max_features`: `None`, `sqrt`, `log2`

Metrik evaluasi: **F1-score**, dengan cross-validation (`cv=5`).

---

## 🏁 Best Model Training & Evaluation

Setelah tuning, model terbaik dilatih ulang dengan parameter optimal:
- Performa model hampir sama dengan model awal (f1-score ±95%)
- `diameter` menjadi fitur paling penting berdasarkan feature importance

---

## 📊 Visualisasi

1. **Confusion Matrix** (sebelum dan sesudah tuning)
2. **Feature Importance**
3. **Decision Tree Visualization** (full & depth-limited untuk keterbacaan)

---

## 📌 Kesimpulan

- Decision Tree efektif untuk klasifikasi dua kelas dengan fitur numerik yang jelas.
- Hasil tuning tidak memberikan peningkatan signifikan karena model awal sudah cukup optimal.
- Fitur `diameter` sangat dominan dalam menentukan klasifikasi buah.

---

## 🧑‍💻 Author

Tugas Klasifikasi Buah - Proyek UTS Prak. ML
