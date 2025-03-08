## Countplot
Digunakan untuk menampilkan jumlah kemunculan data dalam kategori tertentu. Countplot cocok untuk **data kategorikal**, bukan numerik.

__Kegunaan:__
1. **Melihat Distribusi Kategori**
    - Menampilkan jumlah sampel dalam setiap kategori.
    - Misalnya, jumlah pengguna berdasarkan jenis kelamin (Laki-laki/Perempuan).
2. **Membandingkan Kategori**
    - Bisa digunakan untuk membandingkan jumlah item dalam berbagai grup.
    - Contoh: Jumlah pelanggan berdasarkan metode pembayaran (Cash, Transfer, e-Wallet).
3. **Analisis Data Kategorikal**
    - Berguna dalam eksplorasi data (EDA) untuk melihat apakah ada ketidakseimbangan kategori dalam dataset.
    - Contoh: Melihat apakah jumlah positif dan negatif dalam dataset klasifikasi seimbang.
Contoh gambar:
![[Pasted image 20250308104401.png|330]]

## Stripplot
Mirip dengan **scatter plot**, tetapi digunakan untuk menampilkan **distribusi data kategori** dengan menyusun titik-titik data secara acak di sepanjang satu sumbu.

**Strip plot sering digunakan sebagai alternatif untuk swarm plot jika ada banyak data yang tumpang tindih.**

__Kegunaan:__
1. **Setiap titik mewakili satu data**
    - Semakin banyak titik dalam suatu kategori, semakin banyak data dalam kelompok tersebut.
2. **Jika titik-titik bertumpuk vertikal, berarti ada nilai yang berulang**
    - Strip plot tidak memisahkan titik yang tumpang tindih secara otomatis seperti swarm plot.
3. **Lebar penyebaran tidak berarti variasi**
    - Strip plot hanya menyebarkan titik secara horizontal untuk visualisasi, bukan menunjukkan variasi sebenarnya dalam data.
Contoh gambar:
![[Pasted image 20250308114108.png|400]]

## Swarmplot
Menampilkan distribusi data kategori dengan **menyebarkan titik-titik data secara non-overlapping**.

**Berbeda dengan scatter plot atau strip plot**, swarm plot mengatur posisi titik agar tidak saling bertumpuk sehingga distribusi data lebih mudah dipahami.

__Kegunaan:__
1. **Menampilkan Distribusi Data**
    - Setiap titik merepresentasikan **satu data**, jadi kita bisa melihat penyebaran data secara lebih jelas.
2. **Membandingkan Data Antar Kategori**
    - Misalnya, melihat distribusi nilai ujian dari beberapa kelas yang berbeda.
3. **Melihat Pola Outlier**
    - Titik-titik yang jauh dari kumpulan utama bisa diidentifikasi sebagai **outlier**.

Contoh gambar:
![[Pasted image 20250308113740.png|400]]

## Violinplot
Visualisasi data yang menggabungkan **boxplot** dan **density plot** untuk menunjukkan distribusi data secara lebih mendetail.

__Kegunaan:__
1. **Menunjukkan Distribusi Data**
    - Seperti **boxplot**, tetapi dengan tambahan **kepadatan data**.
2. **Membandingkan Beberapa Grup**
    - Bisa digunakan untuk membandingkan distribusi **beberapa kategori dalam satu grafik**.
3. **Menampilkan Outlier & Variabilitas Data**
    - Memungkinkan kita melihat **simetri**, **sebaran**, dan **skewness** dalam dataset.
Contoh gambar:
![[Pasted image 20250308112101.png|400]]