Metrik evaluasi dalam regresi yang mengukur seberapa baik model dapat menjelaskan variabilitas data aktual. Nilai $R^2$ berkisar antara **0 hingga 1**.

__Rumus:__
$$
R^2 = 1 - \frac{\sum_{i}(y - \hat{y})^2}{\sum_{i}(y - \bar{y})^2}
$$
$y_i$ adalah nilai aktual
$\hat{y_i}$ adalah nilai prediksi
$\bar{y_i}$ adalah nilai rata-rata aktual
$n$ adalah jumlah data
$\sum_{i}(y - \hat{y})^2$ **Residual Sum of Squares (RSS)**  jumlah kuadrat error antara nilai aktual dan prediksi
$\sum_{i}(y - \bar{y})^2$ **Total Sum of Squares (TSS)** jumlah kuadrat selisih nilai aktual terhadap rata-rata

Contoh perhitungan:
$$Prediksi = [4, 3, 7]$$
$$Aktual: [2, 1, 4]$$
$$RSS = [4, 3, 7] - [2, 4, 3] = [2, -1, 4]^2 = [4, 1, 16]$$
$$TSS = [2, 1, 4] - 2.33 = [-0.33, -1.33, 1.67]^2 = [0.1089,1.7689,2.7889]$$
$$\frac{4 + 1 + 16}{0.1089 + 1.7689 + 2.7889} = \frac{21}{4.6667} = 4.5$$
$$R^2 = 1 - 4.5 = -3.5$$

### **Penjelasan:**

- **$R^2$ mengukur seberapa baik model menjelaskan variabilitas data dibandingkan hanya menggunakan rata-rata data.**
- Jika **$R^2$ mendekati 1**, model sangat baik dalam menjelaskan data.
- Jika **$R^2$ mendekati 0**, model tidak lebih baik daripada hanya menggunakan rata-rata sebagai prediksi.
- Jika **$R^2$ negatif**, model lebih buruk daripada sekadar memprediksi rata-rata.

### **Kelebihan R2R^2R2:**

+ **Mudah diinterpretasikan**, karena menunjukkan persentase variabilitas yang bisa dijelaskan oleh model.  
+ **Membantu membandingkan model regresi**, semakin tinggi $R^2$, semakin baik model menjelaskan data.

### **Kekurangan R2R^2R2:**

+ **Tidak selalu mencerminkan model yang baik**, karena bisa meningkat hanya dengan menambahkan lebih banyak variabel, bahkan jika variabel tersebut tidak relevan.  
+ **Tidak mempertimbangkan kompleksitas model**, sehingga lebih baik menggunakan **Adjusted $R^2$** jika membandingkan model dengan jumlah fitur yang berbeda.
