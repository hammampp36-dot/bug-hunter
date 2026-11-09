
# Bug Hunter – Perbaikan Bug pada Project Laravel

**Tanggal:** 9 November 2026  
**Kegiatan:** Debugging dan Perbaikan Bug pada Project Laravel  
**Tujuan:** Memperbaiki error dan memastikan seluruh fitur pada website dapat berjalan dengan baik.

## 1. Menginstal Dependency Composer

Pertama, setelah mengunduh project, saya menemukan bahwa folder `vendor` belum tersedia.

Untuk mengatasi masalah tersebut, saya membuka terminal dan menjalankan perintah:

```bash
composer install
```

Perintah ini digunakan untuk menginstal seluruh dependency yang dibutuhkan oleh project Laravel.

## 2. Membuat File Environment (.env)

Setelah itu, saya menemukan bahwa project belum memiliki file `.env`. Namun, terdapat file `.env.example`.

Kemudian, saya membuat file `.env` dengan menyalin seluruh konfigurasi dari `.env.example`.

File `.env` digunakan untuk menyimpan konfigurasi aplikasi, seperti database, application key, dan pengaturan lainnya.

## 3. Membuat Application Key

Ketika memeriksa file `.env`, ternyata bagian `APP_KEY` masih kosong.

Untuk mengatasinya, saya menjalankan perintah:

```bash
php artisan key:generate
```

Perintah tersebut secara otomatis menghasilkan application key dan menyimpannya ke dalam file `.env`.

## 4. Membuat Database di phpMyAdmin

Selanjutnya, saya membuka phpMyAdmin dan membuat database baru dengan nama:

```text
bug-hunter
```

Kemudian, saya menyesuaikan konfigurasi database pada file `.env` agar menggunakan database yang telah dibuat.

Setelah itu, saya menjalankan perintah:

```bash
php artisan migrate
```

Perintah ini digunakan untuk membuat tabel-tabel database berdasarkan file migration yang tersedia di project.

## 5. Memperbaiki Kesalahan pada Route dan View

Selanjutnya, saya menemukan kesalahan pada bagian route yang berhubungan dengan pemanggilan view.

Terdapat perbedaan nama antara view yang dipanggil pada route dan nama file yang sebenarnya, khususnya pada bagian `layout`.

Saya kemudian menyesuaikan penamaan tersebut dengan menambahkan huruf `s` agar nama view yang dipanggil sesuai dengan file yang tersedia.

Setelah diperbaiki, halaman website dapat ditampilkan kembali.

## 6. Memperbaiki Gambar Produk Power Bank

Setelah website berhasil dijalankan, saya menemukan masalah lain, yaitu gambar produk power bank tidak muncul.

Saya kemudian memeriksa file dan lokasi penyimpanan gambar. Setelah ditelusuri, ternyata file gambar belum terhubung dengan benar pada bagian folder `public`.

Saya memperbaiki lokasi atau pemanggilan file gambar tersebut hingga gambar power bank berhasil ditampilkan pada website.

## 7. Mengubah Judul Website Secara Dinamis

Setelah semua perbaikan sebelumnya berhasil, saya menemukan bahwa judul website masih menggunakan nama bawaan Laravel.

Saya kemudian mengubah judul website agar tidak perlu menggantinya secara manual pada setiap halaman.

Caranya adalah dengan memanfaatkan konfigurasi pada file `.env`, khususnya bagian `APP_NAME`.

Dengan cara ini, nama website dapat diatur melalui satu konfigurasi sehingga lebih mudah dikelola, terutama jika website memiliki banyak halaman.

---

## Kesimpulan

Dari kegiatan debugging hari ini, saya belajar bahwa memperbaiki sebuah project Laravel tidak hanya tentang mengubah kode yang error, tetapi juga memahami struktur project dan konfigurasi yang digunakan.

Beberapa hal yang saya pelajari:

1. Menginstal dependency menggunakan Composer.
2. Membuat dan mengatur file environment (`.env`).
3. Menghasilkan application key menggunakan Artisan.
4. Membuat database dan menjalankan migration.
5. Memperbaiki kesalahan pemanggilan route dan view.
6. Memperbaiki path atau lokasi gambar pada folder `public`.
7. Mengatur nama website secara dinamis menggunakan konfigurasi `.env`.

**Pelajaran utama:** Sebelum mengubah kode, penting untuk memahami penyebab masalah terlebih dahulu agar perbaikan yang dilakukan tepat dan tidak menimbulkan bug baru.
