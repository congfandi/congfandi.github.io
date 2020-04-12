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

5. Solusi 5

```dart
solusi5(double jarakTerdekat, int index, Data dataTerdekat) {
  final stopwatch = Stopwatch()..start();
  if (index < dataTrainig.length - 1) {
    if (jarakTerdekat > dataTrainig[index].jarak) {
      jarakTerdekat = dataTrainig[index].jarak;
      dataTerdekat = dataTrainig[index];
      index++;
      solusi5(jarakTerdekat, index, dataTerdekat);
    } else {
      index++;
      solusi5(jarakTerdekat, index, dataTerdekat);
    }
  } else {
    print('${stopwatch.elapsed.toString().split(':')[2].split('.')[1]}');
  }
  return jarakTerdekat;
}
```

## Methode Execution ##

```dart
void main() {
 
  for(var i=0;i<100;i++){
//     solusi1();
//     solusi2();
//     solusi3();
//     solusi4();
//     solusi5(double.infinity,0,new Data()); 
  }
}

```

## Hasil ##

Hasil (Waktu dalam satuan millisecond(ms))
![Hasil Time](https://github.com/congfandi/riset/blob/master/Diagram%20Pencarian%20Data%20Terkecil%20dengan%205%20methode.png?raw=true)

Hasil (Total WAktu)
![Total WAktu](https://github.com/congfandi/riset/blob/master/Screen%20Shot%202020-04-12%20at%2010.58.48.png?raw=true)


Tabel Hasil

|Percobaan Ke|	Methode 1	|Methode 2	|Methode 3	|Methode 4	|Methode 5|
|:----------:|:----------:|:---------:|:---------:|:---------:|:-------:|
|1	|45|20|20|19|0|
|2	|31|10|20|15|0|
|3	|30|9	|10|4|0|
|4	|20|5	|4|	5 |0|
|5	|30|5	|5|	5 |0|
|6	|15|5	|5|	0	|0|
|7	|15|0	|5|	5	|4|
|8	|10|5	|5|	0	|0|
|9	|10|5	|0|	5	|0|
|10	|5|	5	|6|	5	|0|
|11	|11|5	|0|	0	|0|
|12	|10|5	|5|	0	|0|
|13	|10|5	|5|	0	|5|
|14	|5|	0	|5|	0	|0|
|15	|10|0	|5|	0	|0|
|16	|5|	5	|0|	5	|0|
|17	|9|	5	|0|	0	|0|
|18	|5|	5	|5|	0	|0|
|19	|15|0	|5|	5	|0|
|20	|10|10|	5|0	|0|
|21	|20|5	|0|	5	|5|
|22	|15|0	|5|	0	|0|
|23	|5|	0	|0|	0	|0|
|24	|10|4	|0|	0	|0|
|25	|6|	5	|5|	0	|5|
|26	|5|	0	|0|	5	|0|
|27	|5|	0	|0|	5	|0|
|28	|5|	0	|0|	0	|0|
|29	|5|	0	|0|	5	|5|
|30	|4|	0	|5|	0	|0|
|31	|10|5	|0|	0	|0|
|32	|5|	0	|5|	0	|0|
|33	|5|	0	|0|	0	|0|
|34	|10|0	|5|	0	|0|
|35	|5|	0	|5|	0	|0|
|36	|5|	0	|0|	5	|0|
|37	|5|	0	|5|	0	|0|
|38	|10|5	|0|	0	|0|
|39	|5|	0	|5|	0	|0|
|40	|5|	0	|0|	5	|0|
|41	|10|0	|5|	0	|0|
|42	|5|	0	|5|	0	|0|
|43	|4|	0	|0|	5	|0|
|44	|6|	0	|6|	0	|0|
|45	|5|	0	|5|	0	|0|
|46	|10|0	|0|	0	|0|
|47	|5|	0	|0|	5	|0|
|48	|5|	0	|5|	11|	0|
|49	|5|	5	|5|	15|	0|
|50	|10|0|	0|	0	|0|
|51	|5|	0	|0|	0	|0|
|52	|4|	5	|0|	0	|0|
|53	|5|	0	|0|	5	|0|
|54	|10|0	|5|	0	|0|
|55	|6|	0	|6|	0	|0|
|56	|10|0	|	5|	0	|0|
|57	|5|	5	|0|	0	|0|
|58	|6|	0	|5|	4	|0|
|59	|5|	0	|0|	0	|0|
|60	|10|5	|	0|	0	|0|
|61	|10|0|	0|	0	|0|
|62	|5|	0	|5|	0	|0|
|63	|10|0 |	4| 5 |0|
|64	|5|	0	|5|	5	|0|
|65	|5|	0	|0|	0	|0|
|66	|5|	0	|5|	0	|0|
|67	|10|0	|6|	5	|0|
|68	|9|	5	|0|	0	|0|
|69	|10|	0|0| 0|0|
|70	|10|	0|0| 0|0|
|71	|20|	6|0|	0|0|
|72	|10|0	|	0|	0	|0|
|73	|5|	0	|5|	0	|0|
|74	|10|0	|0|	5	|0|
|75	|5|	0	|0|	0	|0|
|76	|15|0	|5|	0	|0|
|77	|0|	0	|5|	0	|0|
|78	|5|	0	|4|	0	|0|
|79	|5|	0	|5|	4	|0|
|80	|5|	5	|0|	0	|0|
|81	|6|	0	|5|	0	|0|
|82	|5|	5	|5|	0	|0|
|83	|10|0	|5|	4	|0|
|84	|5|	5	|0|	5	|0|
|85	|10|0	|0|	5	|0|
|86	|5|	5	|0|	5	|0|
|87	|10|0	|5|	5	|5|
|88	|5|	0	|0|	0	|0|
|89	|9|	0	|0|	0	|0|
|90	|5|	0	|0|	0	|0|
|91	|5|	5	|0|	5	|0|
|92	|6|	0	|5|	5	|0|
|93	|5|	0	|5|	0	|0|
|94	|10|0	|5|	0	|6|
|95	|10|0	|0|	5	|0|
|96	|15|0	|4|	0	|0|
|97	|10|5	|0|	0	|0|
|98	|10|0	|0|	0	|0|
|99	|10|6	|5|	0	|4|
|100|	0|5	|5|	6	|0|

## Kesimpulan ##

**Dari hasil percobaan yang dialukan dapat diambil kesimpulan bahwa methode tercepat diperoleh oleh methode pada solusi nomer 5 dengan total waktu rata-rata yang dibutuhkan untuk 100x percobaan adalah 2.4 persen dan metode terlama adalah pada solusi ke 1 dimana total waktu yg dibutuhkan pada 100 percobaan adalah 53.7 persen.**

## Source Code ##
Source Code dapat dilihat pada link [Github](https://github.com/congfandi/riset)
>Penulis bukan orang yang paling mampu, hanya ingin berbagi saja. Semoga dapat mengambil manfaat<small> - Penulis</small>