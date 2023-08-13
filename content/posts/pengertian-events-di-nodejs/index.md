---
weight: 6
title: "Pengertian Events Di Nodejs"
date: 2023-08-11T11:27:31+07:00
lastmod: 2023-08-11T11:27:31+07:00
draft: false
description: "Pengertian Events Di Nodejs"
featuredImage: "events.png"
featuredImagePreview: "events.png"
tags: [events, nodejs]
categories: [nodejs]
lightgallery: true
---
## Pengertian
Modul [events](https://nodejs.org/docs/latest-v18.x/api/events.html#events) dalam Node.js adalah modul [inti/core nodejs](https://codeburst.io/all-about-core-nodejs-part-1-b9f4b0a83278) yang memungkinkan Anda untuk mengimplementasikan dan mengelola pola ["event-driven programming"](https://en.wikipedia.org/wiki/Event-driven_programming). Pola ini berguna ketika Anda ingin membangun aplikasi yang merespons peristiwa yang terjadi, seperti tindakan pengguna, interaksi jaringan, atau operasi [asinkron](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Introducing) lainnya. Modul [events](https://nodejs.org/docs/latest-v18.x/api/events.html#events) menyediakan kelas [EventEmitter](https://nodejs.org/docs/latest-v18.x/api/events.html#events_eventemitter) yang digunakan untuk mengatur peristiwa dan pendengar. [EventEmitter](https://nodejs.org/docs/latest-v18.x/api/events.html#events_eventemitter) adalah kelas yang ada dalam modul [events](https://nodejs.org/docs/latest-v18.x/api/events.html#events) yang menjadi pusat pengelolaan peristiwa dalam aplikasi.

Berikut adalah komponen-komponen penting dari modul [events](https://nodejs.org/docs/latest-v18.x/api/events.html#events):

## 1. **EventEmitter Class**: 

Ini adalah kelas yang memungkinkan Anda untuk membuat instance yang mampu memancarkan (emit) peristiwa dan memungkinkan pendengar (listener) untuk merespons peristiwa tersebut. [EventEmitter](https://nodejs.org/docs/latest-v18.x/api/events.html#events_eventemitter) memiliki sejumlah metode yang paling penting adalah:

   - `.on(eventName, listener)`: Menambahkan pendengar untuk suatu peristiwa.
   - `.emit(eventName, [args])`: Memancarkan peristiwa dengan nama tertentu kepada semua pendengar yang terkait.
   - `.once(eventName, listener)`: Menambahkan pendengar untuk peristiwa yang hanya diaktifkan sekali.
   - `.removeListener(eventName, listener)`: Menghapus pendengar tertentu dari suatu peristiwa.
   - `.removeAllListeners([eventName])`: Menghapus semua pendengar dari suatu peristiwa atau semua peristiwa jika `eventName` tidak diberikan.

## 2. **Pola "Observer"**: 

Modul [events](https://nodejs.org/docs/latest-v18.x/api/events.html#events) menerapkan pola "observer" atau "publish-subscribe", di mana objek yang mengamati (pendengar) diberi tahu tentang perubahan dalam objek yang diamati (pemancar/peristiwa). Ketika pemancar memancarkan peristiwa, semua pendengar yang terdaftar untuk peristiwa tersebut akan diaktifkan.

## 3. **Contoh Penggunaan**: 

Anda dapat menggunakannya dalam berbagai konteks, seperti mengelola peristiwa pada kelas, menghubungkan komponen dalam aplikasi yang berbeda, atau merespons tindakan pengguna di antarmuka pengguna. Misalnya, Anda dapat menggunakan [EventEmitter](https://nodejs.org/docs/latest-v18.x/api/events.html#events_eventemitter) untuk mengatur komunikasi antara komponen dalam server web, mengaktifkan peristiwa ketika permintaan datang, atau mengelola aliran data di aplikasi yang berkepanjangan.

Berikut adalah contoh sederhana untuk memberi gambaran tentang bagaimana [EventEmitter](https://nodejs.org/docs/latest-v18.x/api/events.html#events_eventemitter) dapat digunakan:

```javascript
const EventEmitter = require('events');

class MyEmitter extends EventEmitter {}

const myEmitter = new MyEmitter();

// Menambahkan pendengar untuk peristiwa 'customEvent'
myEmitter.on('customEvent', (message) => {
  console.log(`Pesan terdengar: ${message}`);
});

// Memancarkan peristiwa 'customEvent'
myEmitter.emit('customEvent', 'Halo, dunia!');
```

Dalam contoh ini, kita membuat subkelas `MyEmitter` yang mewarisi dari [EventEmitter](https://nodejs.org/docs/latest-v18.x/api/events.html#events_eventemitter). Ini memungkinkan kita untuk menggunakan semua metode [EventEmitter](https://nodejs.org/docs/latest-v18.x/api/events.html#events_eventemitter) dalam instance `myEmitter`. Kemudian kita menambahkan pendengar dan memancarkan peristiwa untuk menunjukkan bagaimana objek [EventEmitter](https://nodejs.org/docs/latest-v18.x/api/events.html#events_eventemitter) menghubungkan komponen dalam pola "event-driven programming".