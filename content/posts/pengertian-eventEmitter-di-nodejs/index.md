---
weight: 6
title: "Pengertian EventEmitter Di Nodejs"
date: 2023-08-11T11:30:53+07:00
lastmod: 2023-08-11T11:30:53+07:00
draft: false
description: "Pengertian EventEmitter Di Nodejs"
featuredImage: ""
featuredImagePreview: ""
tags: [evenEmitter, nodejs]
categories: [nodejs]
lightgallery: true
---

`EventEmitter` adalah kelas yang ada di dalam modul `events` dalam Node.js. Ini adalah contoh yang baik dari sebuah stream dalam arti umum, meskipun bukan kelas yang secara langsung terkait dengan pembacaan atau penulisan data seperti halnya `Readable` atau `Writable` stream. Sebagai gantinya, `EventEmitter` digunakan untuk mengelola dan mengirim peristiwa (event) dalam aplikasi Anda.

Dalam konteks ini, "event" mengacu pada suatu kejadian yang terjadi dalam program Anda, seperti penekanan tombol, permintaan HTTP yang masuk, atau penyelesaian operasi berkepanjangan. `EventEmitter` memungkinkan Anda untuk membuat, mendengarkan, dan mengelola peristiwa ini.

Anda dapat membuat instansi `EventEmitter`, menambahkan pendengar (listener) ke peristiwa tertentu, dan kemudian memancarkan (emit) peristiwa tersebut. Berikut adalah contoh sederhana:

```javascript
const EventEmitter = require('events');

// Membuat instansi EventEmitter
const myEmitter = new EventEmitter();

// Menambahkan pendengar untuk peristiwa 'customEvent'
myEmitter.on('customEvent', (message) => {
  console.log(`Pesan terdengar: ${message}`);
});

// Memancarkan peristiwa 'customEvent'
myEmitter.emit('customEvent', 'Halo, dunia!');
```

Dalam kasus ini, kita membuat instansi `myEmitter` dari `EventEmitter`. Kemudian kita menambahkan pendengar untuk peristiwa bernama `'customEvent'`. Ketika `myEmitter` memancarkan peristiwa `'customEvent'`, pendengar yang kita tambahkan akan diaktifkan dan menjalankan fungsinya.

`EventEmitter` adalah dasar dari banyak aspek event-driven programming dalam Node.js, termasuk dalam framework dan modul bawaan seperti HTTP server dan banyak komponen lain yang berfungsi dengan mengandalkan pemancaran dan pendengaran peristiwa.  
