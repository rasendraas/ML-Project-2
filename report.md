# Laporan Proyek Machine Learning  
## Air Quality & Pollution Assessment Quality Prediction  
**Rasendra Akbar Satyatama** — *MC004D5Y1124*

---
## Daftar Isi

- [Domain Proyek](#domain-proyek-lingkungan-dan-kesehatan-masyarakat)
  - [Referensi](#referensi)
- [Business Understanding](#business-understanding)
  - [Problem Statements](#problem-statements)
  - [Goals](#goals)
  - [Solution Statements](#solution-statements)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
  - [Deskripsi Variabel](#deskripsi-variabel)
---
## **Domain Proyek: Lingkungan dan Kesehatan Masyarakat**

Kualitas udara merupakan aspek krusial dalam isu lingkungan dan kesehatan masyarakat. Menurut World Health Organization (WHO), polusi udara menyebabkan sekitar **7 juta kematian dini setiap tahun** di seluruh dunia karena paparan terhadap partikel halus dan gas beracun seperti PM2.5, NO₂, dan SO₂ \[1]. Wilayah dengan tingkat kepadatan penduduk tinggi atau dekat dengan kawasan industri cenderung memiliki tingkat polusi udara yang lebih tinggi, sehingga berdampak signifikan terhadap risiko penyakit pernapasan, kardiovaskular, dan berbagai gangguan kesehatan lainnya.

Dengan semakin pesatnya urbanisasi dan pertumbuhan industri, penting bagi pemerintah, organisasi lingkungan, dan masyarakat umum untuk memiliki sistem pemantauan dan prediksi kualitas udara yang dapat digunakan sebagai dasar pengambilan keputusan. Pendekatan konvensional dalam pemantauan kualitas udara, seperti penggunaan sensor stasioner, memiliki keterbatasan cakupan geografis dan biaya operasional yang tinggi. Oleh karena itu, pendekatan berbasis data dan machine learning dapat menjadi solusi yang efisien dan fleksibel dalam memperkirakan kondisi kualitas udara berdasarkan faktor lingkungan dan demografis.

Proyek ini berada dalam domain **lingkungan hidup dan kesehatan publik**, dengan fokus pada pengembangan model prediksi berbasis data untuk memetakan tingkat kualitas udara suatu wilayah secara otomatis. Dengan prediksi yang akurat, pemerintah dapat mengidentifikasi daerah risiko tinggi, mengatur kebijakan emisi, atau menyampaikan peringatan dini kepada masyarakat.

---

### Referensi:

\[1] World Health Organization (2021). *Air pollution*. Retrieved from [https://www.who.int/news-room/fact-sheets/detail/ambient-(outdoor)-air-quality-and-health](https://www.who.int/news-room/fact-sheets/detail/ambient-%28outdoor%29-air-quality-and-health)

---

## Business Understanding

### Problem Statements

Dalam konteks urbanisasi dan industrialisasi yang pesat, kualitas udara menjadi perhatian utama karena dampaknya terhadap kesehatan masyarakat. Organisasi lingkungan hidup, pemerintah daerah, serta badan perencana kota membutuhkan alat prediksi yang andal untuk memperkirakan kualitas udara secara proaktif. Berdasarkan hal tersebut, berikut adalah pernyataan masalah yang diangkat:

1. **Pernyataan Masalah 1:**  
   Bagaimana mengidentifikasi fitur lingkungan dan demografis yang paling berpengaruh terhadap tingkat kualitas udara di suatu wilayah?

2. **Pernyataan Masalah 2:**  
   Bagaimana membangun model prediksi yang dapat mengklasifikasikan tingkat kualitas udara (*Good, Moderate, Poor, Hazardous*) secara akurat berdasarkan data lingkungan dan kependudukan?

3. **Pernyataan Masalah 3:**  
   Bagaimana menentukan model yang dibangun mampu melakukan prediksi dengan performa optimal dan konsisten pada data baru?

---

### Goals

Untuk menjawab pernyataan masalah di atas, tujuan proyek ini dirumuskan sebagai berikut:

1. **Tujuan 1:**  
   Melakukan eksplorasi data dan analisis korelasi untuk mengetahui fitur mana yang paling signifikan terhadap kualitas udara, seperti konsentrasi PM2.5, NO₂, kepadatan penduduk, atau jarak ke kawasan industri.

2. **Tujuan 2:**  
   Membangun model machine learning klasifikasi multikelas yang dapat memprediksi kategori kualitas udara secara otomatis berdasarkan fitur numerik dan kategorikal.

3. **Tujuan 3:**  
   Melakukan evaluasi terhadap semua model yang digunakan untuk mengetahui prediksi dengan akurasi dan generalisasi terbaik.

---

### Solution Statements

Untuk mencapai tujuan-tujuan tersebut, solusi yang akan diimplementasikan meliputi:

1. **Eksperimen Beberapa Algoritma Klasifikasi:**  
   Membangun dan membandingkan performa dari beberapa algoritma klasifikasi seperti:
   - K-Nearest Neighbors (KNN)
   - Random Forest
   - XGBoost

2. **Evaluasi Berdasarkan Metrik yang Terukur:**  
   Menggunakan metrik evaluasi seperti:
   - **Accuracy** untuk mengukur kebenaran prediksi secara keseluruhan.
   - **Precision, Recall, dan F1-Score** untuk menilai performa tiap kelas.
   - **Confusion Matrix** untuk melihat distribusi kesalahan klasifikasi.

3. **Visualisasi Hasil Fitur Penting:**  
   Menggunakan *feature importance plot* untuk menjelaskan fitur mana yang paling berkontribusi terhadap prediksi model.

---

## Exploratory Data Analysis (EDA)

### Deskripsi Variabel
| Nama Variabel                   | Tipe Data | Deskripsi                                                                 |
|---------------------------------|-----------|---------------------------------------------------------------------------|
| `Temperature`                   | float64   | Suhu udara lingkungan (dalam satuan derajat Celcius).                     |
| `Humidity`                      | float64   | Kelembapan udara relatif (dalam persentase).                              |
| `PM2.5`                         | float64   | Konsentrasi partikel halus dengan diameter ≤2.5µm (mikrogram/m³).         |
| `PM10`                          | float64   | Konsentrasi partikel kasar dengan diameter ≤10µm (mikrogram/m³).          |
| `NO2`                           | float64   | Konsentrasi gas nitrogen dioksida (NO₂) di udara (mikrogram/m³).          |
| `SO2`                           | float64   | Konsentrasi gas sulfur dioksida (SO₂) di udara (mikrogram/m³).            |
| `CO`                            | float64   | Konsentrasi gas karbon monoksida (CO) di udara (ppm).                     |
| `Proximity_to_Industrial_Areas`| float64   | Jarak ke area industri terdekat (dalam kilometer).                        |
| `Population_Density`           | int64     | Kepadatan penduduk di wilayah tersebut (jumlah penduduk per km²).        |
| `Air Quality`                   | object    | Label kualitas udara (kategori: Good, Moderate, Poor, Hazardous).        |

Dataset yang digunakan berisi **5000 observasi** dengan **9 fitur prediktor** numerik dan **1 fitur target** yaitu *Air Quality*. Secara umum, fitur-fitur seperti **Temperature**, **Humidity**, **PM2.5**, **PM10**, **NO2**, **SO2**, **CO**, **Proximity to Industrial Areas**, dan **Population Density** direpresentasikan dalam tipe data numerik, dengan sebaran nilai yang cukup bervariasi. Misalnya, konsentrasi **PM2.5** memiliki nilai maksimum hingga **295 µg/m³**, sedangkan variabel **SO2** bahkan menunjukkan adanya nilai negatif pada data mentah, yang mengindikasikan potensi outlier atau kesalahan pengukuran. Rata-rata kepadatan penduduk berada di angka **497 orang/km²**, dengan jarak rata-rata ke kawasan industri sekitar **8.43 km**.

| Fitur                                  | Mean   | Std Dev | Min   | 25%   | Median | 75%   | Max   |
| -------------------------------------- | ------ | ------- | ----- | ----- | ------ | ----- | ----- |
| **Temperature (°C)**                   | 30.03  | 6.72    | 13.4  | 25.1  | 29.0   | 34.0  | 58.6  |
| **Humidity (%)**                       | 70.06  | 15.86   | 36.0  | 58.3  | 69.8   | 80.3  | 128.1 |
| **PM2.5 (µg/m³)**                      | 20.14  | 24.55   | 0.0   | 4.6   | 12.0   | 26.1  | 295.0 |
| **PM10 (µg/m³)**                       | 30.22  | 27.35   | -0.2  | 12.3  | 21.7   | 38.1  | 315.8 |
| **NO2 (ppb)**                          | 26.41  | 8.90    | 7.4   | 20.1  | 25.3   | 31.9  | 64.9  |
| **SO2 (ppb)**                          | 10.01  | 6.75    | -6.2  | 5.1   | 8.0    | 13.73 | 44.9  |
| **CO (ppm)**                           | 1.50   | 0.55    | 0.65  | 1.03  | 1.41   | 1.84  | 3.72  |
| **Proximity to Industrial Areas (km)** | 8.43   | 3.61    | 2.5   | 5.4   | 7.9    | 11.1  | 25.8  |
| **Population Density (people/km²)**    | 497.42 | 152.75  | 188.0 | 381.0 | 494.0  | 600.0 | 957.0 |

### Rata-rata Fitur per Kategori Air Quality

| Air Quality   | Temperature | Humidity | PM2.5 | PM10  | NO2   | SO2   | CO   | Proximity to Industry | Population Density |
| ------------- | ----------- | -------- | ----- | ----- | ----- | ----- | ---- | --------------------- | ------------------ |
| **Good**      | 24.95       | 60.02    | 9.91  | 14.99 | 19.45 | 5.04  | 1.00 | 11.99                 | 398.94             |
| **Hazardous** | 40.35       | 89.47    | 41.92 | 61.51 | 40.60 | 20.02 | 2.49 | 4.59                  | 696.01             |
| **Moderate**  | 30.14       | 70.21    | 20.46 | 30.60 | 26.44 | 9.98  | 1.51 | 6.96                  | 497.57             |
| **Poor**      | 34.87       | 80.18    | 29.24 | 44.45 | 33.21 | 15.03 | 2.00 | 5.42                  | 594.88             |


Berdasarkan statistik deskriptif per kategori *Air Quality*, terlihat pola yang konsisten antara kenaikan polutan dan penurunan kualitas udara. Kategori **Hazardous** memiliki rata-rata tertinggi pada semua indikator polusi seperti **PM2.5 (41.92 µg/m³)**, **PM10 (61.51 µg/m³)**, **NO2 (40.60 ppb)**, **SO2 (20.02 ppb)**, dan **CO (2.49 ppm)**. Sebaliknya, kategori **Good** menunjukkan nilai terendah untuk semua polutan tersebut, sekaligus memiliki jarak terjauh ke kawasan industri (**11.99 km**) dan densitas penduduk yang relatif rendah (**398.94 orang/km²**).

Selain faktor polusi, variabel **Temperature** dan **Humidity** juga menunjukkan kecenderungan yang sejalan dengan penurunan kualitas udara. Lokasi dengan kualitas udara buruk cenderung memiliki suhu dan kelembapan lebih tinggi. Hal ini memperkuat dugaan bahwa faktor lingkungan dan aktivitas manusia, seperti industrialisasi dan kepadatan penduduk, berkontribusi signifikan terhadap degradasi kualitas udara di wilayah tertentu.

---

### Menangani Missing Value dan Outliers

Dalam tahap awal pembersihan data, dilakukan pengecekan terhadap **duplikasi data** dan **missing value**. Hasilnya menunjukkan bahwa **tidak terdapat duplikasi data** maupun **missing value** di seluruh kolom fitur maupun target. Hal ini mengindikasikan bahwa dataset sudah lengkap dan tidak memerlukan teknik imputasi lebih lanjut.

| Kolom                         | Jumlah Missing Value |
| ----------------------------- | -------------------- |
| Temperature                   | 0                    |
| Humidity                      | 0                    |
| PM2.5                         | 0                    |
| PM10                          | 0                    |
| NO2                           | 0                    |
| SO2                           | 0                    |
| CO                            | 0                    |
| Proximity to Industrial Areas | 0                    |
| Population Density            | 0                    |
| Air Quality                   | 0                    |

Selanjutnya, dilakukan deteksi **outlier** menggunakan metode **Interquartile Range (IQR)** untuk setiap fitur numerik. Hasil analisis menunjukkan bahwa beberapa variabel memiliki jumlah outlier yang cukup signifikan, terutama pada **PM2.5 (352 outlier)** dan **PM10 (324 outlier)**. Variabel lain seperti **SO2 (124 outlier)**, **NO2 (73 outlier)**, dan **Temperature (72 outlier)** juga menunjukkan keberadaan data pencilan dalam jumlah yang cukup banyak. Bahkan fitur-fitur lain seperti **CO**, **Proximity to Industrial Areas**, dan **Population Density** juga mengandung outlier meskipun dalam jumlah yang lebih sedikit.

| Fitur                         | Jumlah Outlier |
| ----------------------------- | -------------- |
| Temperature                   | 72             |
| Humidity                      | 19             |
| PM2.5                         | 352            |
| PM10                          | 324            |
| NO2                           | 73             |
| SO2                           | 124            |
| CO                            | 45             |
| Proximity to Industrial Areas | 16             |
| Population Density            | 7              |

![alt text](image.png)
Visualisasi melalui **boxplot** semakin memperjelas sebaran data dan keberadaan outlier di setiap fitur. Polutan udara seperti **PM2.5**, **PM10**, dan **SO2** tampak memiliki sebaran yang lebar dengan banyak data berada di luar whisker (batas IQR), yang mengindikasikan variasi nilai ekstrim dalam data tersebut.

Meskipun demikian, outlier **tidak dihapus** dari dataset. Hal ini dilakukan untuk menjaga **keutuhan informasi**, mengingat data pencilan tersebut mencerminkan kondisi nyata seperti lonjakan polusi di area industri atau wilayah dengan kepadatan penduduk tinggi. Menghilangkan outlier justru berisiko menghilangkan pola penting dalam konteks analisis kualitas udara.

Sebagai langkah mitigasi terhadap pengaruh outlier, proses **scaling** akan dilakukan menggunakan teknik **Robust Scaler**. Metode ini dipilih karena lebih tahan terhadap pengaruh outlier dibandingkan teknik standardisasi konvensional (seperti Min-Max atau Standard Scaler), sehingga mampu menyesuaikan skala data dengan lebih representatif tanpa terdistorsi oleh nilai ekstrim.

---

