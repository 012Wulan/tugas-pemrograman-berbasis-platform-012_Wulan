## Tahap 9 - Tabel Pengujian Berdasarkan Respon Terminal atau Postman

| No. | Request | Harapan | Hasil Aktual |
|---|---|---|---|
| 1. | GET /api/v1 | 200, pesan welcome | 200 OK, status true, pesan "Welcome to API v1" |
| 2. | GET /api/v1/jadwal?status=aktif | 200, hanya data aktif | 200 OK, status true, menampilkan data jadwal dengan status aktif |
| 3. | GET /api/v1/jadwal/abc | 400, ide harus angka | 400 Bad Request, status false, id harus berupa angka |
| 4. | GET /api/v1/jadwal/99 | 404, jadwal tidak ditemukan | 404 Not Found, status false, pesan "Jadwal tidak ditemukan" |
| 5. | POST /api/v1/jadwal dengan body valid | 201, objek baru | 201 Created, status true, jadwal "Keamanan Aplikasi" berhasil ditambahkan |
| 6. | GET /api/v1/jadwal/1/peserta | 200, peserta jadwal 1 | 200 OK, status true, daftar peserta jadwal 1 berhasil diambil (Alya dan Bima) |
| 7. | GET /api/v1/jadwal/1/peserta/103 | 404, peserta berada di jadwal lain | 404 Not Found, status false, peserta tidak ditemukan pada jadwal ini |
| 8. | GET /api/v1/alamat-salah | 404, follback route | 404 Not Found, status false, route GET /api/v1/alamat-salah tidak ditemukan | 


## Screenshoot
