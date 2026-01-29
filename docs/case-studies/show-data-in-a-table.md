
# Show data in a table

## 1. Tinjauan Modul

**Nama Modul**  
Menampilkan Data ke Halaman Menggunakan Tabel

**Deskripsi**  
Modul ini membahas bagaimana menampilkan data yang berasal dari suatu *entity* ke dalam sebuah *screen* menggunakan komponen tabel di GeneXus.

**Tujuan Pembelajaran**  
Setelah menyelesaikan modul ini, peserta diharapkan mampu menyajikan data dari sebuah Transaction ke dalam tampilan aplikasi dalam bentuk tabel secara terstruktur dan mudah dibaca.

**Ruang Lingkup Materi**  
Materi yang dibahas dalam modul ini meliputi:
- *- Data Modeling*
- *- User Interface Design*
- *- Business Logic & Procedures*
- *- CRUD Operation (Read Operation)*

---

## 2. Implementasi Teknis

Bagian ini menjelaskan langkah-langkah teknis untuk mencapai tujuan pembelajaran pada modul ini, yaitu menampilkan data *Transaction* dalam bentuk tabel pada sebuah halaman (*Panel*).

Secara umum, implementasi dilakukan melalui tahapan berikut:
1. Membuat Structure Data Type (*SDT*)
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/show-data-in-a-table/1.png)
2. Membuat sebuah halaman (*Web Panel*).
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/show-data-in-a-table/2.png)
3. Membuat *Variable* didalam halaman dengan data type SDT Collection. 
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/show-data-in-a-table/3.png)
4. Menambahkan komponen tabel atau grid pada halaman.
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/show-data-in-a-table/4.png)
5. Mendefinisikan struktur data dengan membuat *Transaction*.
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/show-data-in-a-table/5.png)
6. Memastikan data telah tersedia di dalam database.
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/show-data-in-a-table/6.png)
7. Menghubungkan tabel (*Grid*) dengan *Transaction* agar data dapat ditampilkan secara otomatis dengan Data Provider.
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/show-data-in-a-table/7.png)
  Pastikan Output SDT Collection
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/show-data-in-a-table/7.5.png)
8. Menggunakan Data Provider untuk mengambil data dari *Transaction* di halaman.
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/show-data-in-a-table/8.png)
9. Build All dan Selesai.

Dengan mengikuti langkah-langkah tersebut, data yang tersimpan dalam *Transaction* akan berhasil ditampilkan pada halaman dalam bentuk tabel sesuai dengan tujuan modul.
