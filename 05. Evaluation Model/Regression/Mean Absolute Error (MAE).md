Evaluasi model regresi untuk menghitung rata-rata kesalahan absolut dari nilai prediksi dan aktual.

__Rumus:__
$$
MAE = \frac{1}{n} \sum^{n}_{i=1}|y_i - \hat{y}_i|
$$
$y_i$ adalah nilai aktual
$\hat{y_i}$ adalah nilai prediksi
$n$ adalah jumlah data

### __Contoh Perhitungan__
$$\text{Prediksi} = [4, 3, 7]$$
$$\text{Aktual} = [2, 4, 3]$$
$$|4 - 2| = 2 |3 - 4| = 1 |7 - 3| = 4$$
$$MAE = \frac{2+1+4}{3} = \frac{7}{3} \approx 2.33$$
### **Penjelasan:**

- MAE menghitung rata-rata dari selisih absolut antara nilai aktual dan prediksi tanpa memperhitungkan arah kesalahan (positif atau negatif).
- Metrik ini memberikan gambaran langsung tentang seberapa besar rata-rata kesalahan yang dibuat oleh model.
- Semakin kecil nilai MAE, semakin baik performa model.

### **Kelebihan MAE:**

+ Mudah diinterpretasikan karena memiliki satuan yang sama dengan data asli.  
+ Tidak terlalu peka terhadap outlier dibandingkan MSE karena tidak menggunakan pemangkatan kuadrat.

### **Kekurangan MAE:**

+ Tidak memberi penalti lebih besar pada kesalahan besar seperti MSE.  
+ Sulit untuk digunakan dalam optimasi karena tidak memiliki turunan yang kontinu di titik nol.