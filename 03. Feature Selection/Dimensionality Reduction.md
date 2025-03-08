Ini adalah versi lanjutan dari [[Feature Selection]] karena dapat mengubah fitur yang banyak dari ratusan sampai ribuan menjadi sedikit misal menjadi puluhan.

## **Linear Dimensionality Reduction (Berbasis Transformasi Linear)**

1. **Principal Component Analysis (PCA)**
	- Mengubah dataset ke dalam **principal components** yang mewakili variansi terbesar.
	- **Cocok untuk** dataset dengan banyak fitur numerik yang berkorelasi tinggi.
	- **Contoh:** Dataset dengan 100 fitur dapat direduksi menjadi 10 fitur utama yang tetap mencerminkan sebagian besar informasi.
	  
2. **Linear Discriminant Analysis (LDA)**
	- Mirip PCA, tetapi mempertimbangkan **kategori kelas** dalam dataset.
	- **Digunakan dalam klasifikasi** untuk mencari kombinasi fitur yang memisahkan kelas sebaik mungkin.
	- **Contoh:** Menganalisis dataset gambar wajah dan mengurangi dimensi untuk meningkatkan klasifikasi.
	  
3. **Factor Analysis (FA)**
	- Mengasumsikan bahwa ada **variabel laten** (tidak teramati) yang menyebabkan korelasi antara fitur.
	- **Banyak digunakan dalam ilmu sosial & ekonomi.**


## **Non-Linear Dimensionality Reduction (Untuk Data Kompleks & High-Dimensional)**

1. **t-Distributed Stochastic Neighbor Embedding (t-SNE)**
    - Cocok untuk **visualisasi data high-dimensional** dalam 2D/3D.
    - **Mengelompokkan data yang mirip ke dalam kelompok kecil.**
    - **Contoh:** Digunakan dalam Computer Vision untuk menampilkan distribusi gambar dalam 2D.
      
2. **Uniform Manifold Approximation and Projection (UMAP)**
    - Alternatif t-SNE yang lebih cepat dan lebih baik dalam mempertahankan struktur global.
    - **Cocok untuk** clustering dan visualisasi high-dimensional data.
      
3. **Autoencoders (Deep Learning Based)**
    - Model **Neural Network** yang dipakai untuk menyandikan data ke dalam dimensi yang lebih rendah lalu mendekodenya kembali.
    - **Digunakan untuk** reduksi dimensi gambar, deteksi anomali, dan rekonstruksi data.
    - **Contoh:** Mengurangi dimensi gambar 28x28 menjadi vektor 10 angka menggunakan Autoencoder.