## Tugas Mandiri 2 — Menyusun Tata Letak dengan Class Utility
### Tujuan 
Memahami penggunaan class utility Tailwind CSS untuk mengatur tata letak halaman web serta mengetahui 
perubahan tampilan berdasarkan ukuran layar.

### 1. Hasil Pembuatan Halaman
Pada tugas ini, saya membuat halaman web Profil Mahasiswa dengan tema warna pink. Halaman tersebut 
terdiri dari navbar, bagian pembuka (hero), tiga kartu informasi, dan footer. Saya menggunakan 
Tailwind CSS melalui CDN untuk mengatur warna, ukuran teks, jarak, dan tata letak tanpa menambahkan 
CSS buatan sendiri.

### 2. Class Utility yang Digunakan
| Bagian | Class Utility | Fungsi |
| Navbar | flex items-center justify-between gap-3 | Mengatur posisi judul dan menu agar berada dalam satu baris serta memberikan jarak |
| Navbar Responsif | md:px-10 md:gap-6 | Menambah padding dan jarak antarmenu pada layar yang lebih lebar |
| Hero | flex flex-col items-center gap-4 | Menyusun isi bagian pembuka secara vertikal dan memberikan jarak antar elemen |
| Hero Rensponsif | md:flex-row md:justify-center | Mengubah susunan hero menjadi horizontal pada layar yang lebih lebar |
| Kumpulan Kartu | grid grid-cols-1 gap-5 | Menyusun tiga kartu dalam satu kolom dan memberikan jarak antarkartu |
| Kartu Responsif | md:grid-cols-3 | Mengubah susunan kartu menjadi tiga kolom ketika layar mencapai breakpoint md |
| Tampilan Kartu | rounded-xl bg-white p-6 shadow-md | Memberikan sudut membulat, latar putih, ruang di dalam kartu, dan bayangan |
| Efek Hover Kartu | hover:-translate-y-1 hover:shadow-xl | Membuat kartu sedikit terangkat dan bayangannya lebih besar saat kursor diarahkan ke kartu |
| Tombol | bg-pink-400 hover:bg-pink-600 | Memberikan warna pink pada tombol dan mengubahnya menjadi pink yang lebih gelap saat kursor diarahkan ke tombol |
| Footer | bg-pink-400 px-5 py-6 text-center | Memberikan latar pink, mengatur jarak dalam, dan membuat teks berada di tengah |

### 3. Perubahan Tampilan Berdasarkan Ukuran Layar
Pada layar kecil, bagian hero disusun secara vertikal dan ketiga kartu ditampilkan dalam satu kolom 
agar isi halaman lebih mudah dibaca. Ketika layar lebih lebar dan mencapai breakpoint md, susunan 
hero berubah menjadi horizontal, sedangkan kartu ditampilkan dalam tiga kolom. Pengaturan tersebut 
dilakukan menggunakan class flex-col, md:flex-row, grid-cols-1, dan md:grid-cols-3. Dengan 
menggunakan class tersebut, tampilan halaman dapat menyesuaikan ukuran layar tanpa harus membuat 
aturan CSS sendiri. Selain itu, class yang diawali hover: digunakan untuk memberikan perubahan 
tampilan saat kursor diarahkan ke tombol atau kartu. Efek ini membuat halaman terasa lebih 
interaktif ketika dibuka melalui laptop atau komputer.

### 4. Pengalaman Menggunakan Class Utility 
Menurut saya, bagian yang paling mudah diatur menggunakan class utility adalah kumpulan kartu 
karena class grid, grid-cols-1, md:grid-cols-3, dan gap-5 sudah cukup untuk mengatur susunan serta 
jarak antarkartu. Sementara itu, bagian navbar dan hero sedikit lebih sulit dibaca ketika beberapa 
class digunakan secara bersamaan, terutama untuk mengatur posisi elemen dan tampilan responsif. 
Karenanya, saya perlu memahami fungsi setiap class agar bisa mengatur tampilan halaman dengan benar.

### 5. Bukti Sreenshot
### A. Tampilan Laptop 


### B. Tampilan Layar 360 PX


### Kesimpulan 
Berdasarkan tugas yang telah dikerjakan, saya memahami bahwa Tailwind CSS dapat digunakan untuk 
mengatur tampilan halaman web melalui class utility. Penggunaan class responsif membantu 
menyesuaikan tata letak dengan ukuran layar, sedangkan class hover memberikan efek ketika kursor 
diarahkan ke elemen tertentu. Dengan demikian, halaman dapat dibuat lebih rapi dan responsif tanpa 
menambahkan CSS buatan sendiri.
