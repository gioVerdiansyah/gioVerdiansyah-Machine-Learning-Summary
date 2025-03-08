## Lineplot
**Menampilkan tren atau perubahan data seiring waktu** atau sepanjang sumbu kontinu lainnya. Grafik ini biasanya digunakan untuk **menganalisis pola dalam data deret waktu (time series)** atau untuk **menunjukkan hubungan antara dua variabel numerik**.

__Kegunaan:__
1. **Menganalisis Tren Seiring Waktu**
    - Misalnya, melihat bagaimana harga saham, suhu, atau jumlah pengunjung berubah dari waktu ke waktu.
2. **Menunjukkan Hubungan antara Dua Variabel Numerik**
    - Jika satu variabel meningkat, apakah variabel lain ikut meningkat atau menurun?
3. **Membandingkan Beberapa Data Sekaligus**
    - Bisa digunakan untuk membandingkan beberapa kategori dalam satu grafik.
Contoh gambar:
![[Pasted image 20250308132255.png|400]]

## Heatmap
Digunakan untuk menampilkan nilai dalam bentuk warna. Biasanya digunakan untuk menunjukkan hubungan antar variabel atau distribusi data dalam sebuah matriks (correlation).
1. **Menampilkan Korelasi Antar Variabel**
    - Melihat hubungan antar fitur dalam dataset.
2. **Menunjukkan Pola atau Tren dalam Data**
    - Bisa digunakan untuk melihat pola nilai tinggi dan rendah dalam dataset.
3. **Visualisasi Matriks atau Tabel Data**
    - Misalnya dalam analisis **confusion matrix** pada machine learning.
Contoh gambar:
![[Pasted image 20250308105807.png|400]]


## Pieplot
**Menampilkan proporsi atau persentase dari suatu kategori dalam satu kelompok data**. Setiap bagian lingkaran (slice) mewakili bagian dari keseluruhan.

__Kegunaan:__
1. **Menampilkan Proporsi atau Persentase**
    - Digunakan untuk memahami bagaimana bagian-bagian kecil berkontribusi terhadap total.
2. **Membandingkan Kategori dalam Satu Variabel**
    - Cocok digunakan untuk kategori dengan jumlah terbatas, seperti distribusi jenis kelamin, pangsa pasar, atau penggunaan aplikasi.
3. **Memvisualisasikan Data yang Bersifat Diskret**
    - Berguna untuk data kategorikal, misalnya jumlah pengguna berdasarkan platform (Android vs iOS).
Contoh gambar:
![[Pasted image 20250308210646.png|400]]

## Histogram
Digunakan untuk menampilkan distribusi data numerik dengan cara membagi data ke dalam beberapa **bin (interval)** dan menghitung jumlah data dalam setiap bin tersebut.

__Kegunaan:__
1. **Melihat Distribusi Data**
    - Mengetahui apakah data terdistribusi normal, miring ke kiri/kanan, atau memiliki lebih dari satu puncak (bimodal/multimodal).
2. **Menganalisis Outlier**
    - Jika ada nilai yang jauh berbeda dari lainnya, histogram bisa membantu mengidentifikasinya.
3. **Menentukan Pola Data**
    - Mengetahui apakah data lebih terkonsentrasi di rentang tertentu atau tersebar luas.
Contoh gambar:
![[Pasted image 20250308104154.png|400]]

## Boxplot
**Boxplot (box-and-whisker plot)** adalah visualisasi statistik yang digunakan untuk menunjukkan distribusi data numerik berdasarkan **lima nilai utama**:
1. **Minimum** (nilai terkecil, kecuali ada outlier)
2. **Kuartil pertama (Q1)** – 25% data berada di bawah nilai ini
3. **Median (Q2)** – Nilai tengah data (50% data berada di bawahnya)
4. **Kuartil ketiga (Q3)** – 75% data berada di bawah nilai ini
5. **Maksimum** (nilai terbesar, kecuali ada outlier)
Contoh gambar:
![[Pasted image 20250308104834.png|350]]


## Scatterplot
Digunakan untuk menampilkan hubungan antara dua variabel numerik. Setiap titik dalam scatter plot mewakili satu data dengan koordinat **(x, y)**.

__Kegunaan:__
1. **Menunjukkan Hubungan Antar Variabel**
    - Scatter plot membantu memahami apakah ada **hubungan positif, negatif, atau tidak ada hubungan** antara dua variabel.
2. **Mengidentifikasi Pola dan Tren**
    - Bisa melihat apakah data memiliki pola linear, eksponensial, atau tidak beraturan.
3. **Mendeteksi Outlier**
    - Titik-titik yang jauh dari pola utama bisa dianggap sebagai **outlier**.
Contoh gambar:
![[Pasted image 20250308113122.png|400]]

## Pairplot
Menampilkan hubungan antar variabel numerik dalam dataset. Pair plot menampilkan scatter plot untuk setiap kombinasi pasangan variabel dan histogram (atau KDE) untuk distribusi masing-masing variabel.

__Kegunaan:__
1. **Melihat Hubungan Antar Variabel**
    - Dapat membantu memahami **korelasi antara variabel numerik** dalam dataset.
2. **Mendeteksi Pola dan Tren**
    - Jika ada pola linear atau non-linear dalam scatter plot, itu bisa menunjukkan **hubungan antara dua variabel**.
3. **Mengenali Outlier**
    - Titik-titik yang jauh dari pola utama menunjukkan **outlier dalam dataset**.
4. **Memeriksa Distribusi Data**
    - Histogram di diagonal pair plot menunjukkan **distribusi dari masing-masing variabel**.
Contoh gambar:
![[Pasted image 20250308120805.png|400]]


## KDE plot (Kernel Density Estimation Plot)
Digunakan untuk **memvisualisasikan distribusi probabilitas dari sebuah variabel numerik**. KDE plot adalah versi yang lebih halus dari histogram karena menampilkan estimasi kepadatan data secara kontinu.

__Kegunaan:__
1. **Menampilkan Distribusi Data dengan Lebih Halus**
    - Tidak seperti histogram yang bergantung pada jumlah bin, KDE plot memberikan estimasi yang lebih **smooth (halus)**.
2. **Membandingkan Distribusi dari Beberapa Kategori**
    - KDE plot bisa digunakan untuk membandingkan distribusi antara **dua atau lebih kelompok** dalam dataset.
3. **Mendeteksi Modus (Puncak Data)**
    - Jika terdapat **lebih dari satu puncak**, itu menunjukkan bahwa data memiliki **lebih dari satu modus** (multimodal).
4. **Menganalisis Bentuk Distribusi**
    - Memudahkan dalam melihat apakah data **berdistribusi normal**, **skewed (miring)**, atau memiliki pola tertentu.
Contoh gambar:
![[Pasted image 20250308121221.png|400]]