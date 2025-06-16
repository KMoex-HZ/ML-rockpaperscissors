# Proyek Klasifikasi Gambar Rock-Paper-Scissors

Proyek ini adalah submission untuk kelas "Belajar Machine Learning untuk Pemula" di Dicoding. Tujuannya adalah untuk membuat model _machine learning_ yang dapat mengklasifikasikan gambar tangan yang membentuk simbol gunting, batu, atau kertas.

<p align="center">
  <img src="https://github.com/KMoex-HZ/ML-rockpaperscissors/blob/main/Screenshot%202025-06-16%20190301.png" alt="Demo" width="400">
</p>

## Deskripsi Proyek

Model ini dibangun menggunakan _Convolutional Neural Network_ (CNN) dengan TensorFlow dan Keras. Dataset yang digunakan adalah [rockpaperscissors](https://github.com/dicodingacademy/assets/releases/download/release/rockpaperscissors.zip) yang disediakan oleh Dicoding. Proyek ini mencakup langkah-langkah mulai dari _data loading_, _preprocessing_ dengan augmentasi gambar, pembangunan model, pelatihan, hingga pengujian model dengan gambar baru.

**Hasil:**
* **Status:** Diterima
* **Akurasi Model:** Mencapai akurasi di atas 96% pada data validasi.

## Detail Teknis

### 1. Persiapan Data
* **Dataset:** Gambar gunting, batu, dan kertas.
* **Pembagian Data:** Dataset dibagi menjadi data latih (60%) dan data validasi (40%).
* **Augmentasi Gambar:** Untuk data latih, dilakukan augmentasi gambar menggunakan `ImageDataGenerator` dari Keras. Proses ini mencakup rotasi, _horizontal flip_, dan _shear transformation_ untuk meningkatkan variasi data dan mencegah _overfitting_.

### 2. Pembangunan Model
Model CNN yang digunakan memiliki arsitektur sebagai berikut:
1.  **Convolutional Layer 1:** 32 filter dengan kernel (3,3) dan aktivasi ReLU.
2.  **Max Pooling Layer 1:** Ukuran pool (2,2).
3.  **Convolutional Layer 2:** 64 filter dengan kernel (3,3) dan aktivasi ReLU.
4.  **Max Pooling Layer 2:** Ukuran pool (2,2).
5.  **Convolutional Layer 3:** 128 filter dengan kernel (3,3) dan aktivasi ReLU.
6.  **Max Pooling Layer 3:** Ukuran pool (2,2).
7.  **Flatten Layer:** Mengubah data menjadi satu dimensi.
8.  **Dropout Layer:** Dengan rate 0.2 untuk mengurangi _overfitting_.
9.  **Dense Layer:** 512 neuron dengan aktivasi ReLU.
10. **Output Layer:** 3 neuron (untuk 3 kelas) dengan aktivasi Softmax.

### 3. Pelatihan Model
* **Optimizer:** Adam.
* **Loss Function:** `categorical_crossentropy`, karena ini adalah masalah klasifikasi multikelas.
* **Metrik:** Akurasi.
* **Epochs:** Model dilatih selama 20 epoch.

### 4. Hasil dan Evaluasi
Model berhasil mencapai akurasi **di atas 96%** pada data validasi, yang memenuhi kriteria kelulusan proyek.

## Cara Menjalankan
1.  Pastikan Python dan TensorFlow sudah terpasang.
2.  Clone repositori ini.
3.  Jalankan file `RockPaperScissors.ipynb` menggunakan Jupyter Notebook atau Google Colab.
4.  Pastikan dataset `rockpaperscissors.zip` diunduh dan diekstrak sesuai dengan path yang ada di dalam notebook.

![rating-default-4](https://github.com/Wynterwine/ML-Rock-Paper-Scissors/assets/125936700/682446b3-0f5a-4589-a6ae-0a6317d5c3d1)
- Dataset yang dipakai haruslah dataset berikut : rockpaperscissors, atau gunakan link ini pada wget command: https://github.com/dicodingacademy/assets/releases/download/release/rockpaperscissors.zip.
- Dataset harus dibagi menjadi train set dan validation set.
- Ukuran validation set harus 40% dari total dataset (data training memiliki 1314 sampel, dan data validasi sebanyak 874 sampel).
- Harus mengimplementasikan augmentasi gambar.
- Menggunakan image data generator.
- Model harus menggunakan model sequential.
- Pelatihan model tidak melebihi waktu 30 menit.
- Program dikerjakan pada Google Colaboratory.
- Akurasi dari model minimal 85%.

![Screenshot 2024-06-27 223841](https://github.com/Wynterwine/ML-Rock-Paper-Scissors/assets/125936700/1f043679-6669-43c9-9247-3d073791660f)
