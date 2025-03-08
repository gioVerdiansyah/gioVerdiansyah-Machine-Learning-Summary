## Normalisasi dan standarisasi data Numerical

+ ### __Normalisasi__
  1. Min-Max Scaling
     Mengubah nilai menjadi rentan tertentu, biasanya di rentan 0 sampai 1 atau -1 sampai 1.
     Cocok untuk algoritma berbasis jarak seperti **KNN dan SVM**.
     
  2. Robust Scaling 
     Menggunakan median dan Inquartile range(IQR) untuk mengurangi efek outliers.
     Cocok untuk data dengan banyak **outlier**.
     
  3. Log Transformation
     Mengurangi skewness pada distribusi data yang **tidak normal** dengan mengambil **logaritma** dari nilai.
     Cocok untuk data dengan **skewness tinggi (distribusi miring ke kanan)**.
     
  4. Decimal Scaling
     Membagi nilai dengan pangkat dari 10 hingga semua nilai berada dalam rentang -1 sampai 1.
     Cocok untuk dataset numerik dengan **nilai besar**.
     
  5. Power Transformation (Box-Cox & Yeo-Johnson)
     - **Box-Cox:** Hanya untuk **data positif**.	
     - **Yeo-Johnson:** Bisa untuk **data negatif dan nol**.  
     Digunakan untuk membuat data lebih **normal (Gaussian-like)** sebelum digunakan dalam model linear.

+ ### Standarisasi
  
  1. Z-Score normalization
     Mengubah data sehingga memilki __mean__ = 0 dan __standar deviasi__ = 1.
     Cocok untuk algoritma seperti **Linear Regression, Logistic Regression, PCA**, dan model berbasis gradien.

  2. Mean normalization
     Menggeser nilai agar memiliki __mean__ = 0 dan rentan di antara -1 sampai 1.
     Berguna untuk beberapa model linear agar lebih stabil.
     
  3. Unit Vector Scaling (Normalization to Unit Norm)
     Memproyeksikan vector data ke dalam panjang 1 dengan membagi nilai dengan __L1 norm__ (panjang vector).
     Cocok untuk **algoritma berbasis jarak**, seperti **KNN dan SVM**.
     
  4. Whitening (Sphering Transformation)
     Mengubah data agar memiliki __mean__ = 0 dan __covariance matrix__ = __identity matrix__
     Digunakan di **PCA dan Deep Learning** untuk **dekorrelasi fitur**.


## Encoding data Categorical
### 1. Label Encoding

- **Deskripsi:** Mengonversi setiap kategori menjadi bilangan bulat unik.
- **Kelebihan:** Sederhana dan efisien secara memori.
- **Keterbatasan:** Tidak cocok untuk data nominal karena dapat secara tidak sengaja mengindikasikan adanya urutan antar kategori.
---
### 2. Ordinal Encoding

- **Deskripsi:** Mirip dengan label encoding, namun digunakan untuk variabel yang memiliki urutan alami (ordinal).
- **Contoh:** Kategori seperti _rendah_, _sedang_, _tinggi_ dapat diubah ke angka (misalnya 1, 2, 3).
- **Catatan:** Pastikan hanya digunakan bila memang ada urutan yang bermakna.
---
### 3. One-Hot Encoding

- **Deskripsi:** Membuat kolom biner terpisah untuk setiap kategori, di mana setiap kolom menunjukkan keberadaan (1) atau ketidakhadiran (0) kategori tersebut.
- **Kelebihan:** Ideal untuk data nominal karena tidak mengasumsikan adanya hubungan ordinal antar kategori.
- **Keterbatasan:** Dapat menyebabkan peningkatan jumlah fitur secara drastis (curse of dimensionality) pada data dengan banyak kategori.
---
### 4. Binary Encoding

- **Deskripsi:** Menggabungkan kelebihan label encoding dan one-hot encoding. Kategori pertama-tama diubah ke dalam bentuk angka (seperti label encoding), kemudian dikonversi ke representasi biner dan dipisahkan ke dalam beberapa kolom.
- **Kelebihan:** Mengurangi dimensi data secara signifikan dibandingkan one-hot encoding, terutama untuk kategori dengan cardinality tinggi.
---
### 5. Frequency (Count) Encoding

- **Deskripsi:** Mengganti setiap kategori dengan frekuensi kemunculan atau proporsi relatifnya dalam dataset.
- **Kelebihan:** Sederhana dan mempertahankan informasi tentang seberapa sering kategori tersebut muncul.
- **Catatan:** Berguna bila frekuensi kategori memberikan informasi tambahan bagi model.
---
### 6. Hashing Encoding

- **Deskripsi:** Menggunakan fungsi hash untuk memetakan kategori ke dalam sejumlah kolom tetap, tanpa perlu mengetahui daftar lengkap kategori di muka.
- **Kelebihan:** Efisien untuk data dengan cardinality sangat tinggi dan ketika menginginkan ukuran fitur yang tetap.
- **Keterbatasan:** Potensi terjadinya collision (dua kategori berbeda mendapat representasi yang sama) sehingga bisa kehilangan informasi.
---
### 7. Target Encoding

- **Deskripsi:** Mengganti kategori dengan statistik target (misalnya rata-rata nilai target) untuk masing-masing kategori.
- **Kelebihan:** Dapat menangkap informasi yang berkaitan dengan prediksi secara langsung, terutama pada masalah supervised learning.
- **Keterbatasan:** Rentan terhadap overfitting, sehingga perlu dilakukan validasi atau regularisasi yang tepat.
---
### 8. Leave-One-Out Encoding

- **Deskripsi:** Merupakan varian dari target encoding yang menghitung rata-rata target untuk suatu kategori dengan cara mengecualikan data saat itu sendiri (leave-one-out) guna mengurangi bias overfitting.
- **Kelebihan:** Menawarkan perbaikan atas target encoding standar dengan pengurangan risiko overfitting.
- **Catatan:** Tetap memerlukan teknik validasi yang hati-hati.
---
### 9. Embedding Encoding

- **Deskripsi:** Umumnya digunakan dalam deep learning, di mana setiap kategori diwakili oleh vektor berdimensi rendah yang dipelajari selama proses training.
- **Kelebihan:** Mampu menangkap hubungan yang kompleks antar kategori dan dapat digunakan dalam jaringan saraf untuk meningkatkan kinerja model.
- **Keterbatasan:** Membutuhkan data yang cukup besar dan proses training yang lebih kompleks.