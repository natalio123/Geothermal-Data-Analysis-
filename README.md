<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
</head>
<body>

<header>
   <h1 align="center">⛏️ Mithril Miner: Penambangan Data untuk Eksplorasi Lokasi Strategis PLTPs</h1>
<p align="center"><b>Pendekatan Penambangan Data dalam Mencapai Kedaulatan Energi</b></p>
<p align="center">Penerapan Machine Learning untuk Eksplorasi Potensi Lokasi Strategis Pembangkit Listrik Tenaga Pasang Surut (PLTPs) di Sulawesi Utara.</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?style=flat-square&logo=python"/>
<img src="https://img.shields.io/badge/Framework-XGBoost-orange?style=flat-square"/>
<img src="https://img.shields.io/badge/Library-GeoPandas-green?style=flat-square"/>
<img src="https://img.shields.io/badge/Competition-GEMASTIK_XVIII-red?style=flat-square"/>
</p>

---

## 🧩 Ringkasan Proyek

**CND Mithril Miner** merupakan proyek analisis data spasial yang berhasil menjadi **Delegasi dalam Babak Penyisihan Lomba Penambangan Data GEMASTIK XVIII Nasional 2025**. Proyek ini berfokus pada pengembangan sistem identifikasi lokasi strategis untuk Pembangkit Listrik Tenaga Pasang Surut (PLTPs) di Sulawesi Utara guna mendukung kedaulatan energi nasional.Dengan mengintegrasikan data oseanografi dan infrastruktur, sistem ini memberikan pemetaan potensi energi terbarukan yang akurat dan berbasis bukti.

---

## 🏗 Metodologi Teknis

Sistem ini mengikuti standar industri CRISP-DM (Cross-Industry Standard Process for Data Mining), mulai dari pemahaman bisnis hingga evaluasi model.

### 📊 Dataset yang Digunakan 
| Nama Data| Sumber| Variabel Kunci | Peran |
|----------|-------|----------------|-------|
| Kecepatan Arus|Copernicus Marine Service|utide, vtide| Prediktor Utama| 
|Batimetri|BIG (Batnas)|depth | Prediktor Kendala Teknis|
|Pasang Surut |BMKG|EST|Prediktor & Validasi|
|Jarak ke Grid|Olahan Manual (Grid)|Lat G, Long G |Prediktor Kendala Ekonomi|
---

## 👤 **Kontribusi Saya**

Fokus utama saya dalam proyek ini adalah memastikan integritas data dan mentransformasi variabel mentah menjadi fitur yang bermakna bagi model prediktif.

### 🔹 **1. Exploratory Data Analysis (EDA)**
- Analisis Kualitas Data: Mengidentifikasi dan menangani 1.223.109 missing values pada komponen arus dengan teknik imputasi nol (berdasarkan asumsi teknis ketiadaan arus pada titik tertentu).
- Pembersihan Data: Menghapus data duplikat pada dataset observasi Likupang untuk menjaga validitas statistik.
- Deteksi Outlier: Menganalisis nilai ekstrem pada rentang pasang surut menggunakan box plot. Berdasarkan verifikasi domain, data ekstrem tetap dipertahankan karena merupakan fenomena alami (pasang purnama).
- Karakterisasi Fenomena: Mengonfirmasi bahwa pola pasang surut di lokasi studi adalah tipe Mixed, Prevailing Semidiurnal.

### 🔹 **2. Data Preparation & Feature Engineering**
- Raster-to-Tabular Conversion: Mengekstraksi data spasial dari format .tif (Batimetri) dan .nc (Copernicus) ke dalam format tabular menggunakan rasterio dan xarray. 
- Vektor Magnitudo: Menghitung kecepatan arus total ($max\_tidal\_speed$) dari komponen vektor $u$ dan $v$.
- Spatial Merging: Melakukan integrasi data multidimensi menggunakan teknik Nearest Neighbor Join berbasis koordinat geografis (Latitude/Longitude).
- Target Labeling (Energy Score): Merancang variabel target kategorikal menggunakan sistem skor yang mengombinasikan potensi teknis (kecepatan arus) dan kendala ekonomi (jarak ke jaringan listrik).
  
---

## 🧠 Modeling & Evaluasi
Proyek ini membandingkan beberapa algoritma, di mana XGBoost terpilih sebagai model terbaik:

|Metric|Random Forest| XGBoost|
|------|-------------|--------|
|Accuracy|0.9696|0.9797|
|F1-Score|0.9697|0.9797|
|Kappa Score|0.9545|0.9696|

## 📂 Struktur Folder <br>
📦 Geothermal-Data-Analysis- <br>
 ┣ 📂 notebooks/ (EDA, Data Cleaning, & Modeling) <br>
 ┣ 📂 docs/ (Technical Report PDF) <br>
 ┣ 📂 dataset/ <br>
 ┣ 📂 assets/ (Visualisasi Peta & Grafik) <br>
 ┣ README.md <br>
 ┗ requirements.txt

## 👥 Tim CND Mithril Miner
- Christian Andreas Roeroe
- Natalio Michael Tumuahi
- David Evan Efraim Haniko

Dosen Pembimbing: Daniel Febrian Sengkey, S.T., M.Eng <br>
Universitas Sam Ratulangi - Teknik Informatika

## 📬 Kontak
Jika ingin berdiskusi atau merekrut saya, hubungi:
nataliotumuahi@gmail.com

</body>
</html>
