---
title: Methode Tercepat dalam mencari data terkecil
cover-image: hipster.jpg
---
Bismillah, Halo sobat ngoding.....
Kali ini saya akan bercerita tentang kecepatan sebuah methode dalam mencari data terkecil dari kumpulan data training. Dalam riset ini saya membuat data training dengan menggunakan sebuah object buatan saya sendiri.

Awalnya saya hanya ingin mencari methode terbaik untuk menghitung dan mencari data dari sekumpulan data, tentunya saya memiliki banyak pilihan untuk menggunakan beberapa methode yang ada pada bahasa pemrograman dart. 
<!--more-->

Berikut hasil simulasi dan percobaan yang saya lakukan.

## Simulasi ##

1. Percobaan saya lakukan dengan menggunakan bahasa pemrograman dart

2. Editor yang  digunakan adalah online editor pada web [dartpad](https://dartpad.dev/)

3. Percobaan  dilakukan dengan menggunakan 10 data training

4. *Data yang dicari adalah data yang lebih dari 3 dan kurang dari 8*

5. Percobaan dilakukan dengan menghitung lama sebuah solusi(methode) dieksekusi

6. Percobaan dilakukan sebanyak 100x pada masing masing solusi

## Object Training Dalam bahasa dart ##

```dart
class Data {
  int lat;
  int lang;
  double jarak;

  Data({this.lat, this.jarak, this.lang});

  toJson() {
    return {'lat': lat, 'lang': lang, 'jarak': jarak};
  }
}
```

## Data Training ##

```dart
final dataTrainig = [
  new Data(lat: 1, lang: 1, jarak: 3.45),
  new Data(lat: 2, lang: 2, jarak: 3.20),
  new Data(lat: 3, lang: 3, jarak: 3.50),
  new Data(lat: 4, lang: 4, jarak: 3.30),
  new Data(lat: 5, lang: 5, jarak: 5.10),
  new Data(lat: 6, lang: 6, jarak: 3.90),
  new Data(lat: 7, lang: 7, jarak: 7.0),
  new Data(lat: 8, lang: 8, jarak: 3.15),
  new Data(lat: 9, lang: 9, jarak: 9.0),
  new Data(lat: 10, lang: 10, jarak: 3.0),
];
```

## Solusi ##

Solusi yang diberikan dibedakan berdasarkan jenis-jenis Perulangan(for) yang ada pada bahasa pemrograman dart. Pada penelitian ini, terdapat 4 jenis jenis perulangan(solusi), antara lain : 

1. Solusi 1 

```dart
solusi1() {
  final stopwatch = Stopwatch()..start();
  double jarakTerdekat = double.infinity;
  Data dataTerdekat;
  dataTrainig.forEach((data) {
    if (data.jarak > 3.0 && data.jarak < 8.0) {
      if (data.jarak < jarakTerdekat) {
        jarakTerdekat = data.jarak;
        dataTerdekat = data;
      }
    }
  });
  print('${stopwatch.elapsed.toString().split(':')[2].split('.')[1]}');
  return jarakTerdekat;
}
```

2. Solusi 2

```dart
solusi2() {
   final stopwatch = Stopwatch()..start();
  double jarakTerdekat = double.infinity;
  Data dataTerdekat;
  for (Data data in dataTrainig) {
    if (data.jarak > 3.0 && data.jarak < 8.0) {
      if (data.jarak < jarakTerdekat) {
        jarakTerdekat = data.jarak;
        dataTerdekat = data;
      }
    }
  }
  print('${stopwatch.elapsed.toString().split(':')[2].split('.')[1]}');
  return jarakTerdekat;
}
```

3. Solusi 3

```dart
solusi3() {
   final stopwatch = Stopwatch()..start();
  double jarakTerdekat = double.infinity;
  Data dataTerdekat;
  for (var i = 0; i < dataTrainig.length; i++) {
    var data = dataTrainig[i];
    if (data.jarak > 3.0 && data.jarak < 8.0) {
      if (data.jarak < jarakTerdekat) {
        jarakTerdekat = data.jarak;
        dataTerdekat = data;
      }
    }
  }
  print('${stopwatch.elapsed.toString().split(':')[2].split('.')[1]}');
  return jarakTerdekat;
}
```

4. Solusi 4

```dart
solusi4() {
   final stopwatch = Stopwatch()..start();
  double jarakTerdekat = double.infinity;
  Data dataTerdekat;
  int totalData = dataTrainig.length;
  for (var i = 0; i < totalData; i++) {
    var data = dataTrainig[i];
    if (data.jarak > 3.0 && data.jarak < 8.0) {
      if (data.jarak < jarakTerdekat) {
        jarakTerdekat = data.jarak;
        dataTerdekat = data;
      }
    }
  }
  print('${stopwatch.elapsed.toString().split(':')[2].split('.')[1]}');
  return jarakTerdekat;
}
```

## Methode Execution ##

```dart
void main() {
 
  for(var i=0;i<100;i++){
   solusi1(); 
  }
}
```

## Hasil ##

Hasil (Waktu dalam satuan millisecond(ms))
![Hasil Time](https://github.com/congfandi/riset/blob/master/Pencarian%20data%20terkecil%20.png?raw=true)

Hasil (Total WAktu)
![Total WAktu](https://github.com/congfandi/riset/blob/master/chart.png?raw=true)


Tabel Hasil

|Percobaan Ke|Solusi 4|	Solusi 3|	Solusi 2|	Solusi 1|
|:----------:|:------:|:-------:|:---------:|:---------:|
|1	|25	|21|	3|0	|50|
|2	|15	|20|	1|5	|50|
|3	|9	|0	|5	|45|
|4	|5	|0	|5	|26|
|5	|0	|5	|4	|41|
|6	|0	|0	|5	|10|
|7	|0	|0	|5	|15|
|8	|5	|0	|0	|10|
|9	|0	|0	|0	|10|
|10|	0|	0|	0|	9|
|11	|5	|0	|0	|10|
|12|	0|	0|	0|	6|
|13	|0	|5	|4	|15|
|14	|5	|5	|5	|10|
|15	|5	|5	|0	|11|
|16	|0	|0	|0	|10|
|17|	6|	4|	0|	4|
|18|	0|	6|	5|	5|
|19	|0	|0	|0	|10|
|20|	0|	0|	0|	9|
|21|	0|	0|	5|	5|
|22	|0	|0	|0	|10|
|23	|5	|5	|0	|10|
|24	|0	|5	|0	|10|
|25	|0	|0	|4	|10|
|26	|0	|0	|5	|11|
|27	|4	|0	|0	|19|
|28	|4	|0	|6	|15|
|29|	0|	0|	0|	9|
|30|	0|	0|	5|	5|
|31	|6	|6	|4	|15|
|32	|0	|0	|0	|10|
|33|	5|	5|	5|	9|
|34|	5|	0|	0|	5|
|35	|0	|4	|0	|16|
|36	|5	|0	|5	|15|
|37	|0	|5	|0	|15|
|38	|0	|6	|0	|15|
|39	|0	|0	|0	|40|
|40	|0	|5	|5	|16|
|41	|5	|0	|5	|15|
|42	|5	|0	|0	|25|
|43	|0	|0	|0	|16|
|44|	0|	0|	0|	4|
|45	|0	|5	|0	|10|
|46	|4	|5	|0	|10|
|47|	0|	5|	0|	5|
|48|	5|	0|	0|	5|
|49|	0|	0|	6|	0|
|50	|5	|0	|0	|11|
|51	|0	|5	|0	|10|
|52|	0|	0|	5|	9|
|53|	0|	0|	5|	0|
|54|	5|	5|	5|	5|
|55|	5|	0|	0|	6|
|56|	0|	0|	5|	5|
|57|	0|	0|	4|	5|
|58|	0|	4|	5|	5|
|59|	5|	5|	0|	6|
|60	|5	|0	|0	|24|
|61|	0|	0|	0|	5|
|62	|0	|0	|0	|10|
|63|	0|	0|	0|	5|
|64|	0|	0|	0|	5|
|65|	5|	4|	0|	5|
|66|	5|	0|	5|	5|
|67	|0	|0	|0	|10|
|68|	6|	0|	0|	5|
|69|	6|	0|	0|	5|
|70|	0|	0|	0|	5|
|71	|5	|0	|5	|10|
|72|	0|	0|	4|	5|
|73|	0|	5|	5|	4|
|74|	0|	5|	0|	0|
|75|	5|	5|	0|	4|
|76|	0|	5|	0|	5|
|77|	5|	5|	5|	5|
|78|	0|	5|	0|	5|
|79|	5|	0|	0|	5|
|80|	0|	5|	0|	5|
|81|	5|	0|	0|	4|
|82	|5	|4	|0	|10|
|83|	0|	5|	0|	4|
|84	|4	|10|	0|	6|
|85	|0	|4	|0	|10|
|86|	0|	0|	0|	0|
|87|	0|	0|	5|	5|
|88|	0|	0|	0|	5|
|89	|0	|0	|5	|11|
|90|	0|	4|	5|	5|
|91|	0|	0|	0|	5|
|92|	6|	0|	0|	4|
|93	|0	|4	|0	|10|
|94|	0|	0|	0|	5|
|95|	0|	0|	0|	5|
|96|	5|	5|	0|	5|
|97|	0|	0|	5|	5|
|98	|0	|0	|0	|10|
|99|	0|	5|	0|	5|
|100|	0|	5|	6|	0|


## Kesimpulan ##

**Dari hasil percobaan yang dialukan dapat diambil kesimpulan bahwa methode tercepat diperoleh oleh methode pada solusi nomer 2 dengan total waktu yang dibutuhkan pada 100x percobaan adalah 12.9 persen dan metode terlama adalah pada solusi ke 1 dimana total waktu yg dibutuhkan pada 100 percobaan adalah 60.1 persen.**

## Source Code ##
Source Code dapat dilihat pada link [Github](https://github.com/congfandi/riset)
>Penulis bukan orang yang paling mampu, hanya ingin berbagi saja. Semoga dapat mengambil manfaat<small> - Penulis</small>