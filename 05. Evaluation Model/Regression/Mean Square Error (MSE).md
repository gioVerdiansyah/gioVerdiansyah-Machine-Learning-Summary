Digunakan untuk mengukur model regresi seberapa jauh hasil prediksi model meleset dari nilai sebenarnya.

__Rumus:__
$$
MSE = \frac{1}{n} \sum_{i=1}^{n}\left( y_i - \hat{y}_i \right)^2
$$
$y_i$ adalah nilai aktual
$\hat{y_i}$ adalah nilai prediksi
$n$ adalah jumlah data
### __Contoh perhitungan__
$$
\text{Prediksi} = [4, 3, 7]
$$
$$
\text{Aktual} = [2, 4, 3]
$$
$$
[4, 3, 7] - [2, 4, 3] = [2, -1, 4]^2 = [4, 1, 16]
$$
$$
MSE = \frac{4 + 1 + 16}{3} = \frac{21}{3} = 7
$$

### **Penjelasan:**

- MSE menghitung rata-rata dari selisih kuadrat antara nilai aktual dan prediksi.
- Karena menggunakan kuadrat, MSE lebih sensitif terhadap outlier dibandingkan metrik seperti Mean Absolute Error (MAE).
- Nilai MSE yang lebih kecil menunjukkan bahwa model memiliki akurasi yang lebih baik.
### **Kelebihan MSE:**

+ Penalti lebih besar terhadap kesalahan besar karena dipangkatkan 2.  
+ Diferensialnya kontinu sehingga memudahkan optimasi dengan metode seperti Gradient Descent.
### **Kekurangan MSE:**

+ Peka terhadap outlier, karena perbedaan besar akan semakin diperbesar akibat pemangkatan.  
+ Nilainya tidak dalam satuan yang sama dengan data asli, karena berbentuk kuadrat.