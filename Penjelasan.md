Berikut adalah file **README.md** lengkap dalam format GitHub markdown, siap kamu unggah ke repositori: [https://github.com/asrulfami/UASDML/](https://github.com/asrulfami/UASDML/)

---

````markdown
# 📚 Laporan UAS Data Mining  
## Klasifikasi Referensi Dataset Menggunakan Algoritma SVM  

📌 **Link Repository**: [UASDML GitHub](https://github.com/asrulfami/UASDML/)  

### 👨‍💻 Disusun oleh:
- Asrul Fami – 41522010123  
- Reyhan Vincent – 41522010142  
- Claudio Nehemia Panggabean – 41522010144  
- Annas Wicaksono – 41522010211  
- Andika Gusti Restu – 41522010187  

> Program Studi Teknik Informatika  
> Fakultas Ilmu Komputer  
> Universitas Mercu Buana Jakarta  
> Tahun 2025  

---

## 1. 🧠 Hipotesis Awal / Null Hypothesis (20%)

**a. Hipotesis Awal (Null Hypothesis)**  
> Kalimat dalam artikel ilmiah yang mengandung DOI dataset tidak memiliki pengaruh signifikan terhadap klasifikasi tipe referensinya (Primary, Secondary, atau Missing).

**b. Hipotesis Alternatif**  
> Kalimat yang memuat referensi DOI memiliki pola teks tertentu yang dapat digunakan untuk memprediksi tipe referensinya.

🎯 **Tujuan Proyek**  
Membuktikan bahwa model machine learning dapat membedakan tipe referensi dari kalimat dalam artikel dengan akurasi tinggi berdasarkan fitur teks.

---

## 2. 🔍 Exploratory Data Analysis (EDA) (20%)

Dataset yang digunakan adalah `train_labels.csv`, berisi:
- `article_id`: ID artikel ilmiah,
- `dataset_id`: DOI dataset,
- `type`: label (Primary, Secondary, Missing)

📌 Jumlah Kalimat Setelah Preprocessing:
| Label     | Jumlah |
|-----------|--------|
| Secondary | 423    |
| Missing   | 257    |
| Primary   | 222    |
| **Total** | **902**|

📄 File XML digunakan untuk mengekstrak kalimat berdasarkan `dataset_id`, kemudian digabungkan dengan label yang sesuai.

### A. 📊 Visualisasi Distribusi Label

Distribusi label dalam dataset:

```python
import seaborn as sns
import matplotlib.pyplot as plt

plt.figure(figsize=(6,4))
sns.countplot(x='label', data=df_final, palette='Set2')
plt.title('Distribusi Label Referensi')
plt.xlabel('Tipe Referensi')
plt.ylabel('Jumlah Kalimat')
plt.show()
````

📌 **Hasil**:
Distribusi tidak seimbang namun masih bisa digunakan untuk pelatihan. Label *Secondary* paling dominan.

### B. 📈 Visualisasi Confusion Matrix

Evaluasi model dilakukan dengan confusion matrix:

```python
from sklearn.metrics import confusion_matrix, ConfusionMatrixDisplay

# Prediksi model
y_pred = model.predict(X_test)

# Confusion Matrix
cm = confusion_matrix(y_test, y_pred, labels=model.classes_)
disp = ConfusionMatrixDisplay(confusion_matrix=cm, display_labels=model.classes_)

plt.figure(figsize=(6,5))
disp.plot(cmap='Blues', values_format='d')
plt.title("Confusion Matrix - SVM")
plt.show()
```

📌 **Penjelasan:**

* Nilai diagonal = prediksi benar
* Nilai luar diagonal = salah klasifikasi
* Model cukup baik pada label *Missing* dan *Secondary*

---

## 3. 🤖 Model dan Alasan Pemilihan (20%)

Model utama yang digunakan adalah **Support Vector Machine (SVM)** dengan kernel linear, serta representasi fitur menggunakan **TF-IDF**.

**Alasan Pemilihan SVM:**

* Efektif untuk data teks berdimensi tinggi
* Akurat dalam klasifikasi multikelas
* Banyak digunakan dalam NLP (spam detection, sentiment analysis)

📌 **Model lain yang diuji**:

* Naive Bayes
* Logistic Regression
  Namun, SVM memberikan hasil terbaik pada dataset ini.

---

## 4. 💡 Insight dari Model (20%)

📈 **Hasil Evaluasi Klasifikasi (SVM):**

| Label     | Precision | Recall | F1-Score | Support |
| --------- | --------- | ------ | -------- | ------- |
| Missing   | 0.91      | 0.98   | 0.94     | 52      |
| Primary   | 0.89      | 0.91   | 0.90     | 44      |
| Secondary | 0.99      | 0.93   | 0.96     | 85      |

✅ **Akurasi Total Model**: **94%**

📌 **Insight Penting:**

* Model sangat baik dalam mendeteksi label *Missing* (recall 0.98)
* *Secondary* memiliki precision tertinggi (0.99)
* Kesalahan umum terjadi antara *Primary* dan *Secondary* karena kemiripan kosakata

---

## 5. ✅ Kesimpulan (20%)

Model klasifikasi berbasis **SVM + TF-IDF** terbukti efektif untuk mengklasifikasikan tipe referensi dataset dalam artikel ilmiah.

📌 **Kesimpulan Akhir**:

1. Hipotesis nol **ditolak** – tipe referensi dapat diprediksi dari kalimat menggunakan ML
2. Data kalimat artikel + label dari `train_labels.csv` dapat membentuk model klasifikasi yang andal
3. Model SVM + TF-IDF cocok dan **direkomendasikan** untuk klasifikasi teks serupa di masa depan

---

### 📁 Struktur File Repositori

```
📦 UASDML
 ┣ 📂 data/
 ┃ ┗ 📄 train_labels.csv
 ┃ ┗ 📄 articles/
 ┃ ┗ 📄 parsed_texts.csv
 ┣ 📂 notebooks/
 ┃ ┗ 📄 eda_svm_model.ipynb
 ┣ 📄 README.md
 ┗ 📄 requirements.txt
```

---

### ⚙️ Cara Menjalankan

1. Clone repositori:

```bash
git clone https://github.com/asrulfami/UASDML.git
cd UASDML
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Buka notebook:

```bash
jupyter notebook notebooks/eda_svm_model.ipynb
```

---

### 📞 Kontak

Untuk pertanyaan atau saran, silakan hubungi melalui [Issues](https://github.com/asrulfami/UASDML/issues).

---

```

---

Jika kamu ingin saya bantu buatkan juga versi PDF-nya (untuk laporan cetak), tinggal beri tahu saja. Bisa saya susun dengan cover, format baku laporan, dan grafik yang sesuai.
```
