# Deteksi Serangan Jaringan

Proyek ini merupakan eksperimen klasifikasi lalu lintas jaringan dengan pendekatan machine learning. Fokus utama adalah membedakan trafik normal dengan tiga jenis serangan umum yang berasal dari dataset simulasi. Algoritma yang digunakan adalah **Decision Tree**, terkenal karena kesederhanaannya dan kemampuannya dalam menangani data numerik yang kompleks.

---

## Deskripsi Singkat

Dalam jaringan komputer, lalu lintas tidak hanya mencerminkan aktivitas normal, tetapi juga dapat memuat serangan berbahaya yang sulit dikenali tanpa bantuan sistem otomatis. Dengan memanfaatkan algoritma pohon keputusan (Decision Tree), proyek ini berupaya:

- Mengelompokkan trafik berdasarkan jenisnya
- Mendeteksi potensi serangan siber
- Memberikan pemahaman visual melalui hasil evaluasi

---

## Dataset yang Digunakan

Kumpulan data yang dianalisis berasal dari simulasi trafik yang mewakili skenario nyata serangan di jaringan. Dataset yang digunakan meliputi:

1. **Recon Ping Sweep.csv**  
   Trafik hasil pemindaian (scanning) IP aktif dengan metode ICMP Echo untuk eksplorasi jaringan.

2. **DoS UDP Flood.csv**  
   Representasi trafik dari serangan **Denial of Service** yang membanjiri sistem dengan paket UDP.

3. **DDoS ICMP Flood.csv**  
   Trafik serangan terdistribusi (DDoS) yang menyerang dengan membanjiri jaringan menggunakan ICMP (ping) dari banyak sumber.

Semua dataset digabung untuk membentuk satu kumpulan data besar yang siap dianalisis.

---

## Pra-Proses Data

Sebelum model dilatih, dilakukan proses transformasi data untuk memastikan akurasi dan efisiensi:

- **Penggabungan Data**, Seluruh file .csv disatukan ke dalam satu DataFrame.
- **Pembersihan**, Penghapusan nilai yang hilang (missing) dan duplikat.
- **Seleksi Fitur**, Diambil fitur dari kolom ke-7 hingga ke-75 sebagai input model.
- **Penandaan Target**, Kolom `Label` dipakai untuk menandai apakah trafik merupakan serangan atau bukan.

---

## Konstruksi Model Decision Tree

Model klasifikasi dibangun menggunakan `DecisionTreeClassifier` dari library `scikit-learn`. Alasan pemilihan:

- Cocok untuk dataset bertipe numerik.
- Mudah ditafsirkan dan divisualisasikan.
- Mampu menangkap hubungan kompleks antar fitur.

Setelah data dibagi menjadi data latih dan data uji, model diuji menggunakan metrik  **Accuracy** dan **Confusion Matrix**.

---

## Hasil Evaluasi

Model Decision Tree mampu mengidentifikasi lalu lintas jaringan ke dalam kategori berikut:

- Trafik normal (benign)
- Serangan Recon (ping sweep)
- Serangan DoS berbasis UDP
- Serangan DDoS berbasis ICMP

Hasil menunjukkan bahwa meskipun model sederhana, Decision Tree cukup efektif dalam memberikan prediksi yang akurat pada pola trafik yang berbeda.

---

## Tools dan Library

Teknologi yang digunakan dalam proyek ini meliputi:

- `pandas`, `numpy` – manipulasi dan eksplorasi data.
- `scikit-learn` – pembuatan model dan evaluasi klasifikasi.
- `matplotlib`, `seaborn` – pembuatan grafik dan visualisasi hasil.

---

## Rencana Pengembangan

- Mengimplementasikan model pembanding seperti Random Forest.
- Melakukan tuning hyperparameter untuk peningkatan akurasi.
- Menambahkan deteksi berbasis data real-time.

---

