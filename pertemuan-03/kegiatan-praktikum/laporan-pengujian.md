## Laporan Kegiatan 
Pada implementasi login JWT ini, token disimpan menggunakan `localStorage` agar dapat digunakan kembali ketika aplikasi mengakses route yang membutuhkan autentikasi. Namun, cara tersebut masih memiliki keterbatasan dari sisi keamanan karena token dapat diakses oleh JavaScript pada halaman yang sama. Oleh karena itu, untuk aplikasi produksi diperlukan pengamanan tambahan, seperti masa berlaku token yang singkat, perlindungan terhadap serangan XSS, serta mekanisme penyimpanan token yang lebih aman sesuai kebutuhan aplikasi.

## Bukti Screenshot
### 1. mahasiswa
![hasil pengujian](screenshot/KG-1.png)
![hasil pengujian](screenshot/KG-2.png)
![hasil pengujian](screenshot/KG-3.png)

 ### 2. admin
![hasil pengujian](screenshot/KG-4.png)
![hasil pengujian](screenshot/KG-5.png)
![hasil pengujian](screenshot/KG-6.png)
