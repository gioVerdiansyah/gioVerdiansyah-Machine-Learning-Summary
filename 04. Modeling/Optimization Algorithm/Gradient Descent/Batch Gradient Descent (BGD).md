Gradient Descent adalah algoritma optimasi yang digunakan untuk meminimalkan fungsi kesalahan (loss function) dengan cara memperbarui parameter model secara iteratif ke arah negatif dari gradien.

__Rumus BGD:__
$$
	\theta_j := \theta_j - \alpha\frac{1}{m} \sum_{i=1}^m \frac{\partial}{\partial\theta_j} J(\theta)
$$
$\theta_j$ : Parameter yang akan di perbarui
$\alpha$ : Learning rate, menentukan seberapa besar angka langkah pembaruan parameter
$m$ : Panjang data dari 1 batch
$\sum_{i=1}^m$ : Menjumlahkan seluruh gradient dari semua data dalam 1 batch
$\frac{\partial}{\partial\theta_j} J(\theta)$ : Turunan parsial fungsi cost/loss terhadap parameter $\theta_0$
$J(\theta)$ : Fungsi cost/loss function, biasanya menggunakan [[Mean Square Error (MSE)]]

Contoh perhitungan meminimalkan fungsi cost function MSE untuk [[Linear Regression]]:
Ansumsikan parameter $\beta$ dari Linear Regression adalah $\theta$

$$
J(\theta_0, \theta_1) = \frac{1}{2m} \sum_{i=1}^{m}(h_\theta(x_i) - y_i)^2
$$
Note:
	>Apa maksud dari $2m$ pada pembagi di atas? 
	<Karena pada $\frac{1}{2m}$ atau $\frac{1}{m}$ adalah trik matematis agar saat kita mengambil turunan, kita tidak perlu mengambil 2 angka di depan turunan.

Setelah kita memiliki fungsi loss $J(\theta)$  kita harus mencari angka perubahan $\theta$ supaya nilai loss mengecil . 

Karena [[Linear Regression#__persamaan dasar Simple Linear Regression__|hipotesis persamaan linear regression]] adalah seperti ini:
$y = \beta_0 + \beta_1x$ atau $y = \theta_0 + \theta_1x$ atau bisa di singkat $h_\theta(x)$
maka kita perlu mencari turunan $\theta_0$ dan $\theta_1$. Dan sebab hipotesis persamaan linear inilah kita menggunakan turunan parsial.

Turunan dengan fungsi terhadap $\theta_0$ adalah
$$
\frac{\partial J}{\partial\theta_0} = \frac{1}{m} \sum_{i=1}^{m}(h_\theta(x_i) - y_i)
$$
Turunan dengan fungsi terhadap $\theta_1$ adalah
$$
\frac{\partial J}{\partial\theta_1} = \frac{1}{m} \sum_{i=1}^{m}(h_\theta(x_i) - y_i)x_i
$$

Note:
	>Mengapa kuadrat hilang yang padahal di rumus $J(\theta_0, \theta_1)$ ada?
	< Kuadrat tetap ada dalam loss function, tetapi ketika kita mengambil (memakai salah satu turunan terhadap..) maka kita menggunakan aturan turunan fungsi kuadrat:
	$$\frac{d}{dx}x^2 = 2x$$
	Maka dengan hal ini sama seperti:
	$$
	\frac{\partial}{\partial\theta_j}(h_\theta(x) - y)^2 = 2(h_\theta(x)-y) \cdot \frac{\partial}{\partial\theta_j} \cdot h_\theta(x_i)
	$$

__Contoh perhitungan :__

__Langkah 1:__
inisialisasi value, dengan perkiraan angka:

$\beta_0 = 0$
$\beta_1 = 0$
$\alpha = 0.1$

Lalu dengan di ketahui data berikut:

| $x$ | $y$  | $h_\theta(x)$ |
| --- | ---- | ------------- |
| 1   | 1.54 | $0+0(1) = 0$  |
| 2   | 2.48 | $0+0(2) = 0$  |
| 3   | 3.3  | $0+0(3) = 0$  |
Langkah 2
Menghitung fungsi terhadap $\theta_0$
$$
\theta_0 = \frac{1}{3} [(0 - 1.54) + (0-2.48) + (0-3.3)]
$$
$$
\theta_0 = \frac{1}{3}(-7.32) = \frac{-7.32}{3} = -2.44
$$
Langkah 3
Menghitung fungsi terhadap $\theta_1$
$$
\theta_1 = \frac{1}{3}[(0 - 1.54)(1) + (0-2.48)(2) + (0-3.3)(3)]
$$
$$
\theta_1 = \frac{1}{3}(-16.4) = \frac{-16.4}{3} = -5.46
$$
Langkah 4
1. Update parameter $\theta_0$:
   $$\theta_0 = 0 - (0.1 \times -2.44) = 0.244$$
2. Update parameter $\theta_1$
   $$ \theta_1 = 0 - (0.1 \times -5.46) = 0.546 $$
Langkah 5
Setelah mendapatkan angka $\theta_0$ dan $\theta_1$ kita dapat menggunakannya untuk iterasi berikutnya(jika di perlukan) sampai mendapatkan nilai parameter konvergen(stabil/sempurna).


Note:
Jika fitur dan target-terget memiliki rentan yang sangat jauh maka kita perlu menstandarisasi angkanya.

Mengapa perlu?
Untuk mencegah exploding gradients atau vanishing gradient terjadi, mengapa bisa terjadi?
Terjadi karena:
1. **Jika skala fitur X terlalu besar**, maka gradien (`theta1_gradient`) juga besar dan ini  menyebabkan parameter `theta` berubah drastis dan bisa menyebabkan `NaN` atau `Inf`.
   
2. **Jika skala fitur X terlalu kecil**, maka gradien sangat kecil maka pembaruan `theta` lambat, sehingga konvergensi butuh waktu lama atau bahkan berhenti terlalu cepat.