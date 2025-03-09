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

Tujuan linear regresi adalah mengurangi kesalahan di atas hingga menemukan garis yang sesuai dengan data tes. Untuk masalah regresi sederhana hal ini melibatkan intersep $y$ dan kemiringan model kita $\hat\beta_0$ dan $\hat\beta_1$
$$
\hat\beta_1 = \frac{\sum(x_i - \bar{x})(y_i - \bar{y})}{\sum(x_i - \bar{x})^2}
$$
$$
\hat\beta_0 = \bar{y} - \hat\beta_1 \bar{x}
$$
$\bar{x}$ adalah rata-rata nilai fitur.
$\bar{y}$ adalah rata-rata nilai target.

__Contoh perhitungan:__
$\bar{x} = 300$
$\bar{y} = 242000$

Hitung pembilang $\hat\beta_1$
$$
(100 - 300)(100000 - 242000) + (200 - 300)(180000 - 242000) + (300 - 300)(250000 - 242000) + (400 - 300)(31000 - 242000) + (500 - 300)(370000)
$$
$$(−200)(−142000)+(−100)(−62000)+(0)(8000)+(100)(68000)+(200)(128000)$$
$$28400000+6200000+0+6800000+25600000=67000000$$
Hitung penyebut $\hat\beta_1$
$$(100−300)^2+(200−300)^2+(300−300)^2+(400−300)^2+(500−300)^2$$
$$(−200)^2+(−100)^2+(0)^2+(100)^2+(200)^2$$
$$40000+10000+0+10000+40000=100000$$
$$\hat\beta_1 = \frac{67000000}{100000} = 670$$
Hitung $\hat\beta_0$
$$\hat\beta_0 = 242000 - (670 \times 300)$$
$$\hat\beta_0 = 242000 - 201000 = 41000$$

Setelah kita mendapatkan **$\hat{\beta_0}$ dan $\hat{\beta_1}$**, kita bisa menghitung **residual ($\hat{\epsilon}$)** untuk setiap titik data:
$$\hat\epsilon_i = y_i - \hat{y_i}$$
Diamana $\hat{y_i}$ adalah:
$$\hat{y_i} = \hat{\beta}_0 + \hat{\beta}_1x_i$$
Nilai $\hat\epsilon_i$ dapat di gunakan untuk evaluasi error model seperti:
+ __[[Mean Square Error (MSE)]]__
+ [[Mean Absolute Error (MAE)]]
+ [[R2 Squared]]
Note: nilai $y - \hat{y}$ sudah di hitung menjadi $\hat\epsilon$

![[Pasted image 20250309010014.png|500]]
Pada pelatihan di atas model kita sudah bisa menangkap garis yang di maksud meski masih ada sedikit error (ini normal).

Setelah kita melatih model kita, untuk melatih model kita sangat mudah, kita hanya perlu memasukkan nilai $x_i$ pada persamaan kita.
Contoh:

$sqft = 250$ 
$\hat{y} = 756.9 \cdot 350 - 27153.8$
$\hat{y} = 237761$

Model kita memprediksi harga rumah dengan square-footage 350 perkiraan berharga $237.761