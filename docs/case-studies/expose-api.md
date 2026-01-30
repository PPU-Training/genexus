# API Integration (Expose API)

## 1. Tinjauan Modul

**Nama Modul**  
Membuat API Integration (Expose API)

**Deskripsi**  
Modul ini membahas cara membuat API Integration (Expose API) yang dapat digunakan untuk mengakses data dari aplikasi lain.

**Tujuan Pembelajaran**  
Setelah menyelesaikan modul ini, peserta akan mampu membuat API Integration

**Ruang Lingkup Materi**  
Materi yang dibahas dalam modul ini meliputi:
- *- Data Modeling*
- *- User Interface Design*
- *- Business Logic & Procedures*

---

## 2. Implementasi Teknis

Bagian ini menjelaskan langkah-langkah teknis untuk membuat API Integration (Expose API).

Secara umum, implementasi dilakukan melalui tahapan berikut:
1. Jika menggunakan Procedure, ubah properties Export as Web Service jadi True.
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/expose-api/1.png)
  Dokumentasi API
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/expose-api/1.5.png)
2. Jika menggunakan Object API
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/expose-api/2.png)
  ```
      UserAPICRUD {      // inisiasi object terlebih dahulu untuk penamaan bebas
        
        GetUsers(out:&SDT_Users) // Default POST
        => Proc_Users(); // pemamnggilan procedure yang akan di expose ke api

        [RestMethod(POST)] // kalau semisal method api nya dalam bentuk POS harus ada tambahan seperti ini
        UserInsert(in:&SDT_User)
        => Proc_Insert_User(&SDT_User); // bentuk procedure kalau semisal dipanggil dan ada parameter inputnya codenya seperti ini.
      }
  ```
  Dokumentasi API
	![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/case-studies/expose-api/2.5.png)
3. Build All dan Jalankan aplikasi.
