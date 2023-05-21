---
weight: 6   
title: "Cara Install Flutter tanpa Android Studio di Ubuntu 23.04."
date: 2019-12-01T21:57:40+08:00
lastmod: 2020-01-01T16:45:40+08:00
draft: false
description: "Cara Install Flutter tanpa Android Studio di Ubuntu 23.04."
featuredImage: "fotor-ai-20230514185617.png"
featuredImagePreview: "fotor-ai-20230514185617.png"

tags: ["flutter", "install"]
categories: ["flutter"]

lightgallery: true
---
## Cek Persyaratan Sistem

Untuk menginstall Flutter di Ubuntu 22.04 tanpa menggunakan Android Studio, ikuti langkah-langkah berikut:

Prasyarat Sistem Operasi : Linux (64-bit)
Disk Space : 600 MB (tidak termasuk disk space untuk IDE/tools).
Alat : 
Flutter bergantung pada ketersediaan commandline ini di lingkungan Anda:
* bash
* curl
* file
* git2.x
* mkdir  
* rm
* unzip
* which
* xz-utils
* zip
{{< admonition type=tip title="cara cek ketersediaan commandline" open=false >}}
```bash
which bash
which curl
wich file
```
dan seterusnya
{{< /admonition >}}
Download Flutter SDK dari situs resmi [Flutter](https://flutter.dev/docs/get-started/install/linux). Pilih "Linux" sebagai sistem operasi dan "tar.xz" sebagai format file.

## Install Manual 

Ekstrak file Flutter SDK yang telah didownload ke direktori yang diinginkan, misalnya `~/developmet/flutter/`

```bash
cd ~/development
tar xf ~/Downloads/flutter_linux_3.10.1-stable.tar.xz
```
### Tambahkan `flutter` ke path anda:
```bash
export PATH="$PATH:`pwd`/flutter/bin"
```
Perintah ini mengatur PATH variabel di terminal saat ini saja. Untuk menambahkan path Flutter secara permanen, Perbarui melalui `$ sudo nano ~/.bashrc` dan tambahkan path berikut ini 
{{< image src="/cara-install-flutter-tanpa-android-studio-di-ubuntu-23.04/Screenshot from 2023-05-21 12-24-34.png" caption="flutter path" >}}
{{< admonition type=note title="Catatan" open=false >}}
**Sesuaikan dengan path anda**
{{< /admonition>}}
### Jalankan `flutter doctor`

Perintah ini memeriksa lingkungan Anda dan menampilkan laporan ke terminal jendela. SDK Dart dibundel dengan Flutter; tidak perlu menginstal Dart secara terpisah. Periksa output dengan hati-hati untuk perangkat lunak lain yang mungkin Anda miliki perlu menginstal atau tugas lebih lanjut untuk dilakukan (ditampilkan dalam teks tebal ).
Misalnya: 
{{< image src="/cara-install-flutter-tanpa-android-studio-di-ubuntu-23.04/Screenshot from 2023-05-21 12-24-34.png" caption="flutter path" >}}