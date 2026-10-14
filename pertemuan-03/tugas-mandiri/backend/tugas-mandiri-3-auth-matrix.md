# Tugas Mandiri 3 — Analisis Autentikasi dan Otorisasi

## 1. Peran Pengguna

Pada proyek Elibrary, terdapat tiga peran pengguna yang memiliki hak akses berbeda sesuai dengan tugasnya, yaitu:

1. **Anggota**, yaitu pengguna yang dapat melihat katalog buku, mencari buku, meminjam buku, melihat riwayat peminjaman, dan melihat status peminjaman.
2. **Pustakawan**, yaitu pengguna yang bertugas mengelola data buku, memproses peminjaman dan pengembalian, serta melihat data peminjaman.
3. **Pimpinan**, yaitu pengguna yang dapat melihat katalog buku dan laporan atau rekap aktivitas perpustakaan untuk memantau pengelolaan Elibrary.

## 2. Matriks Hak Akses

Tabel berikut menunjukkan hak akses setiap peran terhadap fitur yang tersedia pada aplikasi Elibrary.

| Fitur | Anggota | Pustakawan | Pimpinan | Titik Akhir (Endpoint) |
|---|:---:|:---:|:---:|---|
| Melihat katalog buku | ✅ | ✅ | ✅ | `GET /buku` |
| Mencari buku berdasarkan judul | ✅ | ✅ | ✅ | `GET /buku/search` |
| Melakukan peminjaman buku | ✅ | ✅ | ❌ | `POST /peminjaman` |
| Melihat riwayat peminjaman pribadi | ✅ | ❌ | ❌ | `GET /peminjaman/riwayat` |
| Menambahkan data buku | ❌ | ✅ | ❌ | `POST /buku` |
| Mengubah data buku | ❌ | ✅ | ❌ | `PUT /buku/:id` |
| Memproses pengembalian buku | ❌ | ✅ | ❌ | `PUT /peminjaman/:id/pengembalian` |
| Melihat rekap peminjaman | ❌ | ✅ | ✅ | `GET /laporan/peminjaman` |

Keterangan:

- ✅ = Peran tersebut diizinkan mengakses fitur.
- ❌ = Peran tersebut tidak diizinkan mengakses fitur dan akan menerima respons `403` apabila sudah login dengan token yang valid.
- Endpoint yang tercantum merupakan rancangan endpoint untuk proyek Elibrary.

## 3. Perbedaan Kode 401 dan 403

Kode `401 Unauthorized` digunakan ketika pengguna mengakses endpoint yang dilindungi tanpa menyertakan token atau menggunakan token yang tidak valid. Contohnya, pengguna yang belum login mencoba mengakses `GET /buku`, sehingga sistem menolak permintaan karena identitas pengguna belum berhasil diverifikasi. Sementara itu, kode `403 Forbidden` digunakan ketika pengguna sudah login dan memiliki token yang valid, tetapi tidak mempunyai hak akses terhadap fitur yang diminta. Contohnya, anggota mencoba mengakses `POST /buku` untuk menambahkan data buku. Sistem sudah mengetahui identitas pengguna, tetapi permintaan tetap ditolak karena fitur tersebut hanya boleh digunakan oleh pustakawan. Dengan demikian, autentikasi berfungsi untuk memeriksa identitas pengguna, sedangkan otorisasi berfungsi untuk menentukan apakah pengguna tersebut memiliki izin mengakses fitur tertentu.

## 4. Risiko Jika Endpoint Hanya Menggunakan requireAuth

Jika endpoint hanya menggunakan `requireAuth` tanpa `requireRole`, sistem hanya memeriksa apakah pengguna sudah login dan memiliki token yang valid. Akibatnya, anggota yang sudah login berpotensi menambahkan atau mengubah data buku meskipun fitur tersebut seharusnya hanya dapat diakses oleh pustakawan. Oleh karena itu, penggunaan `requireRole` diperlukan agar setiap endpoint hanya dapat diakses oleh pengguna yang memiliki peran sesuai dengan hak aksesnya.
