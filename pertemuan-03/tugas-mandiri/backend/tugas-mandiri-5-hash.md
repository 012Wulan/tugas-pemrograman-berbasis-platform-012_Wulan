# Tugas Mandiri 5 — Hashing vs Encryption dan Secrets

## 1. Hasil Percobaan Hashing
| No. | Input | Cost Factor | Hasil Hash |
|---|---|---|---|
| 1 | `sama` | 10 | `$2a$10$43pG74BnlxYd8lxCQIL29.lhrouwD6a99ykLOlPSuGL5zpp.7wGGW` |
| 2 | `sama` | 10 | `$2a$10$IJujQgS3UW776SND7MS5duZ8oZDDvrHEvqmKPoM3kTk1Dv.1U35p2` |

Dari percobaan tersebut, hasil hash dari input yang sama ternyata berbeda. Hal ini terjadi karena bcrypt menggunakan salt acak saat membuat hash. Cost factor 10 menentukan tingkat biaya komputasi yang digunakan dalam proses hashing.

## 2. Jawaban Pertanyaan
### a. Apa perbedaan hashing dan encryption?
Hashing adalah proses mengubah data menjadi nilai hash yang tidak dirancang untuk dikembalikan ke bentuk aslinya. Sementara itu, encryption adalah proses mengubah data menjadi bentuk yang tidak mudah dibaca dan dapat dikembalikan menggunakan kunci dekripsi yang sesuai.

### b. Mengapa password sebaiknya disimpan dalam bentuk hash, bukan plaintext?
Password sebaiknya disimpan dalam bentuk hash agar password asli tidak langsung diketahui jika database bocor. Dengan begitu, keamanan password pengguna lebih terjaga dibandingkan jika password disimpan dalam bentuk teks biasa atau plaintext.

### c. Apa fungsi `bcrypt.compare()`?
`bcrypt.compare()` digunakan untuk memeriksa apakah password yang dimasukkan pengguna sesuai dengan hash password yang tersimpan. Fungsi ini menghasilkan nilai `true` jika cocok dan `false` jika tidak cocok. Password tidak perlu diubah kembali dari hash menjadi teks asli.

### d. Apa itu rainbow table dan bagaimana salt membantu mengatasinya?
Rainbow table adalah kumpulan nilai hash yang telah dihitung sebelumnya untuk membantu menebak data asli dari hash. Salt merupakan nilai acak yang ditambahkan saat proses hashing sehingga password yang sama dapat menghasilkan hash berbeda. Hal ini membuat penggunaan rainbow table menjadi lebih sulit dan kurang efektif.

### e. Apa fungsi `JWT_SECRET` dan mengapa harus dirahasiakan?
`JWT_SECRET` adalah kunci rahasia yang digunakan untuk menandatangani dan memverifikasi token JWT pada algoritma yang menggunakan secret tersebut. Jika kunci ini bocor, pihak lain berpotensi membuat token palsu yang tanda tangannya valid. Oleh karena itu, `JWT_SECRET` harus disimpan dengan aman, misalnya melalui file `.env`, dan tidak boleh dimasukkan ke repositori Git.

## 3. Pemeriksaan Keamanan Repositori
| No. | Pemeriksaan | Hasil | Keterangan |
|---|---|---|---|
| 1 | Memeriksa apakah `backend/.env` dilacak oleh Git | Tidak dilacak | Perintah `git ls-files --error-unmatch backend/.env` menghasilkan pesan bahwa file tidak ditemukan dalam daftar file yang dilacak Git. |
| 2 | Mencari pola token JWT pada folder `docs`, `frontend/web`, dan `frontend/mobile` | Tidak ditemukan kecocokan | Perintah `git grep` tidak menghasilkan keluaran untuk pola token JWT yang dicari pada lokasi tersebut. |

Berdasarkan pemeriksaan tersebut, file `backend/.env` tidak sedang dilacak oleh Git dan tidak ditemukan pola token JWT yang dicari pada folder pemeriksaan. Namun, hasil ini hanya berlaku untuk file dan pola yang diperiksa, sehingga belum membuktikan bahwa seluruh repositori bebas dari secret atau token sensitif.
