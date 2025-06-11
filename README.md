# Klasifikasi Gambar Hewan (Sapi, Domba, Tupai)

Proyek ini adalah implementasi dari model klasifikasi gambar menggunakan Convolutional Neural Network (CNN) dengan teknik **Transfer Learning**. Model ini dilatih untuk dapat membedakan tiga kelas hewan: sapi (`mucca`), domba (`pecora`), dan tupai (`scoiattolo`).

### 1. Deskripsi Proyek
Tujuan utama proyek ini adalah membangun model deep learning yang efisien untuk mengklasifikasikan gambar hewan ke dalam tiga kategori yang telah ditentukan. Proyek ini mencakup seluruh siklus machine learning, mulai dari persiapan data, augmentasi, pelatihan model, evaluasi, hingga penyimpanan model dalam berbagai format untuk deployment (`SavedModel`, `TFLite`, `TensorFlow.js`).

### 2. Dataset
- **Nama**: Animals-10
- **Sumber**: [Kaggle - Animals-10 Dataset](https://www.kaggle.com/datasets/alessiocorrado99/animals10)
- **Kelas yang Digunakan**: `mucca` (sapi), `pecora` (domba), `scoiattolo` (tupai)
- **Pembagian Data**: Dataset dibagi menjadi tiga bagian dengan rasio:
    - **Data Latih (Train)**: 70%
    - **Data Validasi (Validation)**: 15%
    - **Data Uji (Test)**: 15%

### 3. Alur Kerja Proyek
1.  **Persiapan Data**: Memilih dan menyalin 3 kelas hewan dari dataset asli.
2.  **Pemisahan Data**: Membuat struktur direktori `train`, `validation`, dan `test` secara manual.
3.  **Preprocessing & Augmentasi**: Menggunakan `ImageDataGenerator` untuk:
    - Menormalisasi nilai piksel gambar ke rentang [0, 1].
    - Melakukan augmentasi data pada set pelatihan (rotasi, zoom, flip, dll.) untuk meningkatkan ketahanan model.
    - Mengubah ukuran semua gambar menjadi **150x150** piksel.
4.  **Pelatihan Model**: Melatih model dengan callback `EarlyStopping` untuk mencegah overfitting dan menghentikan pelatihan pada waktu yang optimal.
5.  **Evaluasi**: Mengevaluasi performa model menggunakan plot akurasi/loss dan metrik pada data uji.
6.  **Penyimpanan Model**: Menyimpan model terlatih ke dalam tiga format berbeda.

### 4. Arsitektur Model
Model ini dibangun menggunakan **Keras Functional API** dengan pendekatan Transfer Learning.
* **Model Dasar (Base Model)**: Menggunakan **InceptionV3** yang telah dilatih pada dataset ImageNet. Bobot dari model dasar ini dibekukan (`trainable=False`) untuk memanfaatkan fitur-fitur yang sudah dipelajarinya.
* **Kepala Model (Custom Head)**: Di atas model dasar, ditambahkan beberapa lapisan kustom untuk disesuaikan dengan tugas klasifikasi 3 kelas ini. dengan Conv2D Dan MaxPooling

### 5. Hasil
Model berhasil dilatih dan dievaluasi dengan hasil yang memuaskan.
* **Akurasi pada Data Uji**: **93.76%**

#### Plot Performa Model

Grafik menunjukkan bahwa akurasi pelatihan dan validasi meningkat secara bersamaan, sementara loss menurun. Ini menandakan model belajar dengan baik tanpa mengalami overfitting yang signifikan.
# clasifikasi_animal
