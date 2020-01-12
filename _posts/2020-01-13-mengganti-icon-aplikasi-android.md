---
title: Mengganti Icon Aplikasi Android
cover-image: hipster.jpg
---

Pada pembahasan kali ini, kita akan mensimulasikan bagaimana caranya mengganti icon aplikasi di andriod studio project.
<!--more-->

Terdapat bebagai macam cara yang bisa kita lakukan, namun disini penulis akan membagikan cara penulis dalam mengganti app icon dengan mudah dan gampang, serta langsung menjadi beberapa bagian ukuran layar.

## Langkah - langkah manual##

1. Buat File icon teman-teman dengan ukuran 36x36, 48x48, 72x72, 96x96, 144x144 and 192x192

2. Pada bagian `src/res` buat folder tambahan dengan nama `drawable-hdpi` , `drawable-mdpi` , `drawable-xhdpi`, `drawable-xxhdpi` dan `drawable-xxxhdpi`

3. Masukan file icon yang sudah dibuat dengan formasi seperti dibawah ini

   36x36 masukan ke folder `drawable`

   48x48 masukan ke folder `drawable-mdpi`

   72x72 masukan ke folder `drawable-hdpi`

   96x96 masukan ke folder `drawable-xhdpi`

   144x144 masukan ke folder `drawable-xxhdpi`

   192x192 masukan ke folder `drawable-xxxhdpi` 

4. Terakhir, panggil nama icon teman-teman pada bagian `AndroidManifest.xml`

   ```manifest
         <application
                android:name="MyName"
                android:label="MyApp"
                android:icon="@drawable/icon_baru_saya">
                .....
                </application>
   ```

## Langkah - langkah dengan `Batch Drawable Inporter` ##

dengan menggunakan `batch drawable importer` kita tidak perlu membuat banyak file, cukup dengan sekali klik maka secara otomatis icon aplikasi kita menjadi 5 bagian dengan folder masing masing, caranya adalah sebagai berikut :

1. Buat Icon nya dengan ukuran salah satu ukuran  192x192

2. Install Plugin pada Android Studio dengan nama `Android Drawable Importer`
   
3. Restart Android Studio

4. Klik kanan pada folder `res/drawable`, kemudian pilih `New`
   
5. Setelah itu pilih `Batch Drawable Importer`
   
6. 
   
7. Pilih Icon yang sudah dibuat,kemudian klik oke
   
8. Icon sudah menjadi beberapa bagian 
   
9.  Masukan nama icon teman-teman ke `AndroidManifest.xml` aplikasi pada bagian ini
   
   ```manifest
         <application
                android:name="MyName"
                android:label="MyApp"
                android:icon="@drawable/icon_baru_saya">
                .....
                </application>
   ```
   
11. Jalankan aplikasinya seharusnya icon aplikasi teman teman sudah berubah menjadi seperti yang teman teman buat.



Sekian tutorial kali ini, sampai jumpa di tutorial berikutnya :-) ....








>Usaha itu bukan segalanya, karena dibalik kesuksesan pasti ada doa yang dipanjatkan<small> - Penulis</small>