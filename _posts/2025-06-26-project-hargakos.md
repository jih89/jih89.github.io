---
layout: post
title: "Prediksi Harga Sewa Kos di Makassar dengan Data Mining"
date: 2025-06-26 15:15:00 +0800
categories: [project, data-science, machine-learning]
tags: [data-mining, xgboost, web-scraping, regression, portfolio]
author_profile: true
description: "Riset mengenai penetapan harga sewa kos yang subjektif di Kota Makassar"
---

Di Kota Makassar, banyak pemilik kos masih menetapkan harga sewa kos mereka berdasarkan intuisi, yang berisiko membuat mereka kehilangan pendapatan atau kamar tidak tersewa. Kami melihat adanya kebutuhan akan alat bantu berbasis data untuk membantu mereka membuat keputusan harga yang lebih objektif. 

Maka dari itu, riset ini bertujuan untuk mengembangkan model prediksi harga sewa kos di Kota Makassar menggunakan teknik data mining dan machine learning. Model ini bertujuan untuk membantu pemilik properti dalam menetapkan harga sewa yang objektif dan kompetitif berdasarkan analisis data.

Hasil dari riset ini telah kami susun dalam sebuah paper ilmiah berjudul **“Pengembangan Model Prediksi Harga Sewa Kos di Makassar Menggunakan Teknik Data Mining”**.

### Pendekatan
Untuk mengatasi masalah ini, tim kami melakukan pendekatan *data-driven* yang komprehensif:
1.  **Mengumpulkan Data:** Kami melakukan *web scraping* terhadap 1.162 listing kos dari platform Mamikos.com. 
2.  **Memperkaya Data:** Kami menerapkan *feature engineering* yang unik, termasuk mengubah fasilitas menjadi data biner dan menghitung jarak spasial dari setiap kos ke kampus-kampus utama di Makassar. 
3.  **Membangun Model:** Kami melatih dan mengevaluasi beberapa model regresi *machine learning* untuk menemukan yang paling akurat dalam memprediksi harga.

### Temuan Utama
Setelah melalui proses pemodelan dan evaluasi yang ketat, model terbaik kami, **XGBoost Regressor**, menunjukkan hasil yang sangat menjanjikan. 
> Model ini mampu **menjelaskan 60,6% variasi harga sewa** di pasar Makassar. 

Salah satu temuan paling menarik adalah faktor apa yang paling dominan dalam menentukan harga. Seperti yang terlihat pada grafik di bawah, **ketersediaan AC** menjadi prediktor harga yang jauh lebih kuat dibandingkan faktor lainnya.

![Grafik Feature Importance](assets/feature_importance.png)
*Gambar: 10 Fitur Teratas yang Paling Berpengaruh Terhadap Harga Sewa Kos.*

---

### Baca Paper Lengkapnya
Tertarik untuk mengetahui lebih dalam tentang metodologi, perbandingan model, dan analisis lengkap kami? Silakan unduh dan baca paper lengkapnya melalui tautan di bawah ini.

Di dalam paper, Anda akan menemukan:
* Penjelasan detail tentang proses *web scraping* dan *feature engineering*.
* Analisis statistik mengenai penanganan *outlier*.
* Perbandingan performa mendalam antara model Random Forest dan XGBoost.
* Diskusi lengkap mengenai implikasi praktis dari penelitian ini bagi pemilik properti.

<a href="https://file.notion.so/f/f/02f6e15c-418d-403d-a309-45b923161c7a/822696e5-0c98-4fd9-b80f-3bb0ea1827c1/Paper_Kelompok_5.pdf?table=block&id=21cab827-d1cd-80e9-a944-c6d5cb9196c6&spaceId=02f6e15c-418d-403d-a309-45b923161c7a&expirationTimestamp=1750946400000&signature=aalf5EQhYKOOiVCWB0bLOzvY_XcsOOFls-KrOJ4SAU8&downloadName=Paper_Kelompok+5.pdf" target="_blank" class="btn btn-primary" mb-2>
  Unduh atau Baca Paper Lengkap
</a>

---

### Acknowledgement
Penelitian ini adalah buah kerja sama tim yang luar biasa, terdiri dari: Muh. Tegar Adyaksa, Athifah Nur Rahman MD, M. Ervin, Cholyn Sharon Enos, dan saya sendiri, Imam Ahmad Mirza. 

Kami juga mengucapkan terima kasih sebesar-besarnya kepada dosen pengampu mata kuliah Data Mining, **Bapak Dr. Eng. Supri Bin Hj. Amir, S.Si., M.Eng.**  dan **Bapak Octavian, S.Si., M.Kom.**, atas bimbingan dan arahan yang sangat berharga.