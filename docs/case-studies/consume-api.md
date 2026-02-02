# API Integration (Consume API)

## 1. Tinjauan Modul

**Nama Modul**  
Membuat API Integration (Consume API)

**Deskripsi**  
Modul ini membahas cara membuat API Integration (Consume API)
**Tujuan Pembelajaran**  
Setelah menyelesaikan modul ini, peserta akan mampu membuat API Integration (Consume API)

**Ruang Lingkup Materi**  
Materi yang dibahas dalam modul ini meliputi:
- *- Data Modeling*
- *- User Interface Design*
- *- Business Logic & Procedures*

---

## 2. Implementasi Teknis

Bagian ini menjelaskan langkah-langkah teknis untuk membuat API Integration (Consume API).

Secara umum, implementasi dilakukan melalui tahapan berikut:
1. Buat SDT sesuai dari response API, bisa buag manual atau pakai JSON Import
  contoh response API
{
  "id": 1,
  "name": "Ivan"
}
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/consume-api/1.png)
otomatis jadi SDT.
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/consume-api/2.png)

2. Buat Procedure untuk mengambil data dari API.
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/consume-api/3.png)
3. Gunakan Procedure di Web Panel untuk menampilkan data.
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/consume-api/4.png)
5. Build All dan Jalankan Aplikasi.
