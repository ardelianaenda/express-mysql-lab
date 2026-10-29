
# Praktikum Database dan Web

## Deskripsi Proyek

Proyek ini merupakan implementasi praktikum integrasi aplikasi web menggunakan Express.js, EJS, dan MySQL. Aplikasi mengelola data produk dengan menerapkan operasi CRUD (Create, Read, Update, Delete), arsitektur Model-View-Controller (MVC), koneksi basis data menggunakan connection pool, serta pengujian keamanan SQL Injection menggunakan Prepared Statements.

## Teknologi yang Digunakan

- Node.js
- Express.js
- EJS
- MySQL
- MySQL2
- DBeaver
- dotenv


## Matriks Penelusuran Pengujian (Traceability Matrix)

| ID Uji | Fitur / Operasi | Target Endpoint URL | HTTP Method | Skenario Pengujian | Hasil yang Diharapkan | Status | Bukti Tangkapan Layar |
|---|---|---|---|---|---|---|---|
| TC-01 | Koneksi Pool | App Startup | - | Server dijalankan pertama kali | Terhubung ke MySQL Pool tanpa error | Pass | `docs/screenshots/01-db-pool-connection.png` |
| TC-02 | Read (All) | `/produk` | GET | Akses halaman daftar produk | Menampilkan seluruh record tabel MySQL ke antarmuka EJS | Pass | `docs/screenshots/02-read-select-render.png` |
| TC-03 | Create | `/produk/tambah` | POST | Submit formulir produk baru | Data tersimpan di database, DevTools mencatat 302 Redirect ke `/produk` | Pass | `docs/screenshots/03-create-insert-prg.png` |
| TC-04 | Update | `/produk/edit/:id` | POST | Mengubah harga dan stok produk | Nilai kolom pada baris MySQL berubah sesuai input baru | Pass | `docs/screenshots/04-update-param-redirect.png` |
| TC-05 | Delete | `/produk/hapus/:id` | POST | Eksekusi tombol hapus | Baris record terhapus dari MySQL dan UI ter-refresh | Pass | `docs/screenshots/05-delete-feedback.png` |
| TC-06 | Keamanan | `/uji-keamanan` | GET | Input `' OR '1'='1` melalui URL | Prepared Statement memperlakukan input sebagai literal string (No Injection) | Pass | `docs/screenshots/06-sql-injection-mitigation.png` |
