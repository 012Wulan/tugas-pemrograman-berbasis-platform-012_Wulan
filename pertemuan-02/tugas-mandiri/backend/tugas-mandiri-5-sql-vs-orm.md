## Tugas Mandiri 5 - Membandingkan SQL Mentah dan ORM

B. SQL Mentah
Dengan menggunakan SQL secara langsung, query yang digunakan adalah:
SELECT * FROM jadwal WHERE id = ?;
Jika menggunakan Node.js dengan library mysql2 
contohnya:
const [rows] = await connection.execute(
  'SELECT * FROM jadwal WHERE id = ?',
  [1]
);
Query tersebut digunakan untuk mengambil data pada tabel jadwal yang memiliki ID 1.

C. ORM 
Operasi yang sama dapat dilakukan menggunakan ORM
Prisma:
const jadwal = await prisma.jadwal.findUnique({
  where: {
    id: 1
  }
});
Dengan Prisma, programmer tidak perlu menulis query SQL secara langsung untuk operasi tersebut. Prisma 
akan menerjemahkan perintah tersebut menjadi query yang dapat dijalankan oleh database.

D. perbandingan SQL mentah dan ORM
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
Parameter query memisahkan data yang diberikan pengguna dari perintah SQL. Dengan begitu, input 
pengguna diperlakukan sebagai data dan tidak dianggap sebagai bagian dari perintah SQL.

6. Bagaimana ORM membantu programmer dalam mengakses database?
ORM membantu programmer dengan menyediakan method dan object untuk melakukan operasi database. 
Programmer dapat melakukan operasi seperti mengambil, menambahkan, mengubah, dan menghapus 
data melalui kode tanpa harus menulis SQL secara langsung untuk setiap operasi.
