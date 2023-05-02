---
title: "Georeference pada QGIS"
date: 2023-05-01T15:48:01+07:00
description: Memasukkan data raster kedalam QGIS sesuai dengan koordinat.
tags: ["qgis", "tutorial"]
---

Georeference adalah proses memasukkan data raster atau vektor ke dalam aplikasi 
yang telah terproyeksi terhadap CRS (Coordinate Reference System) agar data 
tersebut dapat ditampilkan sesuai dengan koordinat yang sebenarnya. Katakanlah 
kita mempunyai peta namun ingin memasukkannya kedalam aplikasi dengan tujuan 
sekedar untuk memperoleh informasi seperti koordinat atau diolah lebih lanjut 
seperti menambahkan data vektor, maka untuk memasukkan peta tersebut diperlukan 
proses georeference. Jadi dengan kata lain, georeference yaitu memasukkan data 
agar sesuai dengan lokasi atau koordinat yang sebenarnya.  

Agar bisa melakukan georeference, aplikasi GIS memerlukan GCP (Ground Control 
Point) berupa koordinat. Biasanya pada peta, koordinat telah tercantum pada 
masing-masing ujung petanya. Namun bagi yang tidak memiliki data koordinat, 
data juga dapat dimasukkan dengan menggunakan data lainnya yakni data 
raster atau vektor yang telah terproyeksi sesuai CRS.  

Berikut cara melakukan georeference berupa data raster pada aplikasi QGIS.  

> Tutorial dilakukan pada QGIS ver. 3.28.5-Firenze. Dan sebagai contoh, disini 
> hanya memasukkan data berjenis raster karena proses georeference lebih sering 
> digunakan untuk memasukkan data raster, untuk data vektor caranya kurang 
> lebih sama.  

## Georeference pada data yang memiliki koordinat  

Pada data raster yang memiliki koordinat, maka dapat menggunakan koordinat yang 
telah tercantum. Berikut memasukkan data raster tersebut.  

1. Sebelum melakukan georeference, buat terlebih dahulu folder baru, lalu data 
raster diletakkan didalam folder tersebut.  
2. Buka QGIS, klik pada bagian layer > klik Georeferencer....  
{{< figure src="/img/QGIS/georeference/Georeference1_1.png" alt="Georeference1-1" width="300px" >}}  
3. Pada jendela Georeferencer, klik Open Raster... dan pilih data raster yang 
ingin dimasukkan.  
{{< figure src="/img/QGIS/georeference/Georeference1_2.png" alt="Georeference1-2" width="200px" >}}  
4. Arahkan pada posisi yang memiliki koordinat, lalu klik titik/daerah tersebut. 
Akan muncul jendela memasukkan koordinat.  
{{< figure src="/img/QGIS/georeference/Georeference1_3.png" alt="Georeference1-3" width="900px" >}}  
5. Pada jendela tersebut, terdapat koordinat X dan Y yang berupa East dan North 
serta CRS. Isi X dan Y tersebut sesuai dengan koordinat yang ditentukan pada 
peta. Pada gambar diatas, tertulis 112°30'BT *(E)* dan 0°00, yang berarti X 
adalah 112°30'dan Y adalah 0°00. Penulisan derajat (°), menit (') dan detik 
(") tidak perlu ditulis, hanya dipisah dengan spasi saja. Lalu isi CRS tersebut 
dengan EPSG:4326 - WGS 84.  
{{< figure src="/img/QGIS/georeference/Georeference1_4.png" alt="Georeference1-4" width="900px" >}}  
Semakin banyak koordinat yang dimasukkan maka data akan semakin akurat.  
Setelah selesai menambahkan koordinat, pada bagian bawah kiri, terdapat Mean error 
yang menyatakan seberapa besar keakuratan titik-titik yang telah diletakkan 
sebelumnya. Semakin rendah nilainya, maka semakin akurat terhadap koordinat 
yang sebenarnya.  
{{< figure src="/img/QGIS/georeference/Georeference1_5.png" alt="Georeference1-5" width="150px" >}}  
**Catatan:**  
Karena pada kotak dialog tersebut hanya ditampilkan East dan North, 
jika koordinat yang ditampilkan adalah West dan South, harus ditambahkan tanda 
minus (-) sebelum penulisan angka. Sebagai contoh:  
| Koordinat | Penulisan |
|   ---     |   ---     |
| 112°30' *(E)* | 112 30 |
| 90°00' *(W)* | -90 00 |
| 2°15' *(N)* | 2 15 |
| 1°30' *(S)* | -1 30|  
6. Setelah itu, klik Transformation Settings....  
{{< figure src="/img/QGIS/georeference/Georeference1_6.png" alt="Georeference1-6" width="300px" >}}  
7. Pada jendela Transformation Settings, beberapa yang wajib diisi yaitu: 
Target CRS dan Output file.  
Target CRS yaitu target proyeksi dari peta yang akan dimasukkan. Biasanya telah 
dicantumkan informasi tersebut pada peta, tetapi ada juga yang tidak. Jika 
tidak, maka kita harus mencari tahu informasi dari peta yang akan kita masukkan. 
Salah satunya dari wilayah peta tersebut, lalu mencari tahu wilayah tersebut 
masuk kedalam proyeksi CRS yang mana.  
Output file yaitu untuk menyimpan data raster yang telah terproyeksi.  
{{< figure src="/img/QGIS/georeference/Georeference1_7.png" alt="Georeference1-7" width="350px" >}}  
8. Setelah siap mengatur pengaturan tersebut, klik Start Georeferencing. Peta 
akan muncul pada layer QGIS sesuai dengan koordinat aslinya.  
{{< figure src="/img/QGIS/georeference/Georeference1_8.png" alt="Georeference1-8" width="300px" >}}  

## Georeference pada data raster yang tidak memiliki koordinat  

Jika data raster tidak memiliki data koordinat, maka kita harus mempunyai data 
lainnya yang memiliki koordinat atau yang telah terproyeksi. Berikut cara 
memasukkan data raster tersebut.  

1. Karena data tidak memiliki koordinat, maka diperlukan data lain yang 
memiliki proyeksi yang tepat. Disini saya memakai layer Google Satellite 
sebagai acuannya. Lalu pilih proyeksi CRS di ujung bawah kanan sesuai dengan 
data raster yang ingin dimasukkan.  
{{< figure src="/img/QGIS/georeference/Georeference2_1.png" alt="Georeference2-1" width="500px" >}}  
2. Masuk ke Layer > Georeferencer... > Open Raser .... , pilih data raster yang 
ingin dimasukkan. Berikut contoh raster yang dimasukkan pada tutorial ini.  
{{< figure src="/img/QGIS/georeference/Georeference2_21.png" alt="Georeference2-21" width="500px" >}}  
3. Setelahnya, pilih posisi yang diinginkan. Cara memilih posisi yang 
baik dalam kondisi ini yaitu memilih posisi pada objek yang tidak mungkin 
bergeser atau bergerak dalam waktu yang lama. Contohnya seperti ujung atap 
bangunan, perempatan atau belokan jalan, menara atau tugu, dsb....  
{{< figure src="/img/QGIS/georeference/Georeference2_2.png" alt="Georeference2-2" width="500px" >}}  
4. Setelah memilih posisi koordinat, akan muncul jendela untuk memasukkan 
koordinat, karena kita tidak memiliki koordinat, maka pilih From Map Canvas, 
ini berfungsi memilih posisi dari data raster kedua yakni Google Satellite.  
{{< figure src="/img/QGIS/georeference/Georeference2_3.png" alt="Georeference2-3" width="500px" >}}  
5. Pilih posisi yang sama pada layer kedua (Google Satellite).   
{{< figure src="/img/QGIS/georeference/Georeference2_4.png" alt="Georeference2-4" width="500px" >}}  
6. Setelahnya, kembali pada jendela koordinat sebelumnya lalu klik OK.  
{{< figure src="/img/QGIS/georeference/Georeference2_5.png" alt="Georeference2-5" width="500px" >}}  
7. Lakukan langkah 3-6 untuk koordinat lain. Semakin banyak koordinat maka 
data akan semakin akurat.  
{{< figure src="/img/QGIS/georeference/Georeference2_6.png" alt="Georeference2-6" width="900px" >}}  
8. Setelah selesai memasukkan koordinat, klik Transformation Settings lalu 
Target CRS dan Output file.  
{{< figure src="/img/QGIS/georeference/Georeference2_7.png" alt="Georeference2-7" width="400px" >}}  
9. Klik Start Georeferencing. Peta akan muncul pada layer QGIS sesuai dengan 
koordinat aslinya.  
{{< figure src="/img/QGIS/georeference/Georeference2_81.png" alt="Georeference2-81" width="700px" >}}  

## Kesimpulan  

Data raster dan vektor dapat dimasukkan kedalam GIS dengan melakukan proses 
Georeference. Data yang akan dimasukkan harus memiliki koordinat, jika tidak 
ada maka dapat menggunakan data lain yang terproyeksi. Beberapa hal penting 
pada georeference ini yaitu:  

- Pada kondisi dimana data memiliki koordinat, jika koordinat yang tercantum 
adalah West dan South, harus menambahkan tanda minus (-) sebelum penulisan angka 
tersebut.  
- Pada kondisi data tidak memiliki koordinat, dapat mengambil posisi/titik yang 
jelas kenampakannya pada kedua data dan memastikan posisi tersebut tetap 
(statis) dalam jangka waktu yang lama, seperti ujung atap bangunan, perempatan 
atau belokan jalan, menara atau tugu, dsb..  
- Mengetahui proyeksi CRS data yang akan dimasukkan.  

