Regresi linier sederhana adalah bentuk dasar regresi linier yang berhubungan dengan prediksi hasil numerik (variabel dependen) berdasarkan fitur input tunggal (variabel independen). Ini adalah cara mudah untuk memodelkan dan memahami hubungan antara dua variabel.

Variabel:
	Dalam linear regresi sederhana kita memliki 2 variabel utama:
	1. Dependen variabel ($y$), variabel yang di gunakan untuk predict.
	2. Independen variabel ($x$), Ini adalah fitur atau input tunggal yang memiliki pengaruh kepada variabel Dependen.

Linear Regression pada Machine Learning adalah __supervised__ agoritma yang belajar untuk menghasilkan variabel $y$ secara terikat dari variabel-variabel $x_i$ atau fitur untuk mencari garis terbaik pada suatu data.

Kita ansumsikan $y$ adalah suatu angka di dalam banyak variabel $x_i$ yang bisa berupa apa saja, misal: harga, suhu, berat dan macam-macam angka lainnya.

Secara umum persamaan regresi linear terlihat seperti ini:
$$
y = \beta_0 + \beta_1x_1 + \beta_2x_2 + ... + \beta_nx_n + \epsilon
$$
Atau bisa di artikan:
$$
y = \beta_0 + \sum_{i=1}^{n} \beta_i x_i + \epsilon
$$
Atau simpelnya
###### __persamaan dasar Simple Linear Regression__
setelah mendapatkan best param adalah seperti ini:
$$y = \beta_0 + \beta_1x$$

$y$ : dependen variabel, hasil dari prediksi
$\beta_i$ : koefesiensi dari model kita, ini adalah dasar dari model kita, apa yang model kita pelajari sebelum nantinya di optimasi.
$x_i$ : independent variabel, fitur-fitur yang digunakan untuk menghasilkan variabel dependen
$\epsilon$ : Kesalahan yang tidak dapat di reduksi oleh model.

#### __Melatih Linear Regression__ 
adalah tentang mencari himpunan koefisiensi untuk menemukan $y$ terbaik.
Kita mungkin tidak pernah tahu true parameter untuk model kita, tapi kita bisa memperkirakan dengan koefesien ini:
$$
\hat{y} = \hat\beta_0 + \hat\beta_1x_1 + \hat\beta_2x_2 + ... + \hat\beta_nx_n
$$
Jadi untuk memprediksi nilai fitur adalah semudah kita memasukkan nilai fitur kita $x_i$ kedalam persamaan.

### Bagaimana itu bekerja?
Contoh persebaran data yang kita punya seperti:

| sftf ($x$) | price $y$ |
| ---------- | --------- |
| 100        | 100.000   |
| 200        | 180.000   |
| 300        | 250.000   |
| 400        | 310.000   |
| 500        | 370.000   |

Dan data tampak seperti ini (contoh saja):
![[Pasted image 20250309000838.png|500]]

Mari kita latih untuk predict harga rumah di San Diego dalam dolar dengan menggunakan ukuran dari rumah (in square-footage / $sqft$).

$house\_price = \hat\beta_1 \cdot sqft + \hat\beta_0$

Untuk mem-predict harga dari setiap rumah hanya perlu menjadikan harga rumah menjadi rata-rata di dalam datasets kita: ~$242.000.

$house\_price = 0 \cdot sqft + 242000$

![[Pasted image 20250309002040.png|500]]
Tentu model kita sangat buruk dan tidak cocok dengan data sama sekali.
Untuk mengukur seberapa kesalahan secara kuantitatif. Ukur jarak antara setiap hasil prediksi dengan nilai test.

Tujuan linear regresi adalah mengurangi kesalahan di atas hingga menemukan garis yang sesuai dengan data tes. Untuk masalah regresi sederhana hal ini melibatkan intersep $y$ dan kemiringan model kita $\hat\beta_0$ dan $\hat\beta_1$ dapat di cari nilai koefisien nya menggunakan salah satu rumus __[[Ordinary Least Squares (OLS)]]__.
OLS akan menghasilkan nilai error residual($\hat\epsilon$) yang dapat berguna untuk menghitung jarak error dengan nilai aslinya.

![[Pasted image 20250309010014.png|500]]
Pada pelatihan di atas model kita sudah bisa menangkap garis yang di maksud meski masih ada sedikit error (ini normal).

Setelah kita melatih model kita, untuk melatih model kita sangat mudah, kita hanya perlu memasukkan nilai $x_i$ pada persamaan kita.
Contoh:

$sqft = 250$ 
$\hat{y} = 41000 + 670 \times 250$
$\hat{y} = 208.500$

Model kita memprediksi harga rumah dengan square-footage 250 perkiraan berharga $208.500

## Next of Simple Linear Regression 
Kita sudah bisa memahami basic linar regression dengan cukup baik.
Untuk catatan tambahan bentuk dari keseluruhan simple linear regression seperti ini
![[Pasted image 20250309203435.png|500]]
Note: simbol $\theta_1 = \hat\beta_0$ dan $\theta_2 = \hat\beta_1$
