---
title: Info Gempa - Membuat Model
cover-image: hipster.jpg
---

Pada pembahasan kali ini kita akan membahas bagaimana cara mmebuat model pada pemrograman `Swift` dengan menggunakan framework `SwiftUI`.
<!--more-->

## Daftar Isi ##

[Daftar Isi](https://thengoding.com/2019/12/16/daftar-isi-aplikasi-info-gempa-ios/)


## Spesifikasi APlikasi ##

|  Spesifikasi  | Keterangan      |
| :------------ |:---------------:|
|  Bahasa       | Swift 5         |
| Framework     | SwiftUI         |
| Editor/Tool   | Xcode 11.3      |
| Platform      | IOS             | 


Model yang akan kita buat adalah sesuai dengan yang dibutuhkan oleh aplikasi dan menyesuaikan dengan `JSON`  yang di dapat dari [API GEMPA](https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/2.5_day.geojson).
Berikut data yang kita butuhkan untuk membuat aplikasi info gempa ini

## Kebutuhan Aplikasi ##

|      Nama      |      Tipe Data      |       Keterangan        |  
| :--------------| :------------------:|:------------------------|
| mag            | Double              | Informasi kekuatan gempa|
| place          | String              | informasi tempat gempat |
| time           | Double              | informasi waktu gempa   |
| detail         | String              | URL detail gempa        |
| title          | String              | Informasi gempa         |
| type           | String              | Tipe Gempa              |
| coordinates    | List<Double>        | Lat Long gempat (Peta)  |


## Format JSON API ##

```json
    {
        "type": "Feature",
        "properties": {
            "mag": 4.3,
            "place": "291km N of Ndoi Island, Fiji",
            "time": 1577425336477,
            "updated": 1577426822040,
            "tz": -720,
            "url": "https://earthquake.usgs.gov/earthquakes/eventpage/us70006rfs",
            "detail": "https://earthquake.usgs.gov/earthquakes/feed/v1.0/detail/us70006rfs.geojson",
            "felt": null,
            "cdi": null,
            "mmi": null,
            "alert": null,
            "status": "reviewed",
            "tsunami": 0,
            "sig": 284,
            "net": "us",
            "code": "70006rfs",
            "ids": ",us70006rfs,",
            "sources": ",us,",
            "types": ",geoserve,origin,phase-data,",
            "nst": null,
            "dmin": 3.389,
            "rms": 0.85,
            "gap": 74,
            "magType": "mb",
            "type": "earthquake",
            "title": "M 4.3 - 291km N of Ndoi Island, Fiji"
        },
            "geometry": {
            "type": "Point",
            "coordinates": [
                            -178.4009,
                            -18.0347,
                            570.2
                ]
        },
        "id": "us70006rfs"
    }
```

## langkah - Langkah ##








>Penulis bukan orang yang paling mampu, hanya ingin berbagi saja. Semoga dapat mengambil manfaat<small> - Penulis</small>