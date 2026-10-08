## Tugas Mandiri 5 - Membandingkan SQL Mentah dan ORM
### Tujuan : 
Memahami perbedaan penggunaan SQL mentah dan ORM dalam mengakses database serta mengetahui kelebihan, kekurangan, dan keamanan dari kedua pendekatan tersebut.

### Perbandingan SQL Mentah dan ORM
| Aspek | SQL Mentah | ORM prisma |
|---|---|---|
| Cara penulisan | Menggunakan perintah SQL secara langsung | Menggunakan method dan object |
| Contoh | SELECT * FROM jadwal WHERE id = ? | prisma.jadwal.findUnique() |
| Penggunaan | Query ditulis dan dikontrol langsung oleh programmer | Query dibuat oleh ORM berdasarkan kode yang diberikan |
| Kemudahan | Membutuhkan pemahaman SQL | Lebih sederhana untuk operasi database umum |
| Kontrol Query | Lebih bebas dalam menentukan query | Mengikuti fitur dan method yang tersedia pada ORM |
| Keamanan | Perlu menggunakan parameter query agar lebih aman | ORM membantu menangani parameter pada operasi database tertentu |

1. Apa perbedaan SQL mentah dan ORM?
SQL mentah menggunakan perintah SQL secara langsung untuk berkomunikasi dengan database. Sedangkan ORM 
menggunakan object dan method dari library pemrograman untuk mengakses database tanpa harus 
menulis SQL secara langsung pada operasi tertentu.

2. Apa kelebihan SQL mentah?
Kelebihan SQL mentah adalah programmer memiliki kontrol lebih besar terhadap query yang dijalankan. 
SQL mentah juga dapat digunakan untuk membuat query yang kompleks dan dapat disesuaikan dengan kebutuhan database.

3. Apa kelebihan ORM?
ORM membuat proses pengaksesan database menjadi lebih sederhana karena programmer dapat menggunakan 
kode dari bahasa pemrograman. ORM juga membantu mengurangi penulisan query SQL secara manual dan membuat kode lebih mudah dikelola.

4. Apa risiko SQL injection?
SQL Injection adalah serangan yang terjadi ketika input dari pengguna dimasukkan ke dalam query SQL 
tanpa penanganan yang aman. Hal ini dapat menyebabkan penyerang memanipulasi query dan 
mengakses atau mengubah data yang seharusnya tidak boleh diakses.

5. Mengapa penggunaan parameter query dapat mengurangi risiko SQL injection?
Karena Parameter query memisahkan data yang diberikan pengguna dari perintah SQL. Dengan begitu, input 
pengguna diperlakukan sebagai data dan tidak dianggap sebagai bagian dari perintah SQL.

6. Bagaimana ORM membantu programmer dalam mengakses database?
ORM membantu programmer dengan menyediakan method dan object untuk melakukan operasi database. 
Programmer dapat melakukan operasi seperti mengambil, menambahkan, mengubah, dan menghapus 
data melalui kode tanpa harus menulis SQL secara langsung untuk setiap operasi.
