---
title: Mengganti Icon Aplikasi Android
cover-image: hipster.jpg
---

Pada pembahasan kali ini, kita akan mensimulasikan bagaimana caranya mengganti icon aplikasi di andriod studio project.
<!--more-->

Terdapat bebagai macam cara yang bisa kita lakukan, namun disini penulis akan membagikan cara penulis dalam mengganti app icon dengan mudah dan gampang, serta langsung menjadi beberapa bagian ukuran layar.

## Langkah - langkah ##

1. Buat Icon nya dengan ukuran salah satu ukuran  ini 36x36, 48x48, 72x72, 96x96, 144x144 and 192x192


2. Install Plugin pada Android Studio dengan nama `Android Drawable Importer`
   
3. Restart Android Studio

4. Klik kanan pada folder `res/drawable`, kemudian pilih `New`
   
5. Setelah itu pilih `Batch Drawable Importer`
   
6. Pilih Icon yang sudah dibuat,kemudian klik oke
   
7. Icon sudah menjadi beberapa bagian 
   
8. Masukan nama icon teman-teman ke manifest aplikasi pada bagian ini
   
   ```manifest
         <application
                android:name="MyName"
                android:label="MyApp"
                android:icon="@drawable/icon_baru_saya">
                .....
                </application>
   ```
   
9. Jalankan aplikasinya seharusnya icon aplikasi teman teman sudah berubah menjadi seperti yang teman teman buat.



Sekian tutorial kali ini, sampai jumpa di tutorial berikutnya :-) ....








>Usaha itu bukan segalanya, karena dibalik kesuksesan pasti ada doa yang dipanjatkan<small> - Penulis</small>