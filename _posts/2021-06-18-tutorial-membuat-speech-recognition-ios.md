---
title: Tutorial membuat speech recognition di iOS #judul postingan
img:  210618/speech.jpg #gambar postingan taruh di assets/img dan langsung call nama imagenya
layout: post #default jangan diganti
author: Cong Fandi #default me
author-img : congfandi.jpeg #default me
author-detail : iOS Developer, Android Developer, Web Developer # default me
fig-caption: Developer #default me
tags: [Developer, iOS, iPhone]# tags dalam array [Developer, Web, Tips]
---


Hola soabt ngoding dimanapun kalian berada, kita berjumpa lagi dalam sebuah karya sederhana dari anak desa. Sduah lama sekali saya belum mempublikasikan sebuah tulisan karena kesibukan. Oke tanpa berbasa basi, kali ini saya akan sedikit sharing tentang sebuah teknologi yang dimliki oleh Apple sebut saja `Speech Recognition`. Speech recognition ini berbeda ya dengan Sicantik siri yang sudah bisa digunakan secara luas pada platform yang dikeluarkan oleh Apple.

Ok tanpa berbasa bagi yuk kita lanjut ke bagian bagian ngoding dulu.


## Kebutuhan / Prasyarat

Sebelum kalian melanjutkan, ada baiknya kita bahas dulu hal hal yang dibutuhkan untuk membuat tutorial kali ini karena tidak semua platform dapat menjalankan hal ini.


|  Spesifikasi  | Keterangan      |
| :------------ |:---------------:|
| OS            | MacOs           |
| Editor/Tool   | Xcode           |
| Platform      | iPhone/iPhone Simulator |


Spesifikasi diatas hanyalah saran guys, jika kalian ada cara lain masih tetap bisa mengikuti tutorial ini.


## Coding

Pada bagian bakalan sangat seru guys, kita bakalan ngoding dengan menggunakan Xcode dengan mengunakan bahasa Swift.

### Membuat Layout 
pembuatan layout ini akan kita lakukan denga menggunakan storyborad, untuk hasilnya dapat kalian lihat pada gambar diabwah ini. 

Untuk langkah pertama ini silahkan kalian buatlah project terlebih dahulu pada Xcode kailan. dan buka file `Main.storybord`.

*Pastikan buat project default agar nama file bisa sama dengan apa yang akan kita lakukan di profject ini*

![Preferences]({{site.url}}/assets/img/210618/image1.png)

Gambar diatas adalah tampilan projcet secara keseluruhan. Idenya adalah jika kalian ucapkan 1 kata dalam bahasa ingris kita akan mengganti warnanya dengan warna yang kita ucapkan.


## Koneksikan layout yang kita buat dengan controller
![Preferences]({{site.url}}/assets/img/210618/image2.png)

Jika kalian berhasil mengkoneksikan component kalian pada controllerview, kalian dapat melihatnya dengan cara klik kanan pada component yang kalian inginkan dana kan terlihat seperti gambar diatas.



