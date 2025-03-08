Feature selection adalah  fitur-fitur yang akan digunakan untuk model. Fitur yang saya maksud disini adalah input atau kolom untuk model kita berlatih dan predict, secara kasarnya bahan belajar model kita.

Sebelum memilih fitur-fitur kita harus melakukan dan memahami:
1. Tujuan dan masalah.
2. Datasets.
3. Kolom dan value dalam datasets.
4. [[Basic Cleaning data|Membersihkan data / cleaning data]]
5. Model Machine/Deep Learning yang akan di gunakan.


Setelah memahami data dengan melakukan EDA dan visualisai, kita seharusnya bisa menentukan fitur-fitur yang cocok / berkorelasi dengan target.

Di atas adalah memilih fitur secara manual atau bisa dinamakan __Manual feature extraction__ atau __Expert-Driven Feature Selection__.

Namun jika fitur terlalu banyak dan yang mengumpulkan data menjadi datasets bukanlah kita. Maka kita bisa menggunakan algoritma untuk menentukan fitur.

Terkadang menentukan fitur oleh mesin bisa lebih baik karena data didalam fitur di lihat oleh mesin bukan manusia, namun kekurangannya terkadang fitur yang dipilih oleh mesin kurang ideal untuk dunia bisnis.


## Algoritma rekomendasi fitur

+ ### Berbasis statistik
  Filter methods mengevaluasi fitur secara independen dari model dengan menggunakan statistik atau korelasi.
  
	1. __Correlation__
	   Teknik paling dasar untuk melihat hubungan variabel dengan terget adalah dengan melihat variabel-variabel yang berhubungan dengan target. Kita bisa melihatnya dengan [[Numerical Visualization#Heatmap|memvisualisasikannya dengan heatmap]]
	2. **Variance Threshold**
	   Menghapus fitur dengan variansi rendah (misalnya fitur yang hampir konstan).
	3. __Chi-Square Test__
	   Digunakan untuk fitur kategorikal dan melihat hubungan dengan target.
	4. __Mutual Information (MI)__
	   Mengukur ketergantungan antara fitur dan target.
	5. __ANOVA (Analysis of Variance)__
	   Mengukur apakah fitur berpengaruh secara signifikan terhadap target dalam data kategorikal.
	6. __F-Score (F-Test)__
	   Mirip dengan ANOVA, digunakan untuk mengukur hubungan antara fitur numerik dan target kategorikal.
	   
+ ### **Wrapper Methods** (Menggunakan Model)
  Wrapper methods menggunakan model Machine Learning untuk mengevaluasi subset fitur.
  
	1. __Forward Selection__
	   Menambahkan fitur satu per satu berdasarkan peningkatan performa model.
	2. __Backward Selection__
	   Menghapus fitur satu persatu dan melihat peningkatan atau penurunan model.
	3. __Sequential Feature Selection (SFS/SBS)__
	   Kombinasi forward dan backward selection untuk mencari subset fitur terbaik.
	4. __Recursive Feature Elimination (RFE)__
	   Menggunakan model untuk memilih fitur paling penting, kemudian menghapus fitur dengan kontribusi kecil secara bertahap.

+ ### **Embedded Methods** (Terintegrasi dalam Model)
  Embedded methods melakukan pemilihan fitur saat model dilatih, sehingga lebih efisien daripada wrapper methods.
  
	1. __LASSO Regression__ (L1 Regularization)
	   Menghapus fitur yang koefisiennya menjadi nol karena penalti L1.
	2. __Ridge Regression__ (L2 Regularization)
	   Menurunkan bobot fitur dengan dampak kecil tanpa menghilangkannya.
	3. __Random Forest__ Importance dan __Decision Tree__
	   Menggunakan model RF atau DT untuk melihat fitur yang berpengaruh.
	4. __XGBoost Feature__ Importance
	   Memanfaatkan model XGBoost untuk menilai kepentingan fitur berdasarkan split gain.