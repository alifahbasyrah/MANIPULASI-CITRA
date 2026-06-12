Nama: Alifah Basyrah Marsani
NIM: 452024618073
Kelas: Universitas Darussalam Gontor C1 

Implementasi dan Analisis Operasi Point Processing serta Spatial Resizing pada Citra Digital Dua Dimensi
Deskripsi Singkat Project
Project ini merupakan sebuah eksperimen berbasis Python untuk mengeksplorasi bagaimana operasi matematika tingkat rendah (low-level image processing) dapat memodifikasi struktur matriks pixel pada citra digital. Eksperimen berfokus pada teknik prapemrosesan (preprocessing) citra melalui spatial resizing (penyelarasan dimensi), serta manipulasi nilai intensitas warna (point processing) yang meliputi penggabungan dua gambar (Image Blending), inversi warna (Image Negative), serta peningkatan kualitas visual non-linear (Transformasi Logaritmik dan Transformasi Gamma/Power-Law).
Selain performa visual, project ini juga menyajikan analisis statistik sebaran warna melalui visualisasi histogram untuk mendiagnosis perubahan brightness dan contrast dari citra objek yang dimanipulasi.
Citra yang Digunakan
Eksperimen ini wajib menggunakan dua citra digital mandiri berbeda dengan karakteristik sebagai berikut:
1.	image1.jpg (Citra Utama): Berupa foto berformat JPEG objek utama atau pemandangan dengan variasi pencahayaan yang jelas untuk diuji transformasinya.
2.	image2.jpg (Citra Kedua/Tekstur): Berupa gambar dengan pola/tekstur yang akan digunakan sebagai latar atau komponen penggabungan efek transparan.
Catatan: Kedua file gambar ini wajib diletakkan di dalam direktori kerja utama sebelum program dijalankan.
Library yang Digunakan
Project ini dibangun menggunakan ekosistem Python 3 dengan beberapa library standar pengolahan data:
•	OpenCV (cv2): Library utama untuk membaca citra, konversi ruang warna BGR ke RGB, operasi pengubahan ukuran (resizing), serta komputasi blending.
•	NumPy: Digunakan untuk manipulasi array matriks pixel 2D/3D secara cepat, konversi tipe data (seperti uint8 ke float), dan perhitungan logaritma serta eksponensial.
•	Matplotlib (pyplot): Digunakan sebagai instrumen visualisasi untuk menampilkan gambar hasil pemrosesan dan memplot grafik distribusi histogram warna.
6. Cara Menjalankan Notebook
Untuk menjalankan file image-manipulation.ipynb di lingkungan lokal komputer Anda maupun di cloud environment (seperti Kaggle atau Google Colab), ikuti langkah-langkah berikut:
 Kaggle Notebook 
7. Struktur Folder Project
Agar project terorganisasi dengan rapi di GitHub, berikut adalah rekomendasi struktur foldernya:
Plaintext
 project-manipulasi-citra/
•	README.md                 
•	image-manipulation.ipynb  
•	lake.jpg                
•	rain.jpg                
•	output/                   
-	blend_result.png
-	negative_result.png
-	gamma_histogram.png
8. Ringkasan Hasil Eksperimen
Eksperimen ini berhasil memetakan perubahan matematis menjadi perubahan fisis visual pada citra. Berikut adalah ringkasan performa dari masing-masing teknik:
•	Konversi Warna (BGR to RGB): Berhasil meniadakan distorsi efek kebiruan akibat perbedaan urutan penyimpanan matriks warna bawaan OpenCV saat digambar oleh Matplotlib.
•	Spatial Resizing: Menghasilkan keseragaman ukuran matriks (misal 600x400 pixel) sehingga mencegah terjadinya kegagalan size mismatch error sewaktu dua matriks citra dijumlahkan.
•	Image Blending: Pengaturan kombinasi bobot skalar α dan  βmemunculkan efek transparansi halus (cross-dissolve). Total intensitas pixel terjaga stabil karena menggunakan syarat α+β= 1.
•	Image Negative: Membalikkan kurva histogram secara simetris lateral (255 - r), mengubah area gelap gulita menjadi putih terang.
•	Transformasi Logaritmik & Gamma (γ< 1): Berhasil melakukan perbaikan kualitas gambar (image enhancement) pada area bayangan (shadow) yang gelap. Grafik histogram membuktikan bahwa tumpukan data pixel rendah ditarik dan didistribusikan melebar ke area tengah dan kanan (terang) secara halus/non-linear tanpa merusak area yang sudah terang (oversaturation).
9. Kesimpulan Singkat
Manipulasi citra digital sejatinya adalah operasi aritmetika pada matriks dua dimensi. Penggunaan transformasi non-linear (seperti Logaritma dan Gamma) terbukti jauh lebih efektif, adaptif, dan natural dalam memperbaiki pencahayaan citra dibandingkan pengali skalar linear biasa. Perubahan visual pada gambar selalu berkorelasi tegak lurus dengan pola pergeseran grafik distribusi statistik pada histogram citranya. Dokumentasi dan visualisasi histogram ini sangat krusial sebagai fondasi prapemrosesan data pada pemodelan AI (Computer Vision) tingkat lanjut.

