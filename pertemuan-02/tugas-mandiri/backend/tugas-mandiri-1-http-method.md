# Tugas Mandiri 1 — Mengenal HTTP Method dan Endpoint

## 1. GET
URL: https://httpbin.org/get?nama=Wulan&prodi=Informatika
Status: 200 OK
Hasil: Server berhasil menerima request GET dan mengembalikan query parameter yang dikirim.

## 2. POST
URL: https://httpbin.org/post
Data:
{
  "nama": "Wulan",
  "prodi": "Informatika"
}
Status: 200 OK
Hasil: Server berhasil menerima data JSON.

## 3. PUT
URL: https://httpbin.org/put
Data:
{
  "nama": "Wulan",
  "prodi": "Informatika",
  "semester": 4
}
Status: 200 OK
Hasil: Data berhasil diterima

## 4. PATCH
URL: https://httpbin.org/patch
Data:
{
  "semester": 4
}
Status: 200 OK
Hasil: Data perubahan berhasil diterima

## 5. DELETE
URL: https://httpbin.org/delete
Status: 200 OK
Hasil: Request DELETE berhasil diterima

## Tabel HasiL Pengujian
|No.|Method|Endpoint|Data yang dikirim|Status|Hasil|
|---:|---|---|---|---:|---|
|1.|GET|'/get'|Query parameter|200|Data query berhasil diterima server|
|2.|POST|'/post'|JSON nama dan prodi|

## Screenshot Pengujian
### GET 
![hasil pengujian get](screenshot/TM1-GET.JPEG)


### POST
hasil pengujian post
(https://github.com/012Wulan/tugas-pemrograman-berbasis-platform-012_Wulan/blob/main/pertemuan-02/tugas-mandiri/backend/screnshoot/TM1-POST.jpeg)
