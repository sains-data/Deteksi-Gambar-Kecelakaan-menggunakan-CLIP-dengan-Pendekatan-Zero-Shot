# Deteksi-Gambar-Kecelakaan-menggunakan-CLIP-dengan-Pendekatan-Zero-Shot
## Anggota Kelompok 26:
1. 121450109 - Della Septiani  
2. 121450031 - Hartiti Fadilah  
3. 121450061 - Josua Alfa Viando Panggabean  
4. 121450093 - Anissa Luthfi Alifia  
5. 121450094 - Syifa Firnanda  
6. 121450030 - Pramudya Wibowo

## Introduction
Deteksi gambar kecelakaan merupakan langkah penting untuk mendukung sistem respons cepat dalam situasi darurat. Penelitian ini menggunakan dataset dari Kaggle, berjudul **Accident Detection From CCTV Footage** oleh Charan Kumar, yang berisi rekaman CCTV untuk mendeteksi kecelakaan lalu lintas melalui analisis gambar. Dataset tersebut awalnya terdiri dari tiga folder: latih, uji, dan validasi, dengan dua kelas, yaitu **Accident** dan **Non-Accident**. Penelitian ini hanya menggunakan satu folder dataset tanpa pembagian data (split), terdiri dari 350 gambar untuk kelas **Accident** dan 350 gambar untuk kelas **Non-Accident**.

Model yang digunakan adalah **Contrastive Language–Image Pre-training (CLIP)** dengan pendekatan **zero-shot**, sehingga tidak memerlukan pelatihan ulang pada dataset spesifik. CLIP bekerja dengan menggabungkan embedding multi-modal dari teks dan gambar, sehingga memungkinkan deteksi berbasis deskripsi teks. Sebelum digunakan oleh model, gambar-gambar dipreproses dengan resize ke ukuran **224x224 piksel** untuk memastikan konsistensi dimensi input dan memaksimalkan performa. Setelah itu, data gambar dinormalisasi ke rentang nilai **[-1, 1]** dengan mean dan standar deviasi sebesar **0.5**. Selanjutnya, kandidat deskripsi didefinisikan untuk masing-masing kelas sebagai bagian dari proses analisis.

## Apa Itu CLIP?
CLIP adalah model pembelajaran mesin yang melibatkan penggunaan lebih dari satu jenis data (multimodal) atau sumber informasi dalam proses pelatihan dan inferensinya. CLIP dikembangkan oleh OpenAI dan dapat memahami hubungan antara teks dan gambar. Karena metode CLIP menggunakan dua jenis data, yaitu gambar dan teks, diperlukan dua encoder utama dalam proses tersebut, yaitu:

### 1. Image Encoder, proses mengkonversi gambar menjadi representasi vektor.
Berikut adalah salah satu contoh data.
![alt text](https://github.com/sains-data/Deteksi-Gambar-Kecelakaan-menggunakan-CLIP-dengan-Pendekatan-Zero-Shot/blob/main/Public/Contoh-data.png?raw=true)

### 2. Text Encoder, proses mengkonversi teks menjadi representasi vektor.
![alt text](https://github.com/sains-data/Deteksi-Gambar-Kecelakaan-menggunakan-CLIP-dengan-Pendekatan-Zero-Shot/blob/main/Public/Desk-Acc.png?raw=true)

![alt text](https://github.com/sains-data/Deteksi-Gambar-Kecelakaan-menggunakan-CLIP-dengan-Pendekatan-Zero-Shot/blob/main/Public/Desk-NonAcc.png?raw=true)

## Apa itu Zero-Shot Learning?
Zero-Shot Learning pada CLIP merujuk pada kemampuan model CLIP untuk melakukan tugas-tugas tertentu tanpa perlu pelatihan tambahan (fine-tuning) atau penyesuaian khusus untuk tugas tersebut. Dengan kata lain, CLIP dapat mengerjakan berbagai tugas baru hanya dengan diberi deskripsi teks yang relevan tanpa perlu melihat contoh data atau gambar yang berkaitan dengan tugas itu sebelumnya. CLIP bekerja dengan mengonversi label dataset atau kandidat deskripsi dan membandingkannya dengan representasi gambar melalui kesamaan kosinus (Cosine Similarity). Prediksi dibuat berdasarkan skor kesamaan tertinggi antara gambar dan teks menggunakan fungsi softmax (softmax probability).

![alt text](https://github.com/sains-data/Deteksi-Gambar-Kecelakaan-menggunakan-CLIP-dengan-Pendekatan-Zero-Shot/blob/main/Public/Zero-Shot.png?raw=true)

## Kandidat Kemiripan Tertinggi 
Sebagai contoh, untuk **Gambar 6**, deskripsi dengan probabilitas tertinggi adalah _"A car accident on a road"_, yang menunjukkan bahwa gambar tersebut paling cocok dengan kategori Accident. Begitu pula dengan **Gambar 8**, deskripsi dengan probabilitas tertinggi adalah _"A calm street with clear traffic"_, yang menunjukkan gambar tersebut paling cocok dengan kategori Non-Accident. Hasil probabilitas tertinggi ini diperoleh dari perhitungan kesamaan antara representasi gambar dan teks dalam ruang laten CLIP, dengan probabilitas yang lebih tinggi menandakan tingkat kecocokan yang lebih besar antara gambar dan deskripsi teks.

![alt text](https://github.com/sains-data/Deteksi-Gambar-Kecelakaan-menggunakan-CLIP-dengan-Pendekatan-Zero-Shot/blob/main/Public/Contoh-Prob-Acc.png?raw=true)

![alt text](https://github.com/sains-data/Deteksi-Gambar-Kecelakaan-menggunakan-CLIP-dengan-Pendekatan-Zero-Shot/blob/main/Public/Contoh-Prob-NonAcc.png?raw=true)

## Bagaimana Evaluasi Hasilnya?
Hasil eksperimen menunjukkan bahwa dengan menggunakan model CLIP ViT base patch 32 metode ini mencapai akurasi **Top-1** sebesar **32%** dan **Top-5** sebesar **95.86%**. Meskipun akurasi Top-1 masih memerlukan optimasi lebih lanjut, performa Top-5 yang tinggi mengindikasikan potensi besar CLIP dalam mendeteksi gambar kecelakaan secara efisien. Dengan pengembangan lebih lanjut, teknologi ini dapat menjadi solusi andal untuk berbagai skenario respons darurat.


