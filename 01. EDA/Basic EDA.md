## Import datasets

Kita bisa menggunakan library _pandas_ dari python.
`import pandas as pd`
pandas seringkali di singkat menjadi pd (standart dari komunitas).

Untuk melakukan import data csv kita bisa menulisnya seperti ini:
`df = pd.read_csv("<file_path>.csv")` 
note: df singkatan dari dataframe

Di atas adalah untuk __CSV__ jika untuk excel bisa menggunakan `read_excel` dan lain-lainnya, silahkan lihat sugesti dari pd.read...

## Info

Kita bisa melihat informasi-informasi datasets dengan cara:
`df.info()`
Maka akan nampak seperti:
![[Pasted image 20250308002948.png|300]]
+ __RangeIndex__
  Adalah panjang dari sebuah datasets di atas, dimana RangeIndex di atas ada 918 entries maka artinya ada 918 row/sample data.
+ __Data columns__
  adalah total kolom yang dimiliki oleh datasets, bisa di liat di list kolomnya ada di bawahnya.
+ Angka pada __Non-Null__
  Menunjukkan angka yang menandakan bahwa apakah ada angka yang tidak full (dari rangeindex), jika tidak full pasti pada kolom tersebut terdapat null atau [[Basic Cleaning data#Menghapus missing values|missing value]].
  Bisa juga menegceknya dengan `df.isnull().sum()`
+ __Dtype__
  Adalah tipe-tipe dari setiap kolom masing-masing.
  note: jika kolom di nyatakan object oleh pandas namun nilai tersebut tidaklah benar, maka perlu di lakukan cleanning. Contoh kolom `tanggal_produksi` di nyatakan object namun seharusnya adalah datetime, begitu juga jika angka dan lain-lainnya.
+ Total tipe-tipe kolom bisa di lihat di bawah
+ __Memory usage__
  `memory_usage` dalam `df.info()` menunjukkan estimasi penggunaan memori dari DataFrame dalam **bytes (B)**. Ini membantu memahami seberapa banyak memori yang digunakan oleh setiap kolom dalam dataset.
  Gunakan parameter `memory_usage="deep"` untuk melihat seberapa banyak memori yang di gunakan keseluruhan (termasuk string)

## Preview datasets

Untuk melihat datasets kamu bisa menggunakan:
- `df.head()`
  digunakan untuk melihat data dari atas ke bawah, total panjang default adalah 5, kamu bisa mengganti total panjangnya di dalam kurung head.
- `df.tail()`
  Sama seperti head namun dari bawah datasets.
- `df`
  Menampillkan semua datasets.
  note: jika terlalu banyak akan di potong otomatis oleh notebook.
Data akan terlihat seperti:
![[Pasted image 20250308005324.png]]
## Describe datasets

Untuk melihat deskripsi datasets ada 2 cara yakni:
+ ### Number
  `df.describe()` untuk melihat semua deskripsi kolom, bisa juga satu atau beberapa kolom dengan cara:
  + `df["<nama kolom>"].describe()`
  + `df[["<nama kolom 1>", "nama kolom 2"]].describe()`
  Maka akan terlihat seperti:
  ![[Pasted image 20250308005502.png|500]]
  1. `count` melihat berapa total dari keseluruhan row/sample
  2. `mean` $\frac{\text{total\_data}}{\text{panjang\_data}}$ rata-rata dari semua nilai dalam kolom tersebut
  3. `std` (standard deviation) melihat seberapa jauh rentan data dari mean. 
     Contoh data age mean = 53 lalu memiliki std = 9 maka bisa di artikan age memiliki data di antara rentan 53 - 9 = 44 sampai 53 + 9 = 62. Atau bisa di simpulkan 53 $\pm$ 9
  4. `min` adalah angka terkecil di dalam kolom.
  5. `25%` $Q1 = (\frac{1}{4}(n + 1))$ 
     quartil 1 menandakan nilai di mana **25% data berada di bawahnya** (batas bawah dari 25% pertama).
  6. `50%` $Q1 = (\frac{2}{4}(n + 1))$ 
     quartil 2 atau median menandakan nilai tengah dataset (50% data di bawahnya dan 50% di atasnya).
  7. `75%` $Q3 = (\frac{3}{4}(n + 1))$  
     quartil 3 menandakan nilai di mana **75% data berada di bawahnya** (batas bawah dari 25% data terakhir).
  8. `max` adalah nilai tertinggi di dalam kolom.
  
  note: saya menggunakan `df.describe().T` agar data tertransform atau posisi row dan col terbalik

+ ### Categorical
  `df.describe(include="object")` untuk melihat data object.
  ![[Pasted image 20250308011357.png|400]]
  + `unique` adalah total value/nilai yang unik pada kolom tersebut.
    Contoh Male dan Female maka total unik adalah 2.
	Bisa juga mengecek manual dengan `df.nunique()`
  + `top` adalah berapa sering data muncul atau bisa di sebut modus.
  + `freq` adalah total banyak data modus yang muncul dalam kolom tersebut.

## Melihat data miss dan duplicate

+ __Melihat missing value__
  Kita bisa menggunakan perintah `df[<nama col>].isna().sum()` untuk melihat total missing value. Kita juga bisa membuatnya plot langsung dengan menambahkan `.plot` di belakang sum().
  Note: `isna()` dan `isnull()` itu sama.
+ __Melihat data duplicate__
  Gunakan `df[df.duplicated()]` untuk melihat kolom apa saja yang duplikat, dan gunakan `df.duplicated().sum()` untuk melihat keseluruhan duplicated.
  
  Namun kadang juga ada data yang duplikat namun tidak terdeteksi, misal data di bilang duplikat karena mirip atau mengandung arti yang sama, bisa di karenakan ada tambahan tanda baca, spasi, dan besar-kecil huruf.
  Kita bisa melihatnya dengan:
  `df[<nama col>].str.strip().str.lower()`
Untuk cleaning bisa lihat di [[Basic Cleaning data#Mengatasi missing values|cleaning missing values]] dan untuk duplikat [[Basic Cleaning data#Mengatasi duplicate values|cleaning duplicate values]]
## Melihat data anomali

+ ### Categorical
  Jika kamu tidak yakin total unique pada deskripsi di atas kita bisa melihat manual beserta valuenya dengan cara:
  + `df[<nama col>].unique()`
    Untuk melihat list values pada kolom yang dimaksud.
  + `df[<nama col>].nunique()`
    Melihat berapa total kolom unik
  + `df[<nama col>].value_counts()`
    Melihat berapa banyak frekuensi jumlah value pada kolom yang dimaksud.
  + `df[<nama col>].value_counts(normalize=True) * 100`
	Menjadikan frekuensi menjadi persentase dengan parameter `normalize=True` * 100 untuk
	menjadikan persentase (bukan 0.0....).
  + __[[Categorical Visualization#Countplot|Countplot]]__
    `sns.countplot(x=df[<nama col>])`
	Dari pada melihat dataframe kita bisa menggunakan searborn dan matplotlib untuk memvisualisasikannya dengan countplot dari seaborn.

+ ### Numerical
  + Cara mudah untuk melihat data anomali number kita bisa menggunakan describe, bisa kita lihat pada Q1 Q2 Q3 sampai max apakah datanya terurut dengan normal, jika pada max terdapat angka yang besar kemungkinan pada kolom tersebut ada anomali.
  + __[[Numerical Visualization#Boxplot|Boxplot]]__
    `sns.boxplot(x=df[<nama col>])` atau `df[<nama col>].plot.box()`
  + __[[Numerical Visualization#Scatterplot|Scatterplot]]__