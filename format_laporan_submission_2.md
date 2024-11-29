# Laporan Proyek Machine Learning - Samuel Cristian Saragih

## Project Overview

Industri hiburan, khususnya perfilman, mengalami pertumbuhan yang pesat dalam beberapa tahun terakhir, dengan begitu banyaknya pilihan film yang tersedia di berbagai platform streaming. Di tengah banyaknya pilihan yang ada, seringkali pengguna kesulitan menemukan film yang sesuai dengan selera mereka. Untuk itu, sistem rekomendasi film menjadi salah satu solusi untuk membantu pengguna menemukan film yang relevan dengan preferensi pribadi mereka. Sistem rekomendasi berbasis konten dan kolaboratif kini banyak digunakan oleh berbagai platform streaming seperti Netflix, Hulu, dan Disney+ untuk memberikan pengalaman pengguna yang lebih personal dan relevan.

Model rekomendasi film berbasis machine learning telah menjadi pusat perhatian dalam penelitian dan aplikasi teknologi kecerdasan buatan (AI). Dengan memanfaatkan data historis pengguna, genre film, serta preferensi yang terungkap dari interaksi sebelumnya, sistem ini dapat mengidentifikasi pola-pola tertentu yang dapat digunakan untuk merekomendasikan film-film yang sesuai. Teknik-teknik seperti Collaborative Filtering dan Content-Based Filtering telah banyak diterapkan untuk membangun sistem rekomendasi yang efektif. Oleh karena itu, penting bagi para pengembang dan peneliti untuk terus meningkatkan akurasi dan relevansi dari rekomendasi yang diberikan melalui penerapan model machine learning yang lebih canggih, yang dapat lebih memahami kebutuhan dan selera pengguna.

 

## Business Understanding

### Problem Statements

Berdasarkan latar belakang di atas, rincian masalahnya adalah sebagai berikut:
- Bagaimana cara melakukan pra-pemrosesan pada data movie recomendation yang akan digunakan agar dapat membuat model yang baik menggunakan teknik content-base filtering?
- Bagaimana memberikan rekomendasi judul film berdasarkan genre pada setiap judul film yang pelanggan input sehingga dapat memberikan preferensi yang sesuai pelanggan inginkan?

### Goals

Berdasarkan  pertanyaan di atas, maka tujuannya sebagai berikut:

- Sistem rekomendasi yang baik akan membuat pengguna kembali lebih sering, meningkatkan retensi.
- Menyediakan rekomendasi film yang lebih akurat dan sesuai dengan genre yang disukai pengguna.

## Data Understanding
Dataset yang digunakan pada proyek ini adalah dataset dari Kaggle yang berjudul Movie Recommender System Dataset

 [(https://www.kaggle.com/datasets/sayan0211/movie-recomendation-pjct?select=movies.csv)]

Dataset yang digunakan memiliki format .csv yang mempunyai total 9741 data dengan 3 kolom (movieId, title, genres)
- movieId : id movie.
- title   : judul movie.
- genre   : genre movie


**Exploratory Data Analysis**

**Mengecek missing value**

![{D51BADF3-CF87-4A80-B93A-E8FCA1C7D7BA}](https://github.com/user-attachments/assets/8a25dd34-35a1-4d80-81d8-cff43a64a265)

dari gambar di atas tidak missing value.

**Univariate Analysis**

![{749B7856-635D-408A-AFD7-D440264C57C0}](https://github.com/user-attachments/assets/64c72324-683e-4411-8fc5-084d58af0cc8)

Sebagian besar sampel film dari dataset movies ber-genre drama dan comedy, hal tersebut menunjukkan bahwa film yang tersedia lebih banyak ber-genre drama dan comedy.

## Data Preparation
Berikut merupakan tahapan-tahapan dalam melakukan data preparation:

- Menghapus Data Duplikat
Proses ini dilakukan dengan menggunakan fungsi drop_duplicates() agar tidak ada data yang memiliki nilai sama untuk mencegah kekeliruan.

- Mengonversi Data Series Menjadi Bentuk List
Proses ini dilakukan dengan menggunakan fungsi tolist() agar data lebih mudah diproses pada tahap pemodelan.

Teknik yang digunakan pada tahapan Proses Data adalah vektorisasi fungsi CountVectorizer dari library scikit-learn. CountVectorizer digunakan untuk mengubah teks yang diberikan menjadi vektor berdasarkan frekuensi (jumlah) setiap kata yang muncul di seluruh teks. CountVectorizer membuat matriks di mana setiap kata unik diwakili oleh kolom matriks, dan setiap sampel teks dari dokumen adalah baris dalam matriks. Nilai setiap sel tidak lain adalah jumlah kata dalam sampel teks tertentu.Pada proses vektorisasi ini, digunakan metode sebagai berikut.

- fit metode berfungsi untuk melakukan perhitungan idf pada data
- get_feature_names_out() berfungsi untuk melakukan mapping array dari fitur index integer ke fitur nama

  ![{49528DE3-C0F5-40C1-BD11-55209D5FA4D8}](https://github.com/user-attachments/assets/1a467abe-d2ec-4c81-ba35-0b026691f52e)

- fit_transform() berfungsi untuk mempelajari kosa kata dan Inverse Document Frequency (IDF) dengan memberikan nilai return berupa document-term matrix

  ![{3AFCA78E-9E87-404F-BADA-78F5CBA26F86}](https://github.com/user-attachments/assets/08d6ac4e-7bf6-446e-a888-df19f768ae5f)

- todense() berfungsi untuk mengubah vektor tf-idf dalam bentuk matriks

  ![{68346F9A-572E-4663-87A7-F5D2FE190487}](https://github.com/user-attachments/assets/2c2069a0-645a-4a1f-bf0b-3d45dac8a663)


## Modeling
Setelah data selesai disiapkan, proses selanjutnya adalah membuat model adapun tahap-tahapnya diantaranya sebagai berikut:
- Mengukur tingkat kesamaan dengan Cosine Similarity.
Setelah data dikonversi menjadi bentuk vektor, selanjutnya ukur tingkat kesamaan antara dua vektor dan menentukan apakah kedua vektor tersebut menunjuk ke arah yang sama. Semakin kecil sudut cosinus, semakin besar nilai cosine similarity.Berikut cara melatih model dengan menggunakan consine similarity yg dapat dilihat pada gambar dibawah brikut ini:

  ![{25441324-E679-427B-AF7F-620B776519A0}](https://github.com/user-attachments/assets/a3805843-0b13-40f3-9e30-d0aa702b1197)

- Pada tahapan ini menampilkan matriks kesamaan setiap judul dengan menampilkan judul film dalam 5 sampel kolom (axis = 1) dan 10 sampel baris (axis=0).

  ![{49957BF5-8014-40CE-A308-6FF2836EE1DD}](https://github.com/user-attachments/assets/27cc9c3b-f7d4-4ab0-a825-c41cc8345f04)

- Membuat Fungsi movie_recommendations(). Tahap terakhir dari proses modeling adalah membuat fungsi untuk mendapatkan hasil top-N recommendation, kali ini fungsinya dinamakan movie_recommendations(). Cara kerja dari fungsi ini yaitu menggunakan fungsi argpartition untuk mengambil sejumlah nilai k tertinggi dari similarity data (dalam kasus ini: dataframe cosine_sim_df). Kemudian mengambil data dari bobot (tingkat kesamaan) tertinggi ke terendah. Data ini lalu dimasukkan ke dalam variabel closest. Berikutnya menghapus movie_title yang dicari menggunakan fungsi drop() agar tidak muncul dalam daftar rekomendasi. Penjelasan parameter dari fungsi movie_recommendations() adalah sebagai berikut:

  - movie_title : Judul film (index kemiripan dataframe) (str)
  - similarity_data : Kesamaan dataframe simetrik dengan judul film sebagai indeks dan kolom (object)
  - items : Mengandung kedua nama dan fitur lainnya yang digunakan untuk mendefinisikan kemiripan (object)
  - k : Banyaknya jumlah rekomendasi yang diberikan (int)


## Results
Setelah model selesai dibuat, panggil model untuk menampilkan hasil rekomendasi, sebagai contoh kita gunakan judul film Precious (2009) untuk menguji model.

![{8DA54029-13CA-4891-A121-24AA18C9F83C}](https://github.com/user-attachments/assets/0d429a97-7bd5-4bbf-908b-ed5ca24f0f4f)

Dapat dilihat  bahwa film Precious (2009) merupakan film dengan genre drama. Selanjutnya kita lihat rekomendasi film yang sesuai dengan genre yang sama dengan film tersebut.

![{7D5C2DE5-5EFE-4424-8DAB-B5BB15849ACC}](https://github.com/user-attachments/assets/c33be8c0-0c37-41ef-9f7d-6d02db5bc390)

model berhasil menampilkan rekomendasi film berdasarkan genrenya.


## Evaluation

Karena model yang digunakan untuk proyek kali ini adalah Content-Based Filtering, maka metrik yang cocok untuk digunakan adalah Precision. Secara matematis dapat dirumuskan sebagai berikut:

![{3D3A8B3A-8F78-45FE-84A3-89C8562B5EDC}](https://github.com/user-attachments/assets/716200b1-d8cf-4e0e-a25c-a49e1ca3bdb6)

Berdasarkan hasil rekomendasi dapat disimpulkan bahwa dari 10 judul film yang direkomendasikan, ada 10 film yang relevan oleh karena itu nilai Precision dari model ini adalah 10/10 atau 100%.

**Kesimpulan**

Setelah melalui proses yang panjang, mulai dari mempersiapkan dataset hingga melakukan evaluasi, akhirnya sistem rekomendasi dengan pendekatan Machine Learning Content-Based Filtering pun selesai dirancang dan hasilnya pun cukup memuaskan yaitu dari 10 judul film yang direkomendasikan, terdapat 10 film yang relevan dengan judul film yang diuji yang menandakan precision dari model ini adalah 100%.


