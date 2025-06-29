

# Catatan Pembelajaran Statistika Deskriptif dan Inferensial

## Konsep Dasar

### Statistika Deskriptif

- **Definisi**: Cabang statistika untuk menggambarkan atau merangkum data.
- **Teknik**:
  - Ukuran tendensi sentral: mean, median, modus.
  - Ukuran penyebaran: varians, standar deviasi.
  - Visualisasi data: histogram, diagram batang, scatter plot.
- **Tujuan**: Memberikan gambaran umum tentang dataset.

### Statistika Inferensial

- **Definisi**: Cabang statistika untuk membuat kesimpulan atau prediksi tentang populasi dari data sampel.
- **Teknik**:
  - Pengujian hipotesis (hypothesis testing).
  - Interval kepercayaan (confidence interval).
  - Analisis regresi.
  - Analisis varians (ANOVA).
- **Tujuan**: Generalisasi hasil sampel ke populasi.

### Perbedaan Utama

| Aspek  | Deskriptif           | Inferensial                                     |
| ------ | -------------------- | ----------------------------------------------- |
| Fokus  | Data aktual yang ada | Kesimpulan/prediksi                             |
| Teknik | Mean, median, grafik | Hipotesis, interval kepercayaan, regresi, ANOVA |
| Tujuan | Menggambarkan data   | Menggeneralisasi data                           |

## Hubungan dengan Jenis Data

### Data Kualitatif

- Deskriptif: Frekuensi, persentase, visualisasi (pie chart).
- Inferensial: Uji Chi-square untuk hubungan antar kategori.

### Data Kuantitatif

- Deskriptif: Mean, median, varians, standar deviasi.
- Inferensial: Uji hipotesis, regresi.

### Korelasi dalam Analisis Data

- **Contoh Data Kuantitatif (Gaji karyawan)**:
  - Deskriptif: Rata-rata gaji, standar deviasi, histogram.
  - Inferensial: Uji perbedaan gaji antar departemen, regresi terhadap pengalaman kerja.
- **Contoh Data Kualitatif (Golongan darah)**:
  - Deskriptif: Diagram pie.
  - Inferensial: Uji hubungan antara golongan darah dan penyakit tertentu dengan Chi-square.

## Skala Data

| Skala    | Contoh                   | Karakteristik                    |
| -------- | ------------------------ | -------------------------------- |
| Nominal  | Gender, warna favorit    | Tanpa urutan                     |
| Ordinal  | Pendidikan (SMA, S1, S2) | Berurutan, interval tidak sama   |
| Interval | Suhu (°C, °F)            | Interval sama, tanpa nol absolut |
| Rasio    | Berat badan, usia        | Interval sama, ada nol absolut   |



## Kuantil

Kuantil adalah nilai-nilai yang membagi data yang telah diurutkan menjadi beberapa bagian yang sama besar. Beberapa jenis kuantil yang sering digunakan adalah:

- **Kuartil**: Membagi data menjadi empat bagian sama besar. Kuartil ke-2 adalah median.
- **Desil**: Membagi data menjadi sepuluh bagian sama besar.
- **Persentil**: Membagi data menjadi seratus bagian sama besar.

###

```python


```

Output dari kode di atas adalah nilai tengah (median) dari kolom 'Pendapatan' dalam dataset tersebut. Untuk mencari kuartil 1 (Q1), kuartil 3 (Q3), atau persentil lainnya, kamu bisa mengganti nilai `q` menjadi 0.25, 0.75, 0.10, 0.90, dst.

## Ukuran Sebaran (Measures of Dispersion)

Ukuran sebaran (measure of dispersion) adalah statistika deskriptif yang digunakan untuk membantu kita memahami sebaran titik data di dalam sebuah sampel ataupun populasi.

Terdapat beberapa ukuran sebaran yang biasanya digunakan tergantung pada jenis atau tipe datanya, yaitu:

**Tipe Data Nominal dan Ordinal**
- Proporsi Kategori (Categorical Proportion)
- Persen Proporsi (Percent Proportion)
- Rasio Variasi (Variation Ratio)

### Proporsi Kategori

Proporsi kategori adalah ukuran sebaran yang paling sederhana dari ukuran sebaran pada data nominal dan ordinal. Secara matematis dapat dirumuskan sebagai:

\[
\text{Proporsi} = \frac{N_{\text{kategori ke-i}}}{N_{\text{total}}}
\]

Artinya, proporsi suatu kategori adalah jumlah data pada kategori tersebut dibagi dengan total seluruh data.

**Tipe Data Interval dan Rasio**
- Rentang (Range)
- Variansi (Variance)
- Deviasi Baku (Standard Deviation)

### Rentang (range)

Rentang adalah jarak antara nilai maksimum dengan nilai minimum. Semakin besar jarak antara nilai maksimum dan minimum semakin besar pula sebaran datanya. Secara matematis dapat dituliskan sebagai berikut:

\[
\text{Range} = \max(x) - \min(x)
\]

Dengan \(x\) adalah sampel atau populasi yang sedang diamati.

### Variansi

Variansi adalah ukuran sebaran pusat yang diperoleh dengan cara menghitung jarak antara tiap titik data pada sampel atau populasi dengan nilai mean. Secara matematis variansi dirumuskan sebagai berikut:

**Variansi Populasi**
\[
s^2 = \frac{\sum_{i=1}^{N}(X_i - \bar{X})^2}{N}
\]

**Variansi Sampel**
\[
s^2 = \frac{\sum_{i=1}^{N}(X_i - \bar{X})^2}{N-1}
\]

Dimana \(N\) merupakan jumlah data dan \(X_1, ..., X_N\) adalah titik data pada sampel atau populasi.

Perhatikan bahwa variansi populasi dan sampel berbeda pada penyebutnya (N vs N-1).

### Deviasi Baku (Standard Deviation)

Deviasi baku adalah ukuran sebaran pusat yang diperoleh dengan cara menarik akar kuadrat dari hasil perhitungan variansi. Hal ini dilakukan karena nilai variansi umumnya memiliki nilai yang lebih besar daripada nilai aslinya sebagai efek dari pengkuadratan data dan ini menjadikan variansi sulit untuk diinterpretasikan. Secara matematis deviasi baku dapat dirumuskan sebagai berikut:

**Deviasi Baku Populasi**
\[
s = \sqrt{\frac{\sum_{i=1}^{N}(X_i - \bar{X})^2}{N}}
\]

**Deviasi Baku Sampel**
\[
s = \sqrt{\frac{\sum_{i=1}^{N}(X_i - \bar{X})^2}{N-1}}
\]

Deviasi baku dapat dihitung menggunakan method `.std()` dari pandas maupun numpy. Perhatikan perbedaan default parameter `ddof` pada kedua library tersebut.

## Korelasi

Korelasi adalah salah satu metode statistika yang dapat digunakan untuk mengukur seberapa besar hubungan antara satu variabel dengan variabel lainnya. Sebagai contoh, misalnya mencari hubungan antara tinggi badan dengan berat badan, mencari hubungan antara gender dengan penghasilan dan masih banyak aplikasi penggunaan korelasi.

Terdapat beberapa metode yang dapat digunakan untuk menghitung korelasi antara sepasang variabel tergantung tipe dari sepasang variabel tersebut. Diantaranya adalah:

- Korelasi Pearson
- Korelasi Spearman
- Korelasi Kendall

### Korelasi Pearson

Korelasi Pearson atau sering juga disebut sebagai *Pearson's product moment correlation* adalah pengukuran korelasi parametrik yang menghasilkan koefisien korelasi. Koefisien korelasi ini dapat digunakan untuk mengukur kekuatan hubungan atau asosiasi linier antara dua variabel. Artinya jika hubungan kedua variabel tidak linier maka koefisien korelasi Pearson tidak dapat digunakan untuk mengukur kekuatan hubungan antara kedua variabel.

Selain itu nilai dari koefisien Pearson dapat digunakan untuk mengukur arah dari hubungan tersebut: **positif atau negatif**. Hubungan antar variabel dikatakan **positif jika nilai salah satu variabel naik maka nilai variabel lainnya juga naik**. Sebaliknya, hubungan antar variabel dikatakan **negatif jika nilai salah satu variabel naik maka nilai variabelnya turun**.

Contoh visualisasi hubungan korelasi:
- Perfect Positive Correlation (1)
- High Positive Correlation (0.9)
- Low Positive Correlation (0.5)
- No Correlation (0)
- Low Negative Correlation (-0.5)
- High Negative Correlation (-0.9)
- Perfect Negative Correlation (-1)

Sumber gambar: [https://www.mathsisfun.com/](https://www.mathsisfun.com/)

Beberapa asumsi yang harus dipenuhi untuk menggunakan korelasi Pearson diantaranya adalah:
1. Nilai berskala interval/rasio
2. Terdapat hubungan linier antara kedua variabel, yaitu dapat menggambarkan hubungan kedua variabel sebagai garis lurus.
3. Kedua variabel berdistribusi normal
4. Homoskedastis, atau data berdistribusi seragam di sepanjang garis regresi

Secara matematis, korelasi Pearson dapat dirumuskan sebagai berikut:

\[
r_{xy} = \frac{n \sum x_i y_i - \sum x_i \sum y_i}{\sqrt{n \sum x_i^2 - (\sum x_i)^2} \sqrt{n \sum y_i^2 - (\sum y_i)^2}}
\]

### Korelasi Spearman

Korelasi Spearman atau sering juga disebut sebagai *Spearman's rank correlation* adalah **pengukuran korelasi non-parametrik**. Artinya kita mencoba mengukur hubungan antara kedua variabel tanpa menghiraukan asumsi seperti distribusi dari kedua variabel dan asumsi lainnya. Secara kriteria memiliki kemiripan dengan korelasi Pearson walau korelasi Spearman bisa digunakan untuk data bertipe ordinal. Perbedaannya hanya terletak pada pengubahan data dalam bentuk ranking sebelum menghitung nilai korelasinya.

Secara matematis, korelasi Spearman dapat dihitung menggunakan rumus berikut:

\[
\rho = 1 - \frac{6 \sum d_i^2}{n(n^2 - 1)}
\]

Dimana:
- \(\rho\) adalah nilai korelasi Spearman
- \(d_i\) adalah nilai beda antara kedua variabel (setelah di-ranking)
- \(n\) adalah jumlah data

### Korelasi Kendall

Korelasi Kendall atau sering juga disebut sebagai *Kendall's rank correlation* atau korelasi Tau (\(\tau\)) adalah pengukuran korelasi non-parametrik.

Secara matematis, korelasi Kendall dapat dihitung menggunakan rumus berikut:

\[
\tau = \frac{n_c - n_d}{\frac{1}{2} n(n-1)}
\]

Dimana:
- \(n_c\) adalah jumlah pasangan konkordan
- \(n_d\) adalah jumlah pasangan diskordan
- \(n\) adalah jumlah data

### Interpretasi Nilai Korelasi dan Kaitannya dengan Kausalitas

Perhatikan nilai korelasi Pearson dari `raw_data` berikut:

```python
raw_data.corr()
```

Perhatikan bahwa beberapa pasang variabel memiliki nilai korelasi yang positif maupun negatif. Selain itu terdapat nilai yang sangat kecil hingga mendekati nol, namun ada juga yang cukup besar di atas 0.5, misalnya korelasi antara 'Jumlah' dan 'Pendapatan'. Besar kecilnya suatu nilai korelasi dari sepasang variabel menandakan seberapa kuat hubungan linier antara kedua variabel tersebut. Sebagai acuan untuk mengukur seberapa kuat korelasi sepasang variabel, kita dapat menggunakan ukuran berikut:

- \(0 < |r| < 0.49\): Hubungan lemah
- \(0.50 \leq |r| < 0.79\): Hubungan sedang
- \(0.80 \leq |r| < 1\): Hubungan kuat

Berdasarkan kriteria di atas, kita dapat menilai bahwa hubungan antara variabel 'Total' dan 'Jumlah' hubungannya sedang dan positif (\(r = 0.636097\)) sedangkan hubungan antara 'Pendapatan' dan 'Tingkat Kepuasan' hubungannya lemah dan negatif (\(r = -0.088339\)).

Namun, perlu diperhatikan bahwa walaupun kita dapat menilai kuat hubungan antara kedua variabel, kita tidak bisa menentukan arah dari hubungan tersebut. Sebagai contoh, walaupun antara variabel 'Total' dan 'Jumlah' memiliki hubungan yang sedang, tidak berarti kita bisa mengetahui apakah kenaikan nilai 'Total' berefek positif terhadap 'Jumlah' atau sebaliknya.

## Agregasi Data dengan method `.agg()`

Agregasi data adalah proses untuk menghitung beberapa ukuran statistik (seperti mean, median, min, max, dsb) secara bersamaan pada satu atau beberapa kolom dalam DataFrame. Pada pandas, method `.agg()` memungkinkan kita untuk melakukan agregasi ini dengan mudah, baik pada seluruh DataFrame maupun setelah melakukan groupby pada kolom tertentu. Dengan menggunakan `.agg()`, kita dapat memperoleh ringkasan statistik yang lebih komprehensif dalam satu langkah.

## Tools (Python)

### Mengimpor Library Pandas & Numpy

```python
import pandas as pd
import numpy as np
```

### Membuat DataFrame

```python
# Dari Dictionary
data_dict = {'Nama': ["Rama", "Octario", "Prawayan"], 'Kelas': [1, 2, 3]}
df_dict = pd.DataFrame(data_dict)

# Dari List of Lists
data_list = [["Rama", 1], ["Octario", 2], ["Prawayan", 3]]
kolom = ['Nama', 'Kelas']
df_list = pd.DataFrame(data_list, columns=kolom)
```

### Memuat DataFrame dari CSV

```python
file = pd.read_csv("data_mobil.csv", sep=",")
print(file.columns)
file = file.drop('No', axis=1)
file.head()

# Menampilkan nilai NaN tiap kolom
print(file.isna().sum())
```

### Mendeskripsikan DataFrame

```python
print(file.describe())
file.max()
file['Harga'].max()
file['Harga'].min()
```

### Menjumlahkan Kolom DataFrame

```python
file[['Harga']].sum()
file.sum(numeric_only=True)
```

### Menggunakan `.loc`

```python
print(file[:10])
print(file[3:5])
print(file.loc[[1, 3, 10]])
print(file[['Harga', 'Tahun']][1:10])
print(file[['Harga', 'Tahun']].loc[[1, 10, 15]])
```

### Menghitung Ukuran Pusat

```python
df = pd.read_csv("data_mobil.csv", sep=",")
df.head()
df['Harga'].mean()
df['Harga'].median()
df['Harga'].mode()
```

---

### Menghitung Proporsi Kategori pada Data

```python
import pandas as pd
# Membaca data dari dataset DQLab
raw_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/dataset_statistic.csv", sep=';')

# Cari proporsi tiap Produk
print(raw_data['Produk'].value_counts() / raw_data.shape[0])
```

Output contoh:
```
D    0.25
B    0.25
C    0.20
A    0.20
E    0.15
Name: Produk, dtype: float64
```

### Menghitung Rentang pada Data

```python
import pandas as pd
raw_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/dataset_statistic.csv", sep=';')

# Cari nilai rentang dari kolom 'Pendapatan'
print(raw_data['Pendapatan'].max() - raw_data['Pendapatan'].min())
```

Output contoh:
```
6850000
```

### Menghitung Variansi pada Data

```python
import numpy as np
import pandas as pd
raw_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/dataset_statistic.csv", sep=';')

# Menghitung variansi Pendapatan menggunakan method .var() dari pandas (default: sampel)
print(raw_data['Pendapatan'].var())

# Menghitung variansi Pendapatan menggunakan method .var() dari numpy (default: populasi)
print(np.var(raw_data['Pendapatan']))

# Mengatur variansi populasi dengan method .var() dari pandas
print(raw_data['Pendapatan'].var(ddof=0))
```

Output contoh:
```
1645684210526.3157
1563400000000.0
1563400000000.0
```

**Catatan:** Nilai variansi dari pandas dan numpy bisa berbeda karena default pandas adalah variansi sampel (penyebut N-1), sedangkan numpy default-nya variansi populasi (penyebut N). Untuk memperoleh hasil yang sama, gunakan parameter `ddof=0` pada pandas untuk variansi populasi.

### Menghitung Deviasi Baku pada Data

```python
import numpy as np
import pandas as pd
raw_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/dataset_statistic.csv", sep=';')

# Menghitung deviasi baku sampel menggunakan method std() dari pandas
print(raw_data['Pendapatan'].std())

# Menghitung deviasi baku sampel menggunakan method std() dari numpy
print(np.std(raw_data['Pendapatan'], ddof=1))
```

Output contoh:
```
1282842.2391478776
1282842.2391478776
```

**Catatan:** Nilai deviasi baku dari pandas dan numpy akan sama jika parameter `ddof` disamakan (default pandas: ddof=1, default numpy: ddof=0). Untuk deviasi baku sampel gunakan `ddof=1`.

### Menghitung Kuantil

```python
import numpy as np
import pandas as pd

# Membaca data dari dataset DQLab
data_url = "https://storage.googleapis.com/dqlab-dataset/dataset_statistic.csv"
raw_data = pd.read_csv(data_url, sep=';')

# Mencari median (50%) dari data menggunakan pandas
print(raw_data['Pendapatan'].quantile(q=0.5))

# Mencari median (50%) dari data menggunakan numpy
print(np.quantile(raw_data['Pendapatan'], q=0.5))

# Mencari kuartil 1 (Q1)
print(raw_data['Pendapatan'].quantile(q=0.25))

# Mencari kuartil 3 (Q3)
print(raw_data['Pendapatan'].quantile(q=0.75))

# Mencari persentil ke-90
print(raw_data['Pendapatan'].quantile(q=0.9))
```

Output dari kode di atas adalah nilai tengah (median) dari kolom 'Pendapatan' dalam dataset tersebut. Untuk mencari kuartil 1 (Q1), kuartil 3 (Q3), atau persentil lainnya, kamu bisa mengganti nilai `q` menjadi 0.25, 0.75, 0.10, 0.90, dst.

### Agregasi Data dengan method `.agg()`

```python
# menghitung rerata dan median Pendapatan dan Harga
raw_data[['Pendapatan', 'Harga']].agg([np.mean, np.median])
```

Output:
```
           Pendapatan    Harga
mean         1160000  197500.0
median        875000  200000.0
```

```python
# menghitung rerata dan median Pendapatan dan Harga dari tiap produk
raw_data[['Pendapatan', 'Harga', 'Produk']].groupby('Produk').agg([np.mean, np.median])
```

Output:
```
        Pendapatan             Harga            
               mean   median     mean   median
Produk                                      
A            850000  600000.0   100000  100000.0
B            950000  900000.0   200000  200000.0
C           1200000 1200000.0   250000  250000.0
D           1100000 1100000.0   300000  300000.0
E           1100000 1100000.0   300000  300000.0
```

### Menghitung Korelasi

Untuk menghitung korelasi antara dua variabel, kita dapat menggunakan method `.corr()` dari pandas sebagaimana contoh berikut:

```python
import pandas as pd
raw_data = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/dataset_statistic.csv", sep=';')

# menghitung korelasi dari setiap pasang variabel pada raw_data
print(raw_data.corr())

# mencari korelasi 'kendall' untuk tiap pasang variabel
print(raw_data.corr(method='kendall'))

# mencari korelasi 'spearman' untuk tiap pasang variabel
print(raw_data.corr(method='spearman'))
```

Perhatikan bahwa hanya variabel bertipe numerik saja yang dihitung nilai korelasinya. Selain itu secara default method `.corr()` memiliki parameter method bernilai `pearson` sehingga nilai korelasi di atas adalah korelasi Pearson. Untuk menggantinya menjadi korelasi Kendall atau korelasi Spearman kita cukup menambahkan parameter `method='kendall'` atau `method='spearman'` pada method `.corr()`.

Output contoh:

```
# Output korelasi Pearson
           ID Pelanggan  Jenis Kelamin  Pendapatan     Harga    Jumlah    Total  Tingkat Kepuasan
ID Pelanggan    1.000000      0.151375    0.110558 -0.028707  0.011289 -0.039968         -0.245717
Jenis Kelamin   0.151375      1.000000    0.192849  0.457555 -0.104160  0.238051          0.230051
Pendapatan     0.110558      0.192849    1.000000  0.322443  0.399825  0.592044         -0.312653
Harga         -0.028707      0.457555    0.322443  1.000000 -0.138883  0.645455         -0.380798
Jumlah         0.011289     -0.104160    0.399825 -0.138883  1.000000  0.638097          0.017568
Total         -0.039968      0.238051    0.592044  0.645455  0.638097  1.000000         -0.268345
Tingkat Kepuasan -0.245717      0.230051   -0.312653 -0.380798  0.017568 -0.268345          1.000000
```

```
# Output korelasi Kendall
           ID Pelanggan  Jenis Kelamin  Pendapatan     Harga    Jumlah    Total  Tingkat Kepuasan
ID Pelanggan    1.000000      0.126650   -0.064998  0.007573  0.024016 -0.065998          0.183817
Jenis Kelamin   0.126650      1.000000    0.190245  0.415339 -0.090295  0.190245         -0.085796
Pendapatan    -0.064998      0.190245    1.000000  0.520353  0.501925  0.988606         -0.165588
Harga          0.007573      0.415339    0.520353  1.000000 -0.098450  0.535078         -0.322659
Jumlah         0.024016     -0.090295    0.501925 -0.098450  1.000000  0.501925         -0.165588
Total         -0.065998      0.190245    0.988606  0.535078  0.501925  1.000000         -0.165588
Tingkat Kepuasan 0.183817     -0.085796   -0.165588 -0.322659 -0.165588 -0.165588          1.000000
```

```
# Output korelasi Spearman
           ID Pelanggan  Jenis Kelamin  Pendapatan     Harga    Jumlah    Total  Tingkat Kepuasan
ID Pelanggan    1.000000      0.151375   -0.063711 -0.039149  0.046356 -0.069779         -0.238890
Jenis Kelamin   0.151375      1.000000    0.219508  0.463635 -0.068864  0.219508         -0.090784
Pendapatan    -0.063711      0.219508    1.000000  0.640000  0.507110  0.998470         -0.192463
Harga         -0.039149      0.463635    0.640000  1.000000 -0.130749  0.646194         -0.378933
Jumlah         0.046356     -0.098864    0.607110 -0.130749  1.000000  0.607110         -0.023874
Total         -0.069779      0.219508    0.998470  0.646194  0.607110  1.000000         -0.192463
Tingkat Kepuasan -0.238890     -0.090784   -0.192463 -0.378933 -0.023874 -0.192463          1.000000
```



## Insight Pribadi

- Pemahaman tentang statistika deskriptif dan inferensial sangat penting dalam analisis data. Keduanya saling melengkapi: deskriptif sebagai dasar analisis dan inferensial untuk pengambilan keputusan.
- Pemilihan teknik statistika yang tepat bergantung pada jenis dan skala data yang digunakan. Memahami ini akan meningkatkan akurasi dan efektivitas analisis.
