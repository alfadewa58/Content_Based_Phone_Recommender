# Mobile Phones Recommender System

### By: Alfa Isa Dewa

## Overview
Proyek ini berfokus pada pembuatan **Sistem Rekomendasi Ponsel** untuk membantu Perusahaan X, sebuah platform jual-beli HP online, dalam menyediakan pengalaman belanja yang lebih personal dan efektif bagi pengguna. Sistem ini dirancang untuk menampilkan rekomendasi produk yang relevan berdasarkan preferensi pengguna, sehingga meningkatkan kepuasan, memperpanjang waktu kunjungan, dan mendorong konversi penjualan.

## Stakeholders
- **Tim Manajemen Produk**: Memberikan arahan mengenai fitur rekomendasi yang diinginkan.
- **Tim Layanan Pelanggan**: Menyediakan wawasan mengenai kendala dan umpan balik dari pengguna terkait sistem rekomendasi.

## Business Understanding
### Context
Perusahaan X menghadapi tantangan dalam meningkatkan pengalaman pengguna karena banyaknya pilihan ponsel yang tersedia, yang seringkali membingungkan pengguna. Tujuan sistem rekomendasi ini adalah membantu pengguna menemukan produk yang sesuai dengan kebutuhan dan preferensi mereka dengan lebih cepat.

### Problem Statement
Perusahaan X mengalami tingkat bounce rate tinggi dan tingkat konversi yang rendah di halaman produk. Pengguna kesulitan menemukan ponsel yang cocok, sehingga perlu ada sistem yang membantu dalam pemilihan produk dengan lebih relevan.

### Goals
1. Membangun sistem rekomendasi untuk ponsel.
2. Menganalisis distribusi rating ponsel dalam dataset.
3. Menilai rentang harga ponsel berdasarkan kapasitas penyimpanan (ROM) untuk memberikan rekomendasi sesuai anggaran.

### Analytic Approach
Pendekatan yang digunakan adalah *content-based filtering*, dengan langkah-langkah berikut:
1. **Pemrosesan Data**: Membersihkan dan menyiapkan data agar setiap atribut ponsel seperti OS, RAM, ROM, harga, warna, dan kamera dapat direpresentasikan dalam bentuk vektor fitur.
2. **Pengukuran Kesamaan**: Menggunakan metode seperti *cosine similarity* atau *Euclidean distance* untuk menghitung kesamaan antar produk berdasarkan karakteristik yang relevan.
3. **Pengaturan Bobot Fitur**: Bobot fitur disesuaikan dengan preferensi pengguna, seperti harga atau OS.
4. **Evaluasi Sistem**: Metrik evaluasi seperti *Mean Average Precision (MAP)* dan *Normalized Discounted Cumulative Gain (NDCG)* digunakan untuk menilai relevansi rekomendasi.

### Metric Evaluation
- **Mean Reciprocal Rank (MRR)**: Menilai posisi item relevan pertama dalam daftar rekomendasi. Hasil MRR dari model ini adalah **0.9697**, yang menunjukkan bahwa sistem berhasil menampilkan item relevan di posisi atas dengan sangat baik.
  
## Sample Output
Berikut adalah contoh hasil rekomendasi yang dihasilkan oleh sistem:

| Mobile Phone   | ROM | RAM | Camera | Price | Score  |
|----------------|-----|-----|--------|-------|--------|
| oppo f11 pro   | 128 | 6.0 | 48     | 29990 | 0.9570 |
| oppo f15       | 128 | 4.0 | 48     | 20990 | 0.8167 |
| realme 6       | 128 | 6.0 | 64     | 15990 | 0.8029 |
| oppo f7        | 128 | 6.0 | 16     | 27990 | 0.7879 |
| realme 6       | 128 | 8.0 | 64     | 16999 | 0.7809 |
| redmi k20      | 128 | 6.0 | 48     | 24999 | 0.7731 |

## Insights from Data Analysis
1. **Distribusi Rating**: Ponsel dalam dataset memiliki rating tinggi secara umum, menunjukkan kepuasan pengguna yang baik, yang bisa dimanfaatkan untuk rekomendasi produk populer.
2. **Pengaruh Kapasitas Penyimpanan pada Harga**: Harga ponsel cenderung meningkat seiring dengan kapasitas penyimpanan (ROM) yang lebih besar.
3. **Hubungan Non-Linear Antara Harga dan Rating**: Tidak ada hubungan linear antara harga median dan rating pengguna, menunjukkan faktor lain mungkin mempengaruhi kepuasan pengguna.

## System Performance and Key Findings
1. **Akurasi Rekomendasi yang Tinggi**: Nilai MRR mendekati 1 menunjukkan bahwa sistem ini sangat akurat dalam menampilkan produk relevan di posisi teratas.
2. **Efektivitas dalam Menentukan Produk Relevan**: Sistem mengenali spesifikasi penting (seperti RAM, ROM, harga, dan kamera) yang relevan bagi pengguna.
3. **Pengalaman Pengguna yang Lebih Baik**: Rekomendasi yang lebih relevan memudahkan pengguna dalam menemukan produk yang sesuai, meningkatkan kepuasan dan efisiensi pencarian.
4. **Siap untuk Implementasi Nyata**: MRR yang tinggi menunjukkan kesiapan sistem untuk diimplementasikan dalam platform e-commerce.

## Recommendations for Further Development
1. **Penggunaan Data Teks**: Integrasikan data teks (seperti deskripsi produk dan ulasan) menggunakan TF-IDF untuk meningkatkan relevansi rekomendasi berdasarkan preferensi pengguna.
2. **Normalisasi Khusus Fitur**: Terapkan normalisasi berbeda untuk fitur seperti harga, berdasarkan kategori produk atau kelas harga, untuk memastikan relevansi rekomendasi yang lebih baik.
3. **Personalisasi Lebih Lanjut**: Gunakan data riwayat pengguna (klik, pencarian, pembelian) untuk menambah personalisasi rekomendasi, dan pertimbangkan pendekatan hybrid dengan collaborative filtering.