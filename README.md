🧐 UAS Data Mining & Learning: Klasifikasi Referensi Dataset Ilmiah

Proyek ini bertujuan untuk mengklasifikasikan tipe referensi dataset dalam artikel ilmiah berdasarkan kalimat yang memuat DOI (Digital Object Identifier). Proyek ini memanfaatkan teknik Natural Language Processing (NLP) dan algoritma machine learning sederhana seperti Logistic Regression dan Naive Bayes.

📌 1. Hipotesis Awal / Null Hypothesis

"Kalimat dalam artikel ilmiah yang menyebutkan DOI dataset tidak memiliki hubungan signifikan terhadap tipe referensinya (Primary, Supplementary, Missing)."

Proyek ini berupaya menguji hipotesis tersebut menggunakan data nyata dari kompetisi Kaggle Make Data Count - Finding Data References, serta pendekatan NLP dan machine learning.

📊 2. Exploratory Data Analysis (EDA)

Membaca label dari file train_labels.csv

Mengekstrak kalimat dari artikel XML (data/metadata/*.xml) berdasarkan dataset_id

Melihat distribusi label:

Banyak referensi yang bertipe Missing

Referensi Primary relatif sedikit

Menampilkan contoh kalimat untuk tiap tipe label

Cek ketidakseimbangan (imbalanced data), data kosong, dan potensi bias

🧹 Contoh kode:

<img width="579" height="295" alt="image" src="https://github.com/user-attachments/assets/9d1f8ef3-5d45-46c8-a5ea-b2dd63d2bdb4" />

🧮 3. Model dan Alasan Pemilihan

✅ Logistic Regression

Cocok untuk klasifikasi teks

Dapat menangani multi-kelas (multi-class classification)

Digabung dengan TF-IDF untuk representasi kata

⚙️ Naive Bayes

Model baseline yang cepat dan efisien

Bekerja baik pada data teks sederhana

Asumsi independensi antar fitur → bisa jadi kelemahan jika konteks antar kata penting

🧑‍💻 Contoh kode model:

<img width="575" height="459" alt="image" src="https://github.com/user-attachments/assets/cb404b53-e51f-4112-8088-f4d5f9273513" />

🔍 4. Insight

Logistic Regression menunjukkan akurasi yang lebih tinggi dibanding Naive Bayes, terutama dalam membedakan Primary dan Supplementary.

Data tidak seimbang (Missing sangat dominan), hal ini menurunkan performa model pada label minoritas.

Kalimat antar label sangat mirip, model butuh fitur yang kuat (TF-IDF bekerja cukup baik).

Penggunaan metode NLP sederhana sudah cukup untuk menghasilkan prediksi yang masuk akal.

✅ 5. Kesimpulan

Hipotesis awal ditolak → kalimat dengan DOI dalam artikel berkorelasi signifikan dengan tipe referensinya.

Logistic Regression terbukti efektif untuk tugas klasifikasi referensi dataset.

Proyek ini menunjukkan bagaimana NLP + ML bisa membantu otomasi dan analisis dalam publikasi ilmiah.

👥 Pembagian Tugas (Tag Team GitHub)

Asrul Fami - 41522010123 - @asrulfami📌 Leader, buat repo GitHub UASDML, integrasi, merge PR semua anggota.

Reyhan Vincent - 41522010142📊 Exploratory Data Analysis: analisis distribusi label, visualisasi, dan deskripsi awal.

Claudio Nehemia Panggabean - 41522010144🔍 Parsing XML dan ekstraksi kalimat berdasarkan dataset_id, cleaning, dan normalisasi teks.

Annas Wicaksono - 41522010211 - @annaswcksn🤖 Implementasi model Logistic Regression dan Naive Bayes, preprocessing TF-IDF, evaluasi awal.

Andika Gusti Restu Putra - 41522010187 - @Dika0378📈 Evaluasi akhir, membuat confusion matrix, membandingkan model, menyusun insight.
