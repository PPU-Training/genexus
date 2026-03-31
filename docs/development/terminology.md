# Terminology
---
| Object               | Description                                                                 | When to use                                                                 |
|-----------------------|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| API                  | Object untuk expose/mengonsumsi service (REST/SOAP).                        | Dipakai saat butuh integrasi dengan aplikasi lain.                          |
| Transaction          | Mendefinisikan tabel database, atribut, relasi, dan CRUD otomatis.          | Digunakan untuk membuat struktur data + ABM (Add, Browse, Modify).          |
| Data Provider        | Object untuk load, transformasi, dan return data dalam bentuk koleksi/struktur.| Dibutuhkan untuk menyiapkan data ke UI atau API.                             |
| Data Selector        | Object untuk Query reusable dengan filter tertentu.                        | Digunakan saat sering butuh query dengan kondisi spesifik.                  |
| Data View            | Object untuk mendefinisi view/tabel eksternal di database.                  | Dipakai kalau database sudah ada (legacy DB).                               |
| Domain               | Object untuk mendefinisikan tipe data dengan aturan khusus.                 | Digunakan untuk atribut/variabel agar konsisten validasinya (contoh: Email, Phone). |
| Procedure            | Object logic untuk implementasi algoritma terpisah yang bisa dipanggil.    | Digunakan untuk proses bisnis.                                              |
| Structured Data Type (SDT) | Object untuk mendefinisikan struktur data kompleks (mirip class).          | Digunakan untuk kirim/terima data di API.                                   |
| Subtype Group        | Object untuk mengelompokkan atribut dengan arti sama.                      | Digunakan agar bisa reuse rules & logika.                                   |
| Design System        | Object untuk berisi kumpulan style, layout, dan behavior standar.           | Digunakan untuk menjaga konsistensi UI di semua panel.                      |
| Master Panel         | Object template utama aplikasi web/mobile (misalnya: header, footer, menu).| Digunakan sebagai kerangka untuk layar lain.                                |
| Menu                 | Object untuk definisi navigasi/menu app.                                    | Digunakan untuk membuat daftar navigasi otomatis.                           |
| Panel                | Object untuk layar kustom, bebas desain & logic.                           | Digunakan untuk UI yang tidak otomatis dibuat oleh Transaction.             |
| Stencil              | Object template visual untuk mempercepat desain.                           | Digunakan saat butuh tampilan seragam (list, card, form).                   |
| Theme                | Kumpulan style visual (warna, font, ukuran).                               | Dipakai untuk branding aplikasi.                                            |
| URL Rewrite          | Aturan custom URL agar lebih ramah.                                         | Digunakan untuk SEO dan user friendly URL.                                  |
| User Control         | Object untuk komponen UI custom (misal calendar, map).                     | Digunakan saat kontrol bawaan GeneXus tidak cukup, kode dibuat manual.      |
| Web Component        | Object untuk membuat reusable component di banyak panel.                   | Digunakan untuk widget/partial screen.                                      |
| Web Master Panel     | Object template utama aplikasi web (khusus web).                           | Digunakan untuk konsistensi layout antar halaman web.                       |
| Web Panel            | Object layar web custom (tidak auto-generated).                            | Dipakai untuk form, laporan, dashboard, dll.                                |
| Web Theme            | Object tema khusus web (warna, CSS, style).                                | Digunakan untuk kustomisasi tampilan web app.                               |


| Feature        | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| Build<Panel>   | Generate dan Deploy App hanya panel tertentu.                               |
| BuildAll       | Generate dan Deploy App untuk yang ada perubahan saja.                      |
| Rebuild<Panel> | Generate ulang dan Deploy App hanya panel tertentu saja.                    |
| RebuildAll     | Generate ulang dan Deploy App seluruh Root Module dan dependencies.         |
| Attribute      | Sebuah field dari database / Transaction.                                   |
| Variable       | Sebuah field kosong untuk menampung data.                                   |
| Domain         | Sebuah template tipe data atau definisi tipe data kustom yang bisa dipakai ulang di seluruh aplikasi. |
| JSON Import    | Import JSON ke dalam GeneXus menjadi Structured Data Type (SDT) secara otomatis. |
