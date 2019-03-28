Bismillah, 

Tutorial kali ini khusus untuk teman-teman Universitas Muhammadiyah Gresik (UMG) yang mengadakan Event Tahunan **HRC**. Event ini diselengarakan oleh Himatif UMG dengan kerja sama dengan GresikDev.

Pada tutorial ini, kita akan mencoba membuat sebuah aplikasi bank makanan (Foodbank) dimana Mockup dari aplikasi ini dapat dilihat [disini](https://www.behance.net/gallery/67347541/FoodBank-Restaurant-App-UI-Kit).

Oke kita mulai saja tutorialnya.

**Tutorial Membuat Foodbank**
1. Buat aplikasi dengan menggunakan **Android Studio**
2. Atur project seperti gambar 1
   ![Gambar 1](/../img/foodbank1/gambar1.png)
   _Gambar 1_

   saya sangat menyarankan teman-teman utntuk mengatur aplikasi seperti yang ada pada gambar 1.0 agar tidak terjadi error yang tidak di inginkan, jika ingin membuat yang berbeda silahkan tapi lakukan hal itu diluar kelas ya .
3. Setelah project selesai dibuat, Buatlah beberapa folder yang ada didalam `id.gresikdev.foodbank`  antara lain **models** , **views**, **controllers** seperti gambar 2
![Gambar 2](/../img/foodbank1/gambar2.png)
    _Gambar 2_

4. Masih didalam folder(istilah lainnya *package*) `id.gresikdev.foodbank` kita pindahkan file `MainActivity` kedalam *package* **views** kemudian buat beberapa *Activity* `LoginActivity`, `RegisterActivity`, `SplashActivity` dan `WelcomeActivity` dengan cara : Klik kanan pada *package* **views** => **New** => **Activity** => **Empty Activity**.
Struktur file dapat dilihat pada gambar 3.
![Gambar 3](/../img/foodbank1/gambar3.png)

5. Jalankan aplikasi, maka aplikasi akan terlihat seperti gambar 4 
   ![Gambar 4](/../img/foodbank1/gambar4.png).
6. 