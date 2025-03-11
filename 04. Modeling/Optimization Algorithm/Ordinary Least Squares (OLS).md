Metode analitik untuk mencari koefesien terbaik dalam [[Linear Regression]].
Metode ini **menggunakan rumus matematika tertutup (closed-form solution)** untuk menghitung nilai $\beta_0$ dan $\beta_1$ secara lansung. 

__Rumus OLS:__
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

Nilai $\hat\epsilon_i$ dapat di gunakan untuk melihat jarak error residual data.