---
title: Info Gempa - Perpindahan Halaman
cover-image: hipster.jpg
---

Pada tutorial kali ini, kita akan mensimulasikan perpindahan halaman antar tampilan di `SwiftUI`
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


## langkah - Langkah ##

1. Buka File `ContentView.swift`
   
2. Ganti codenya menjadi seperti dibawah ini

    ```swift
            import SwiftUI

            struct ContentView: View {
                var body: some View {
                    NavigationView{
                        List{
                            ForEach(0...10,id: \.self){ index in
                                NavigationLink(destination: Text("Next Page")){
                                    ItemList()
                                }.navigationBarTitle("Info Gempa")
                            }
                        }
                    }
                }
            }

            struct ContentView_Previews: PreviewProvider {
                static var previews: some View {
                    ContentView()
                }
            }
    ```

3. Silahkan coba aplikasinya, harusnya sudah dapat di klik



>Penulis bukan orang yang paling mampu, hanya ingin berbagi saja. Semoga dapat mengambil manfaat<small> - Penulis</small>