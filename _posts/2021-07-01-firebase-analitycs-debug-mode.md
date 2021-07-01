---
title: Firebase analytics debuging mode #judul postingan
img:  210701/banner.png #gambar postingan taruh di assets/img dan langsung call nama imagenya
layout: post #default jangan diganti
author: Cong Fandi #default me
author-img : congfandi.jpeg #default me
author-detail : iOS Developer, Android Developer, Web Developer # default me
fig-caption: Developer #default me
tags: [Developer, iOS, iPhone, Firebase]# tags dalam array [Developer, Web, Tips]
---

Halo sobat ngoding yang budiman, kali ini saya ingin berbagi tentang cara membuka debuging mode pada firebase analytics. Kenapa butuh debuging mode? karena saat developer mengimplementasikan firebase analytics kedalam aplikasi berupa mobile dan web, hasilnya tidak dapat dilihat secara langsung saat itu juga harus menunggu setidaknya seharian paling sedikit. Oelh sebab itu maka lahirlah sebiah metode yang disebut *DebugView* pada firebase console sehingga developer dapat melihat hasil dari implementasi firebase analytics.

Hasil dapat dilihat pada gambar dibawah ini :
![Firebase]({{site.url}}/assets/img/210701/firebase.png)

 Oke kita langsung saja pada tutorial.

## Langkah langkah

1. Kalian wajib buat dulu project kalian di [fierbase console](https://www.console.firebase.google.com)