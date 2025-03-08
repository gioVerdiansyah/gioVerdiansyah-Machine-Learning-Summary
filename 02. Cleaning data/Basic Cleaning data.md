## Mengganti nama kolom
Jika nama kolom terlalu banyak singkatan yang susah untuk di ingin kita bisa menggantinya dengan:
`df.rename({"<nama_col>": "<nama_baru>"}, axis=1)`

## Mengatasi missing values
1. __Hapus__
   Jika data yang miss hanya sedikit kita bisa langsung drop.
   `df.dropna()`
2. __Mengisi missing value (Imputasi)__
   Jika data lumayan banyak yang miss kita bisa mengisinya dengan:
   + Mean
     `df['<nama_col>'].fillna(df[<nama col>].mean())`
   + __Median__
     `df['<nama_col>'].fillna(df[<nama col>].median())`
   + __Modus__
     `df['<nama_col>'].fillna(df[<nama col>].mode())`
   + __Interpolasi__
     Jika ada berupa time series maka kita bisa menggunakan:
     `df.interpolate(method="linear")`
   + __Imputer__
     Kita bisa menggunakan teknik imputer dari sklearn.
     1. __SimpleImputer__
     2. __KNNImputer
1. Forward Fill dan Backward Fill
   Jika data tidak sedikit tidak banyak kita bisa menggunakan ffill dan bfill, contoh penerapan:
   `df[<nama_col>].fillna(method='ffill')`
2. __Tandai missing value dengan value baru__
   Contoh jika categorical kita menambahkan "unknown", contoh penerapan
   `df[<nama_col>].fillna("unknown")`
3. __Dengan menggunakan model untuk memprediksi__
   Cara ini bagus namun sedikit ribet.

## Mengatasi duplicate values
1. __Hapus__
   Jika data yang miss hanya sedikit kita bisa langsung drop.
   `df.drop_duplicates()`
2. __Menggabungkan atau Mengagregasi Data Duplikat__
   Kadang data duplikat masih berguna, jadi bisa digabung atau dirata-ratakan:
   `df.groupby(['kolom_1', 'kolom_2']).mean().reset_index()`
   Atau menggabungkan teks dari duplikasi:
   `df.groupby(['kolom_1'], as_index=False).agg({'kolom_2': ' '.join})`
3. __Menandai data duplikat__
   `df['is_duplicate'] = df.duplicated(keep='first')`
   Tambahkan `keep=first` jika ingin menandai hanya duplikat setelah baris pertama.

## Menangani data yang tidak konsisten
1. Cleaning text:
   + `df['nama_col'].str.title()` menjadikannya huruf besar di awal.
   + `df['nama_col'].str.lower()` menjadikkanya huruf kecil semua.
   + `df['nama_col'].str.upper()` menjadikkanya huruf besar semua.
   + `df['nama_col'].str.strip()` menghapus spasi awal dan akhir.
   + `df['nama_col'].str.replace('-', '')` menghilangkan / mengganti karakter tertentu
1. Standarisasi format data:
   + `pd.to_datetime(df['<nama_col>'], errors='coerce')` error coerce akan menjadikan value menjadi NaT (Not a Time) atau bisa di bilang missing value.
   + `df['<nama_col>'].astype(float)` Tipe bisa di sesuaikan dengan jenis kolom.

## Menangani data outliers
+ Menghapus outlier berdasarkan Quartile
	```python
	Q1 = df['harga'].quantile(0.25)
	Q3 = df['harga'].quantile(0.75)
	IQR = Q3 - Q1
	df = df[(df['harga'] >= Q1 - 1.5 * IQR) & (df['harga'] <= Q3 + 1.5 * IQR)]
	```
+ Menghapus outlier dengan batasan tertentu
  `df[df['<nama_col>'] <= <batasan>]`
+ Mengganti outlier dengan nilai maksimum/minimum yang wajar
	```python 
	df = df['harga'].clip(
		lower=df['harga'].quantile(0.05), 
		upper=df['harga'].quantile(0.95)
	)
	```


Selanjutnya kita bisa malakukan [[Common feature extraction|fitur ekstraksi]] pada data yang sudah bersih.