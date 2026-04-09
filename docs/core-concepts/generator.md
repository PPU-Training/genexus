# GeneXus Generators

**GeneXus Generator** adalah komponen inti yang bertanggung jawab untuk menghasilkan kode sumber (*source code*) dalam bahasa pemrograman tertentu berdasarkan model yang didefinisikan dalam *Knowledge Base* (KB). Generator memungkinkan pengembang untuk membangun aplikasi tanpa harus menulis kode manual untuk infrastruktur, koneksi database, atau antarmuka dasar.

Setiap *Environment* dalam GeneXus memerlukan konfigurasi generator untuk menentukan target teknologi aplikasi yang akan dibangun.

---

## Arsitektur Generator
Generator dibagi menjadi dua peran utama berdasarkan arsitektur aplikasi:

### 1. Back-end Generator
Menghasilkan kode yang berjalan di sisi server (logika bisnis, akses data, dan API).
* **Default Generator:** Secara otomatis dibuat oleh GeneXus untuk menangani *back-end*.
* **Reorganization:** Generator ini juga bertanggung jawab untuk membuat program yang memodifikasi struktur database sesuai dengan perubahan model data (tabel, indeks, dll).



### 2. Front-end Generator
Menghasilkan kode untuk antarmuka pengguna (UI) dan logika sisi klien.
* **Web:** Seperti Angular, Java, atau .NET.
* **Mobile:** Menghasilkan aplikasi native untuk platform Android dan iOS.

---

## Fitur dan Fleksibilitas

### Generator Sekunder (Secondary Generators)
Selain generator utama, Anda dapat menambahkan **Secondary Generator**. Ini sangat berguna jika aplikasi Anda memerlukan integrasi multi-bahasa dalam satu lingkungan yang sama.
* **Contoh:** Menggunakan **Java** untuk modul web utama, namun menggunakan **RPG** untuk proses *batch* pada sistem iSeries.

### Penentuan Generator per Objek
GeneXus memberikan kontrol granular di mana Anda dapat menentukan generator mana yang akan memproses sebuah objek melalui properti **Generator**.
* Jika sebuah **Main Object** diatur ke generator tertentu, maka seluruh objek dalam *call tree* (rantai panggilan) objek tersebut akan dihasilkan menggunakan bahasa generator tersebut.

---

## Daftar Generator yang Didukung
Berikut adalah ringkasan teknologi yang didukung oleh GeneXus:

| Kategori | Generator |
| :--- | :--- |
| **Server-Side** | .NET, .NET Core, Java |
| **Client-Side Web** | Angular, HTML/JS |
| **Mobile** | Android, iOS (Apple) |
| **Legacy/Lainnya** | RPG, COBOL, Ruby, Visual FoxPro |

---

## Cara Konfigurasi di IDE
Untuk mengelola generator, Anda dapat mengikuti langkah-langkah berikut:

1. Buka jendela **Preferences** di IDE GeneXus.
2. Navigasi ke **Knowledge Base** > **Environments**.
3. Pilih *Environment* yang sedang aktif.
4. Klik kanan pada node **Back end** untuk menambah generator baru melalui opsi **New Generator**.
5. Gunakan opsi **Set As Reog Generator** pada salah satu generator untuk menentukan siapa yang bertanggung jawab atas struktur database.

---

> **Tip Profesional:** > Keunggulan utama menggunakan GeneXus adalah sifatnya yang *future-proof*. Anda dapat memindahkan seluruh sistem dari teknologi lama ke teknologi baru (misalnya dari .NET Framework ke .NET Core) hanya dengan mengganti generator tanpa harus mengubah logika bisnis yang sudah ada.
