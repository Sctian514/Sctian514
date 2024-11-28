# Laporan Proyek Machine Learning - Samuel Cristian Saragih

## Project Overview

Industri hiburan, khususnya perfilman, mengalami pertumbuhan yang pesat dalam beberapa tahun terakhir, dengan begitu banyaknya pilihan film yang tersedia di berbagai platform streaming. Di tengah banyaknya pilihan yang ada, seringkali pengguna kesulitan menemukan film yang sesuai dengan selera mereka. Untuk itu, sistem rekomendasi film menjadi salah satu solusi untuk membantu pengguna menemukan film yang relevan dengan preferensi pribadi mereka. Sistem rekomendasi berbasis konten dan kolaboratif kini banyak digunakan oleh berbagai platform streaming seperti Netflix, Hulu, dan Disney+ untuk memberikan pengalaman pengguna yang lebih personal dan relevan.

Model rekomendasi film berbasis machine learning telah menjadi pusat perhatian dalam penelitian dan aplikasi teknologi kecerdasan buatan (AI). Dengan memanfaatkan data historis pengguna, genre film, serta preferensi yang terungkap dari interaksi sebelumnya, sistem ini dapat mengidentifikasi pola-pola tertentu yang dapat digunakan untuk merekomendasikan film-film yang sesuai. Teknik-teknik seperti Collaborative Filtering dan Content-Based Filtering telah banyak diterapkan untuk membangun sistem rekomendasi yang efektif. Oleh karena itu, penting bagi para pengembang dan peneliti untuk terus meningkatkan akurasi dan relevansi dari rekomendasi yang diberikan melalui penerapan model machine learning yang lebih canggih, yang dapat lebih memahami kebutuhan dan selera pengguna.

 

## Business Understanding

Pada bagian ini, Anda perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements

Berdasarkan latar belakang di atas, rincian masalahnya adalah sebagai berikut:
-Model Machine Learning apa yang cocok untuk menyelesaikan permasalahan tersebut?
-Bagaimana cara menentukan hasil rekomendasi suatu model Machine Learning dapat dikatakan baik?


### Goals

Berdasarkan  pertanyaan di atas, maka tujuannya sebagai berikut:

- Model yang cocok untuk menyelesaikan masalah tersebut adalah model yang berbasis dengan konten atau biasa disebut Content-Based Filtering. Melakukan evaluasi terhadap metrik dari model Machine Learning tersebut.
- Menjelaskan tujuan proyek yang menjawab pernyataan masalah:


**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Approach” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution approach (algoritma atau pendekatan sistem rekomendasi).

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai jumlah data, kondisi data, dan informasi mengenai data yang digunakan. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya, uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data beserta insight atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
