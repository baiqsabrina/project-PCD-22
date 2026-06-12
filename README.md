
## Klasifikasi Motif Batik Megamendung dan Parang Menggunakan Ekstraksi Fitur GLCM dengan Metode KNN dan SVM
Kelompok 22: 
1. Baiq Sabrina Ramadhani (F1D02410040)
2. Bunga Alma Azzahra M (F1D02410110)
3. Lalu Farras Hanif Aslam (F1D02410118)
4. Muhammad Asrodi Sazani (F1d02410123)

### Project Overview
Pada project PCD ini, kami melakukan eksperimen klasifikasi motif batik menggunakan pendekatan pengolahan citra digital. Motif batik yang diklasifikasikan adalah Megamendung dan Parang, yang memiliki karakteristik visual berbeda — Megamendung dengan pola awan berlapis dan kurva organik, sedangkan Parang dengan pola garis diagonal yang tegas dan berulang. Hal ini bertujuan untuk:
1. Menguji kemampuan dalam mengimplementasikan teknik pengolahan citra digital untuk melakukan klasifikasi citra motif batik.
2. Memilih tahapan preprocessing yang tepat sesuai dengan karakteristik visual motif batik.

Eksperimen dilakukan sebanyak 3 kali percobaan dengan penambahan preprocessing secara bertahap:
1. Percobaan Pertama : Preprocessing 1
2. Percobaan Kedua : Preprocessing 1 + Preprocessing 2
3. Percobaan Ketiga : Preprocessing 1 + Preprocessing 2 + Preprocessing 3
Dari setiap percobaan, akan dibandingkan akurasi masing-masing model: KNN dan SVM.

### Import Library
Pada tahap ini dilakukan import seluruh library yang dibutuhkan selama proses klasifikasi, mulai dari library pengolahan citra, ekstraksi fitur, hingga pembuatan model machine learning.

### Load Data
Dataset berisi citra motif batik yang dibagi ke dalam dua folder berdasarkan jenis motifnya (label). Pada tahap ini seluruh citra dibaca sekaligus beserta labelnya, kemudian diseragamkan ukurannya agar proses selanjutnya dapat berjalan konsisten.

Link Dataset: https://data.mendeley.com/datasets/5hp2dg7n3m/1

### Data Understanding
Setelah data dimuat, dilakukan eksplorasi untuk memahami karakteristik dataset, meliputi:
1. Jumlah total citra dan distribusi per kelas motif (Megamendung & Parang)
2. Kondisi visual citra (background, pencahayaan, noise, resolusi)
3. Sampel citra dari masing-masing kelas motif

Tahap ini penting untuk menentukan teknik preprocessing yang paling sesuai dengan kondisi data.

### Preprocessing
Pemilihan preprocessing didasarkan pada karakteristik visual citra batik yang memiliki pola tekstur kompleks dan variasi pencahayaan. Berikut preprocessing yang digunakan:

1. P1: Resize + Grayscale + Ekualisasi Histogram + Normalisasi
2. P2: Resize + Grayscale + Median Filter + Sharpening
3. P3: Resize + Grayscale + Morfologi Opening + Morfologi Closing

### Feature Extraction
Ekstraksi fitur dilakukan menggunakan metode Gray Level Co-occurrence Matrix (GLCM) dengan konfigurasi. Fitur yang diekstrak dari setiap citra meliputi, Contrast, Dissimilarity, Homogeneity, Energy, Correlation, ASM, dan Entropy