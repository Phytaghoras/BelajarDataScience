

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

## Agregasi Data dengan method `.agg()`

Ada kalanya kita ingin menghitung sekaligus beberapa ukuran, misalnya menghitung nilai mean sekaligus menghitung nilai median. Kita dapat melakukan kedua hal tersebut dengan menggunakan method `.agg()` pada objek pandas DataFrame sebagaimana contoh berikut:

```python
# menghitung rerata dan median usia (agg) dan insulin (insu)
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

## Insight Pribadi

- Pemahaman tentang statistika deskriptif dan inferensial sangat penting dalam analisis data. Keduanya saling melengkapi: deskriptif sebagai dasar analisis dan inferensial untuk pengambilan keputusan.
- Pemilihan teknik statistika yang tepat bergantung pada jenis dan skala data yang digunakan. Memahami ini akan meningkatkan akurasi dan efektivitas analisis.
