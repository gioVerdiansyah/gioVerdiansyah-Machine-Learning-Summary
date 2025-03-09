## Cek distribusi data
Jika datasets terkait sentimen atau kategori maka kita bisa kita cek dengan `.value_counts()` 
atau bisa di visualisasikan dengan [[Numerical Visualization#Pieplot|pieplot.]]

## Mengecek karakter non-alfabetik / simbol
Kita bisa menemukannya dengan menggunakan regex(regular expression) untuk melihat karakter non-alfabetik / simbol yang ada dalam datasets teks. Contoh kode
`df['<nama_col>'].apply(lambda x: re.findall(r'[^a-zA-Z0-9 ]', str(x)))`

## Menampilkan kata yang sering muncul

+ **Analisis N-grams (Bigram/Trigram)**
	- Untuk melihat kombinasi kata yang sering muncul.
	- Bisa digunakan `NLTK` atau `sklearn.feature_extraction.text.CountVectorizer`.

+ Word Cloud
	+ Menggunakan pustaka `wordcloud` untuk melihat kata yang sering muncul
	  Contoh gambar:![[Pasted image 20250308212913.png]]