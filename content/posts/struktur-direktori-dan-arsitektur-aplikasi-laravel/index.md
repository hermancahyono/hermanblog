---
weight: 6
title: "Struktur Direktori Dan Arsitektur Aplikasi Laravel"
date: 2023-05-21T21:20:18+07:00
lastmod: 2023-05-21T21:20:18+07:00
draft: false
description: "struktur direktori dan arsitektur aplikasi laravel"
featuredImage: "laravel-2.jpg"
featuredImagePreview: "laravel-2.jpg"
tags: ['laravel', 'struktur directori']
categories: ['laravel']
lightgallery: true
---

Struktur direktori dan arsitektur aplikasi Laravel mengikuti pendekatan "Model-View-Controller" (MVC) yang terkenal. Berikut adalah struktur direktori dan arsitektur umum aplikasi Laravel:

1. Direktori `app`: Direktori ini berisi kode inti aplikasi Laravel.
   - Direktori `Console`: Berisi perintah konsol yang dapat Anda buat.
   - Direktori `Exceptions`: Berisi pengecualian kustom untuk menangani kesalahan dalam aplikasi Anda.
   - Direktori `Http`: Berisi kontroler, middleware, dan pengaturan rute HTTP.
   - Direktori `Models`: Berisi model Eloquent untuk mengakses dan memanipulasi data dalam basis data.

2. Direktori `bootstrap`: Direktori ini berisi file yang membantu dalam proses bootstrapping dan konfigurasi awal aplikasi Laravel.

3. Direktori `config`: Berisi berbagai file konfigurasi untuk aplikasi Laravel, termasuk pengaturan basis data, cache, sesi, dan banyak lagi.

4. Direktori `database`: Direktori ini berisi skema basis data, migrasi, dan pengaturan pengujian.
   - Direktori `migrations`: Berisi file migrasi untuk mengatur perubahan skema basis data.
   - Direktori `seeds`: Berisi file pengisian data awal (seeder) untuk mengisi basis data dengan data sampel.

5. Direktori `public`: Direktori ini berisi file yang dapat diakses publik dari web, seperti file CSS, JavaScript, dan gambar. File `index.php` di direktori ini berfungsi sebagai titik masuk ke aplikasi Laravel.

6. Direktori `resources`: Direktori ini berisi berbagai sumber daya yang digunakan dalam pembangunan aplikasi Laravel.
   - Direktori `assets`: Berisi file aset seperti file LESS, SASS, atau JavaScript yang akan dikompilasi.
   - Direktori `lang`: Berisi file bahasa yang digunakan dalam aplikasi Anda.
   - Direktori `views`: Berisi file tampilan (view) yang digunakan untuk menghasilkan output HTML dari aplikasi.

7. Direktori `routes`: Direktori ini berisi file yang mendefinisikan rute HTTP aplikasi Anda.
   - File `web.php`: Berisi definisi rute untuk permintaan web.
   - File `api.php`: Berisi definisi rute untuk permintaan API.

8. Direktori `storage`: Direktori ini berisi file sementara, file log, dan file yang dihasilkan oleh aplikasi Laravel.
   - Direktori `app`: Berisi file-file yang dihasilkan oleh aplikasi, seperti file cache, sesi, dan file lainnya.
   - Direktori `framework`: Berisi file-file yang dihasilkan oleh kerangka kerja Laravel, seperti file cache framework dan file log.

9. Direktori `tests`: Direktori ini berisi file pengujian untuk aplikasi Laravel.

10. File `artisan`: Ini adalah file utilitas baris perintah yang kuat yang digunakan untuk menjalankan tugas-tugas pengembangan, seperti menjalankan migrasi dan pengujian.

Itulah beberapa direktori utama dalam struktur direktori dan arsitektur aplikasi Laravel. Struktur ini membantu memisahkan logika