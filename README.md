# Deteksi-Gambar-Kecelakaan-menggunakan-CLIP-dengan-Pendekatan-Zero-Shot
## Anggota Kelompok 26:
1. 121450030 - Pramudya Wibowo  
2. 121450031 - Hartiti Fadilah  
3. 121450061 - Josua Alfa Viando Panggabean  
4. 121450093 - Anissa Luthfi Alifia  
5. 121450094 - Syifa Firnanda  
6. 121450109 - Della Septiani

## Abstrak
Deteksi gambar kecelakaan merupakan langkah penting dalam mendukung sistem respon cepat terhadap situasi darurat. Penelitian ini menggunakan model Contrastive Language–Image Pre-training (CLIP) untuk mendeteksi gambar kecelakaan dengan pendekatan zero-shot, tanpa memerlukan pelatihan ulang menggunakan dataset spesifik. Model CLIP menggabungkan embedding multi-modal dari teks dan gambar, memungkinkan deteksi berbasis deskripsi teks. Hasil eksperimen menunjukkan bahwa dengan menggunakan model CLIP ViT base patch 32 metode ini mencapai akurasi Top-1 sebesar 32% dan Top-5 sebesar 95.86%. Meskipun akurasi Top-1 masih memerlukan optimasi lebih lanjut, performa Top-5 yang tinggi mengindikasikan potensi besar CLIP dalam mendeteksi gambar kecelakaan secara efisien. Dengan pengembangan lebih lanjut, teknologi ini dapat menjadi solusi andal untuk berbagai skenario respons darurat.

## Apa Itu CLIP?
CLIP adalah model pembelajaran  mesin yang melibatkan penggunaan lebih dari satu jenis data (multimodal) atau sumber informasi dalam proses pelatihan dan inferensinya [5]. CLIP dikembangkan oleh OpenAI, yang dapat memahami hubungan antara teks dan gambar [6]. Dengan karakteristik metode CLIP yang menggunakan 2 jenis data yaitu gambar dan teks, diperlukan 2 encoder utama pada proses tersebut[5], yaitu: 
1. Image Encoder, proses mengkonversi gambar menjadi representasi vektor.
2. Text Encoder, proses mengkonversi teks menjadi representasi vektor.

![alt text](https://github.com/sains-data/Deteksi-Gambar-Kecelakaan-menggunakan-CLIP-dengan-Pendekatan-Zero-Shot/blob/main/Public/CLIP.png?raw=true)






