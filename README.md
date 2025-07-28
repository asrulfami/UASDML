📚 Penjelasan Proyek dan Struktur Analisis
1. Hipotesis Awal / Null Hypothesis
Hipotesis awal:
"Kalimat dalam artikel ilmiah yang menyebutkan DOI dataset tidak memiliki hubungan signifikan terhadap tipe referensinya (Primary, Supplementary, Missing)."

Tujuan dari proyek ini adalah menguji hipotesis tersebut dengan data nyata dan algoritma klasifikasi teks.

2. Exploratory Data Analysis (EDA)
Membaca data label dari train_labels.csv

Mengekstrak kalimat dari file XML berdasarkan dataset_id

Melihat distribusi label:

Banyak yang Missing, lebih sedikit yang Primary

Contoh kalimat ditampilkan untuk masing-masing tipe referensi

Cek apakah ada bias, imbalance, atau data kosong

3. Model yang Digunakan dan Alasan
Logistic Regression

Cocok untuk klasifikasi teks

Efisien dan cukup kuat jika fitur direpresentasikan dengan baik (TF-IDF)

Dapat digunakan untuk multi-class classification

Naive Bayes

Model baseline cepat

Asumsi independen antar fitur (tidak selalu cocok untuk kalimat, tapi cukup baik sebagai perbandingan awal)

Fitur input: TF-IDF vector dari kalimat
Label target: tipe referensi (Primary, Supplementary, Missing)

4. Insight
Logistic Regression memiliki akurasi yang lebih baik dari Naive Bayes karena dapat memodelkan hubungan antar kata lebih kompleks

Model bisa mengalami kesulitan dalam membedakan antara Missing dan Supplementary karena kalimat yang sangat mirip

Jumlah data per label tidak seimbang, sehingga bisa memengaruhi performa

5. Kesimpulan
Hipotesis awal ditolak: kalimat dalam artikel memang mengandung informasi penting untuk menentukan tipe referensi dataset

Model Machine Learning sederhana seperti Logistic Regression dapat digunakan untuk membantu otomatisasi klasifikasi referensi ilmiah

Proyek ini menunjukkan bagaimana teknik Natural Language Processing (NLP) bisa diintegrasikan ke dalam proses ilmiah

👥 Pembagian Tugas (Tag Team GitHub)
1. Asrul Fami - 41522010123 - @asrulfami (Leader)
Membuat repository GitHub UASDML, mengelola branching dan pull request, integrasi akhir semua bagian.
2. Anggota 1
Bertugas melakukan Exploratory Data Analysis (EDA): melihat distribusi label, contoh kalimat, dan visualisasi awal.
3. Anggota 2
Fokus pada Ekstraksi Kalimat dari File XML menggunakan ElementTree, parsing dataset_id, dan cleaning text.
4. Annas wicaksono - 41522010211 - @annaswcksn
Membuat dan melatih Model Machine Learning (Logistic Regression dan Naive Bayes), termasuk splitting data dan validasi.
5. Andika Gusti Restu Putra - 41522010187 - @Dika0378
Menganalisis Hasil Model: evaluasi akurasi, confusion matrix, dan menulis insight dari performa model.

