---
title: "Cara menambahkan Basemap Layer pada QGIS"
date: 2023-04-26T13:21:12+07:00
description: "Menambahkan basemap layer (ex: Google Maps, Google Satellite, 
Google Terrain, etc.) pada QGIS secara manual dan dengan bantuan plugin."
tags: ["qgis", "tutorial"] 
---

Basemap merupakan layer yang menampilkan peta atau wilayah secara keseluruhan. 
Biasanya dapat berupa batas administrasi, jalan, nama tempat, dsb. Beberapa 
contoh dari basemap ini yaitu Google Maps, Google Satellite, Google Terrain, 
dll.. Terkadang kita memerlukan layer tersebut untuk menunjang pekerjaan yang 
akan dilakukan pada aplikasi GIS. Pada aplikasi QGIS, basemap yang tersedia 
setelah melakukan instalasi hanya OpenStreetMap. Jika ingin menambah basemap 
yang lain, maka terdapat beberapa cara, diantaranya yaitu:  

1. Menambahkan secara manual 
2. Menggunakan plugin   

Berikut cara menambahkan basemap. 

## Menambahkan Secara Manual  

Dengan menambahkan basemap secara manual, terdapat beberapa pilihan, yaitu 
sebagai berikut.  

### Menggunakan XYZ Tiles  

Jika menggunakan cara ini, berarti kita menambahkan basemap secara satu persatu 
dengan memasukkan link basemap yang diinginkan. Berikut link dari beberapa 
service yang dapat digunakan.  


**Google Maps:**  

```
https://mt1.google.com/vt/lyrs=m&x={x}&y={y}&z={z}
```  

**Google Satellite:**  

```
https://mt1.google.com/vt/lyrs=s&x={x}&y={y}&z={z}
```  

**Google Satellite Hybrid:**  

```
https://mt1.google.com/vt/lyrs=y&x={x}&y={y}&z={z}
```  

**Google Terrain:**  

```
https://mt1.google.com/vt/lyrs=t&x={x}&y={y}&z={z}
```  

**Esri World Topo:**  

```
https://services.arcgisonline.com/ArcGIS/rest/services/World_Topo_Map/MapServer/tile/{z}/{y}/{x}
```  

Berikut cara memasukkan link tersebut.  

1. Arahkan mouse ke bagian Browser, pilih XYZ Tiles.  
2. Klik kanan > klik New Connection...  

{{< figure src="/img/QGIS/basemap/XYZ_Tiles-1.png" alt="XYZ Tiles-1" width="240px" >}}  

3. Ketik sesuai dengan layer yang akan dimasukkan, kemudian masukkan link 
ke bagian URL.  

{{< figure src="/img/QGIS/basemap/XYZ_Tiles-2.png" alt="XYZ Tiles-2" width="340px" >}}  

4. Klik OK. Layer akan muncul pada bagian XYZ Tiles.  

> Cara lainnya untuk mengakses XYZ Tiles yaitu pada Layer > Data Source Manager > 
XYZ. Pada XYZ Connection, klik New.  

Jika ingin menambahkan link lainnya, maka dapat mengunjungi 
*https://qms.nextgis.com/* dan memilih menu TMS.  

### Menggunakan Python Script  

Jika ingin menambahkan basemap secara sekaligus, maka dapat menggunakan python 
script. Berikut contoh python script: 
[Python Script](https://raw.githubusercontent.com/klakar/QGIS_resources/master/collections/Geosupportsystem/python/qgis_basemaps.py)  

Berikut merupakan cara memasukkan script tersebut:  

1. Copy text pada link tersebut.  
2. Buka QGIS. Klik pada bagian Plugins > klik Python Console.  

{{< figure src="/img/QGIS/basemap/Python_script-1.png" alt="Python Script-1" width="400px" >}}  

3. Console akan muncul pada bagian bawah, lalu paste semua text pada console.  

{{< figure src="/img/QGIS/basemap/Python_script-2.png" alt="Python Script-2" width="1000px" >}}  

4. Tunggu sesaat. Setelah siap, maka akan muncul text **iface.reloadConnections()**, 
lalu tekan Enter pada keyboard atau tombol Run Command pada console tersebut.  

{{< figure src="/img/QGIS/basemap/Python_script-3.png" alt="Python Script-3" width="1000px" >}}  

5. Restart QGIS. Layer akan muncul pada bagian XYZ Tiles.  

Layer pada script tersebut dapat diedit sesuai diinginkan. Oleh karena itu, 
kelebihan dengan menggunakan script yaitu kita dapat mengontrol atau mengatur 
layer apa saja yang akan dimasukkan pada QGIS dan juga dengan script akan lebih 
mudah untuk mengirim konfigurasi layer yang sama antara satu komputer dengan 
komputer lainnya.  

## Menggunakan Plugin  

Cara lain untuk menambahkan layer yakni dengan menggunakan plugin. Dengan 
adanya plugin, menambahkan basemap menjadi lebih mudah. Terdapat beberapa 
plugin yang digunakan untuk menampilkan basemap, yang dijelaskan disini 
diantaranya yaitu **QuickMapServices** dan **Tile+** 

### Plugin QuickMapServices

Plugin yang sangat popular untuk menambahkan basemap yakni QuickMapServices. 
Berikut merupakan cara mengkonfigurasikannya.

1. Klik pada bagian Plugins > klik Manage and Install Plugins....  

{{< figure src="/img/QGIS/basemap/QuickMapServices-1.png" alt="QuickMapServices-1" width="400px" >}}  

2. klik pada tombol pencarian dan cari QuickMapServices. 
Pastikan yang terpilih yaitu pada bagian All.  

3. Pilih plugin tersebut, lalu klik Install Plugin.  

{{< figure src="/img/QGIS/basemap/QuickMapServices-2.png" alt="QuickMapServices-2" width="460px" >}}  

4. Setelah terinstall, klik Web > QuickMapServices > pilih map yang diinginkan. 

{{< figure src="/img/QGIS/basemap/QuickMapServices-3.png" alt="QuickMapServices-3" width="340px" >}}  

5. Pada instalasi pertama kali, basemap yang tersedia hanya sedikit, maka jika 
ingin mendapatkan layer seperti google satellite, bing map, dsb., maka pada 
QuickMapService dapat memilih Settings > More services > Get contributed pack.  

{{< figure src="/img/QGIS/basemap/QuickMapServices-4.png" alt="QuickMapServices-4" width="360px" >}}  

{{< figure src="/img/QGIS/basemap/QuickMapServices-5.png" alt="QuickMapServices-5" width="360px" >}}  

> Pada plugin QuickMapServices dapat menambahkan basemap secara manual yakni 
pada QuickMapServices > Settings > Add\Edit\Remove lalu dapat menambahkan grup 
atau service(layer) secara manual.  

### Plugin Tile+

Tile+ merupakan plugin yang lebih minimal/simpel yakni tidak memiliki banyak 
pengaturan seperti plugin sebelumnya. Plugin ini hanya dapat memilih peta 
kemudian menampilkannya pada aplikasi. Plugin ini tidak terdapat pada 
repository plugin QGIS, sehingga harus diinstal secara manual. Berikut 
link download plugin [*Tile+*](https://drive.google.com/file/d/1LMAb_SMYHBpZrDhFIkgxUHLE2hNVIirE/view).  

Cara menginstall plugin tersebut yakni sebagai berikut:  

1. Download plugin tersebut dalam format .zip.  
2. Buka QGIS, klik pada bagian Plugins > klik Manage and Install Plugins... > 
klik Install from ZIP.  

{{< figure src="/img/QGIS/basemap/Tileplus-1.png" alt="Tileplus-1" width="460px" >}}  

3. Klik tombol … (titik tiga) kemudian cari file zip yang telah didownload.  
4. Klik Install Plugin.   

{{< figure src="/img/QGIS/basemap/Tileplus-2.png" alt="Tileplus-2" width="200px" >}}  

5. Jika muncul jendela *Security warning*, pilih yes.  

{{< figure src="/img/QGIS/basemap/Tileplus-3.png" alt="Tileplus-3" width="300px" >}}  

6. Maka plugin akan langsung muncul pada bagian toolbar, jika tidak maka dapat 
dilihat pada bagian Plugins.

Terdapat berbagai macam cara dalam menambahkan basemap pada QGIS, terserah pada 
pengguna bagaimana cara untuk memasukkannya pada aplikasi QGIS.

