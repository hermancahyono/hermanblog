---
weight: 6
title: "Events EventEmitter Dan Streams Nodejs"
date: 2023-08-11T11:32:44+07:00
lastmod: 2023-08-11T11:32:44+07:00
draft: false
description: "Events EventEmitter Dan Streams Nodejs"
featuredImage: ""
featuredImagePreview: ""
tags: [events, evenEmitter, streams, nodejs]
categories: [nodejs]
lightgallery: true
---

Modul `events`, `EventEmitter`, dan `Streams` adalah konsep-konsep yang terkait dalam Node.js yang semua berkaitan dengan pengelolaan peristiwa dan aliran data. Berikut adalah penjelasan tentang hubungan antara ketiganya:

1. **Modul `events`**: Modul ini adalah bagian dari inti Node.js dan menyediakan fungsionalitas dasar untuk mengimplementasikan pola "event-driven programming". Dalam modul ini, ada kelas utama yang disebut `EventEmitter` yang digunakan untuk mengatur peristiwa dan pendengar. Modul `events` adalah dasar bagi banyak aspek asynchronous programming dalam Node.js, dan ia menyediakan struktur dasar untuk menghubungkan komponen aplikasi melalui peristiwa.

2. **`EventEmitter`**: Ini adalah kelas yang ada dalam modul `events` dan memungkinkan Anda untuk membuat dan mengelola peristiwa dalam aplikasi Anda. Anda dapat membuat instance `EventEmitter`, menambahkan pendengar untuk peristiwa tertentu, dan memancarkan peristiwa tersebut. `EventEmitter` adalah salah satu bentuk penerapan pola "observer", di mana komponen yang berbeda dalam aplikasi dapat berkomunikasi melalui peristiwa. Walaupun tidak secara langsung terkait dengan data streaming, `EventEmitter` adalah fondasi dari banyak kerangka kerja asinkron dalam Node.js.

3. **`Streams`**: Streams adalah konsep yang memungkinkan Anda untuk memanipulasi data berkepanjangan dengan cara yang efisien dan asinkron. Dalam Node.js, ada beberapa jenis stream seperti `Readable`, `Writable`, `Duplex`, dan `Transform`. Stream memungkinkan Anda untuk membaca atau menulis data dalam potongan-potongan kecil daripada menangani keseluruhan data sekaligus. Ini sangat berguna saat berurusan dengan data besar atau ketika respons segera diperlukan, seperti pada permintaan HTTP yang segera mengirim respons sebelum seluruh data diterima.

Jadi, hubungan antara ketiganya adalah sebagai berikut: Modul `events` memberikan dasar bagi pola "event-driven programming", yang mengizinkan penggunaan `EventEmitter` untuk mengelola peristiwa dan pendengar. Sementara itu, `Streams` memberikan cara efisien untuk mengalirkan dan memproses data dalam bentuk aliran, dan dalam beberapa kasus, aliran data ini bisa berkaitan dengan peristiwa yang dikelola oleh `EventEmitter`.