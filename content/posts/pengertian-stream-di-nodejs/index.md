---
weight: 6
title: "Pengertian Stream Di Nodejs"
date: 2023-08-11T11:02:17+07:00
lastmod: 2023-08-11T11:02:17+07:00
draft: false
description: "catatan belajar nodejs/stream"
featuredImage: "stream.png"
featuredImagePreview: "stream.png"
tags: [stream, nodejs]
categories: [nodejs]
lightgallery: true
---

Dalam konteks Node.js, "stream" mengacu pada konsep yang digunakan untuk mengelola aliran data berkelanjutan (sequence of data) dalam input dan output. Stream memungkinkan Anda untuk memproses data secara efisien dalam potongan-potongan kecil, daripada harus menunggu seluruh data tersedia sebelum memulai pemrosesan.

## Ada empat jenis stream utama dalam Node.js:

1. **Readable Streams**: Ini adalah aliran data yang dapat dibaca. Contoh penggunaannya adalah membaca file, membaca data dari permintaan HTTP, atau mengonsumsi data dari sumber eksternal lainnya.

2. **Writable Streams**: Aliran ini digunakan untuk menulis data. Misalnya, menulis data ke file atau menulis respons HTTP.

3. **Duplex Streams**: Ini adalah gabungan dari Readable dan Writable streams. Anda dapat membaca dari dan menulis ke aliran ini secara bersamaan.

4. **Transform Streams**: Transform streams adalah jenis khusus dari duplex streams yang digunakan untuk mengubah atau memanipulasi data saat mengalir melalui aliran tersebut. Contohnya adalah mengkompresi data saat menulis ke file.

Keuntungan menggunakan stream dalam Node.js adalah efisiensi penggunaan memori dan kinerja yang lebih baik, terutama saat menangani data besar. Dalam pengolahan data secara berurutan, Anda tidak perlu menyimpan keseluruhan data di memori sekaligus, yang dapat menghemat sumber daya dan mengurangi waktu latensi.

Contoh penggunaan stream dalam membaca file dan mengirimkannya sebagai respons HTTP dapat dilihat dalam potongan kode berikut:

```javascript
const http = require('http');
const fs = require('fs');

const server = http.createServer((req, res) => {
  const readableStream = fs.createReadStream('large-file.txt');
  readableStream.pipe(res); // Mengalirkan data dari stream baca ke respons HTTP
});

server.listen(3000, () => {
  console.log('Server is running on port 3000');
});
```

Dalam contoh di atas, file "large-file.txt" dibaca sebagai Readable stream dan kemudian data dari stream tersebut dialirkan langsung ke respons HTTP menggunakan metode `pipe()`. Hal ini memungkinkan pengiriman data yang efisien dan adaptif tanpa harus menyimpan seluruh isi file di memori sekaligus.

**Berikut beberapa contoh lain tentang bagaimana penggunaan stream dalam Node.js:**

## 1. **Membaca dan Menulis Berkas dengan Stream**:

```javascript
const fs = require('fs');

const readableStream = fs.createReadStream('input.txt');  // Stream yang dapat dibaca dari berkas
const writableStream = fs.createWriteStream('output.txt'); // Stream yang dapat ditulis ke berkas

readableStream.pipe(writableStream); // Mengalirkan data dari input.txt ke output.txt
```

## 2. **Stream Permintaan dan Respons HTTP**:

```javascript
const http = require('http');

const server = http.createServer((req, res) => {
  // Stream yang dapat dibaca dari permintaan HTTP
  req.on('data', chunk => {
    // Memproses potongan data yang masuk
    console.log('Menerima data:', chunk.toString());
  });

  // Stream yang dapat ditulis untuk respons HTTP
  res.write('Halo, klien!\n');
  res.end();
});

server.listen(3000, () => {
  console.log('Server berjalan di port 3000');
});
```

## 3. **Mengompresi dan Mendekompresi Stream**:

```javascript
const fs = require('fs');
const zlib = require('zlib');

const readableStream = fs.createReadStream('large-file.txt');
const writableStream = fs.createWriteStream('compressed-file.txt.gz');

// Stream transform untuk mengompresi data dan menulisnya ke berkas terkompresi
const gzip = zlib.createGzip();
readableStream.pipe(gzip).pipe(writableStream);
```

## 4. **Menggunakan Stream Transform**:

```javascript
const fs = require('fs');
const { Transform } = require('stream');

// Stream transform untuk mengubah teks masukan menjadi huruf kapital
const upperCaseTransform = new Transform({
  transform(chunk, encoding, callback) {
    this.push(chunk.toString().toUpperCase());
    callback();
  }
});

const readableStream = fs.createReadStream('input.txt');
const writableStream = fs.createWriteStream('output.txt');

readableStream.pipe(upperCaseTransform).pipe(writableStream);
```

Contoh-contoh ini menunjukkan berbagai kasus penggunaan stream dalam Node.js, termasuk membaca dan menulis berkas, menangani permintaan dan respons HTTP, mengompresi dan mendekompresi data, dan menggunakan stream transform untuk mengubah data saat mengalir melalui saluran stream. Stream memberikan cara yang kuat dan efisien untuk menangani data, terutama ketika berurusan dengan sejumlah besar informasi.