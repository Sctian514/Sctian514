# Laporan Proyek Machine Learning - Samuel Cristian Saragih

## Domain Proyek

Domain yang dipilih untuk proyek machine learning ini adalah Keuangan, dengan judul Predictive Analytics : Predictive Analytics Gold Price

**Latar Belakang**:

Harga emas telah lama menjadi indikator penting dalam ekonomi global, berfungsi sebagai aset pelindung nilai terhadap inflasi, ketidakstabilan ekonomi, dan ketidakpastian pasar. Sebagai salah satu komoditas keras yang paling diminati, emas memiliki fluktuasi harga yang signifikan, dipengaruhi oleh berbagai faktor seperti nilai tukar mata uang, suku bunga, permintaan pasar, dan kondisi geopolitik. Namun, ketidakpastian pergerakan harga emas ini sering kali menjadi tantangan besar bagi investor, perusahaan, dan pemerintah dalam mengambil keputusan strategis terkait investasi dan perdagangan emas. Oleh karena itu, diperlukan solusi yang efektif untuk memprediksi harga emas di masa depan, sehingga dapat membantu mengurangi risiko dan mendukung pengambilan keputusan yang lebih akurat.

Masalah ini menjadi semakin relevan dengan meningkatnya popularitas investasi emas melalui berbagai instrumen modern seperti Exchange-Traded Funds (ETF) Emas dan perdagangan di pasar forex. Dengan risiko tinggi yang melekat pada investasi tersebut, terutama bagi investor individu yang tidak memiliki akses ke analisis data yang komprehensif, predictive analytics berbasis machine learning menjadi pendekatan yang sangat penting. Teknologi ini mampu memanfaatkan data historis untuk mengidentifikasi pola dan tren, sehingga menghasilkan prediksi harga emas yang lebih akurat dan dapat diandalkan. Dengan demikian, predictive analytics tidak hanya membantu investor mengurangi risiko kerugian tetapi juga meningkatkan potensi keuntungan.

Proyek ini bertujuan untuk membangun model prediksi harga emas menggunakan teknik machine learning dengan data historis harga emas sebagai input utama. Melalui analisis data time series, model ini akan mendeteksi pola yang relevan dan memanfaatkan algoritma seperti regresi, Long Short-Term Memory (LSTM), atau metode lainnya untuk memberikan prediksi harga emas di masa depan. Solusi ini diharapkan dapat memberikan manfaat luas, tidak hanya bagi investor individu tetapi juga bagi institusi keuangan dan perusahaan yang bergantung pada pergerakan harga emas. Dengan adanya alat prediktif yang efektif, pengguna dapat membuat keputusan berbasis data, mengoptimalkan strategi investasi, dan mengantisipasi risiko di tengah fluktuasi pasar yang dinamis.

## Business Understanding


### Problem Statements

Berdasarkan latar belakang di atas, berikut ini merupakan rincian masalah yang dapat diselesaikan pada proyek ini:
- Bagaimana menganalisa data harga Emas?
- Bagaimana cara mengolah data agar di latih dengan baik oleh model?
- Model yang seperti apa yang memiliki akurasi paling baik?

### Goals

Tujuan dari proyek ini adalah:
- Dapat memprediksi harga Emas dengan akurat menggunakan model machine learning.
- Melakukan analisa dan mengolah data yang optimal agar diterima dengan baik oleh model machine learning.
- Membandingkan beberapa algoritma model untuk menemukan akurasi terbaik.


    ### Solution statements

Solusi yang dapat dilakukan agar goals terpenuhi adalah sebagai berikut :


- Menangani missing value pada data.
  - Mencari korelasi pada data untuk mencari dependant variable dan independent variable.
  - Menangani outlier pada data dengan menggunakan Metode IQR.
  - Melakukan normalisasi pada data terutama pada fitur numerik.


- Berikut beberapa algoritma yang digunakan pada proyek ini :
  - Support Vector Machine (Support Vector Regression)
  - K-Nearest Neighbors
  - Boosting Algorithm (Gradient Boosting Regression)


- Melakukan hyperparameter tuning agar model dapat berjalan pada performa terbaik dengan menggunakan teknik Grid Search

## Data Understanding
Dataset yang digunakan pada proyek ini adalah dataset dari Kaggle yang berjudul Gold Price | 10 Years | 2013-2023

[https://www.kaggle.com/datasets/farzadnekouei/gold-price-10-years-20132023]

Dataset yang digunakan memiliki format .csv yang mempunyai total 2583 data dengan 7 kolom (Date,Price, Open, High, Low, Vol, Change %)

- Date    : Tanggal pencatatan Data
- Price   : Harga emas
- Open    : Harga buka dihitung perhari
- High    : Harga tertinggi perhari
- Low     : Harga terendah perhari
- Vol     : Volume transaksi
- Change% : Persentase perubahan harga emas

**Data visualiation**

![{62BCD9C3-EB07-455D-A97D-BFD8A34E876B}](https://github.com/user-attachments/assets/c0a83c33-b115-4cb2-8b64-7f3da09cc14c)

**Univariate Analysis**

![{0A645AD3-7D18-4508-8358-90720D2171B4}](https://github.com/user-attachments/assets/24604d2b-f41f-42da-aa54-b4c39c6b22d1)

**Multivariate Analysis**

![{0BCA7EEF-0C52-4956-AC1E-F6FECF23EFC5}](https://github.com/user-attachments/assets/1f409fb1-276f-43fe-87d9-2d0dd2d0cbdf)
![{D3E5AF2B-38CE-46D6-AFBC-C329E6E3A687}](https://github.com/user-attachments/assets/406029ff-6616-47b6-9a2e-3088c1fb5322)


## Data Preparation
Berikut ini merupakan tahapan-tahapan dalam melakukan pra-pemrosesan data:

**Melakukan Penanganan Missing Value**

Pada kasus ini dalam menangani Missing Value menggunakan library SimpleImputer, yang dimana library ini bertugas untuk mengisi kolom yang memiliki missing value dengan data mean (nilai rata-rata)

**Melakukan pembagian dataset**

Kita akan membagi dataset menjadi 2 yaitu sebagai train data dan test data. Train data digunakan sebagai training model dan test data digunakan sebagai validasi apakah model sudah akurat atau belum. Ratio yang umum dalam splitting dataset adalah 80:20, 80% sebagai train data dan 20% sebagai test data, sehingga kita akan menggunakan Ratio tersebut. Pembagian dataset dilakukan dengan modul train_test_split dari scikit-learn. Setelah melakukan pembagian dataset, didapatkan jumlah sample pada data latih yaitu 2066 sampel dan jumlah sample pada data test yaitu 517 sampel dari total jumlah sample pada dataset yaitu 2583 sampel.

**Menghapus fitur yang tidak diperlukan**

Karena kita tidak memerlukan fitur Date,Vol, dan Change%. kita akan menghapus fitur Date, Vol, dan Change%. 

**Data Normalization**

Normalisasi data digunakan agar model dapat bekerja lebih optimal karena model tidak perlu mengolah data dengan angka besar. Normalisasi biasanya mentransformasi data dalam skala tertentu. Untuk proyek ini kita akan normalisasi data 0 hingga 1 menggunakan MinMaxScaler.

## Modeling

Model yang akan digunakan proyek kali ini yaitu Support Vector Regression, Gradient Boosting, dan K-Nearest Neighbors.

**Support Vector Regression**

Support Vector Regression memiliki prinsip yang sama dengan SVM, namun SVM biasa digunakan dalam klasifikasi. Pada SVM, algoritma tersebut berusaha mencari jalan terbesar yang bisa memisahkan sampel dari kelas berbeda, sedangkan SVR mencari jalan yang dapat menampung sebanyak mungkin sampel di jalan. Untuk hyper parameter yang digunakan pada model ini adalah sebagai berikut :

- kernel : Hyperparameter ini digunakan untuk menghitung kernel matriks sebelumnya.
- C : Hyperparameter ini adalah parameter regularisasi digunakan untuk menukar klasifikasi yang benar dari contoh training terhadap maksimalisasi margin fungsi keputusan.
- gamma : Hyperparameter ini digunakan untk menetukan seberapa jauh pengaruh satu contoh pelatihan mencapai, dengan nilai rendah berarti jauh dan nilai tinggi berarti dekat.

**Kelebihan**

- Lebih efektif pada data dimensi tinggi (data dengan jumlah fitur yang banyak)
- Memori lebih efisien karena menggunakan subset poin pelatihan

**Kekurangan**

-Sulit dipakai pada data skala besar

**K-Nearest Neighbors**

K-Nearest Neighbors merupakan algoritma machine learning yang bekerja dengan mengklasifikasikan data baru menggunakan kemiripan antara data baru dengan sejumlah data (k) pada data yang telah ada. Algoritma ini dapat digunakan untuk klasifikasi dan regresi. Untuk hyperparameter yang digunakan pada model ini hanya 1 yaitu :

- n_neighbors : Jumlah tetangga untuk yang diperlukan untuk menentukan letak data baru

**Kelebihan**

- Dapat menerima data yang masih noisy
- Sangat efektif apabila jumlah datanya banyak
- Mudah diimplementasikan

**Kekurangan**

- Sensitif pada outlier
- Rentan pada fitur yang kurang informatif

**Gradient Boosting**

Gradient Boosting adalah algoritma machine learning yang menggunakan teknik ensembel learning dari decision tree untuk memprediksi nilai. Gradient Boosting sangat mampu menangani pattern yang kompleks dan data ketika linear model tidak dapat menangani. Untuk hyperparameter yang digunakan pada model ini ada 3 yaitu :

- learning_rate : Hyperparameter training yang digunakan untuk menghitung nilai koreksi bobot padad waktu proses training. Umumnya nilai learning rate berkisar antara 0 hingga 1
- n_estimators : Jumlah tahapan boosting yang akan dilakukan.
- criterion : Hyperparameter yang digunakan untuk menemukan fitur dan ambang batas optimal dalam membagi data

**Kelebihan**

- Hasil pemodelan yang lebih akurat
- Model yang stabil dan lebih kuat (robust)
- Dapat digunakan untuk menangkap hubungan linear maupun non linear pada data

**Kekurangan**

- Pengurangan kemampuan interpretasi model
- Waktu komputasi dan desain tinggi
- Tingkat kesulitan yang tinggi dalam pemilihan model

Untuk proyek kali ini kita akan menggunakan model K-Nearest Neighbors karena memiliki error (0.00001) yang paling sedikit daripada model yang lain. Namun tidak bisa dipungkiri model dari Gradient Boosting juga -memiliki error (0.000011) yang hampir seperti KNN.

## Evaluation

Untuk evaluasi pada machine learning model ini, metrik yang digunakan adalah mean squared error (mse). Dimana metrik ini mengukur seberapa dekat garis pas dengan titik data.


![Cuplikan layar_20241123_192853](https://github.com/user-attachments/assets/d35bf8c5-3213-43e7-9b8a-d58a8ea3a85f)


dimana : n = jumlah titik data Yi = nilai sesungguhnya Yi_hat = nilai prediksi

Menampilkan hasil akurasi dari beberapa model yang dipakai :
![{0A53B03E-94EB-4899-A268-AEDAA7DF71C8}](https://github.com/user-attachments/assets/789bf038-49ca-4803-92eb-bbdf3e8359b2)

![{979ACD69-47F9-4EB7-B532-08335B1DBE03}](https://github.com/user-attachments/assets/39dcd474-933f-43d5-8caf-3a0a7bef8342)


Untuk proyek kali ini terdapat model yang dapat berjalan dengan performa optimal yaitu K-Nearest Neighbor.

