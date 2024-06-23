---
title: "[WINDOWS] Instalasi WebODM"
date: 2024-06-22T21:18:36+07:00
description: "Menginstall WebODM pada Windows dengan menggunakan Docker"
tags: ["webodm", "opendronemap", "tutorial"]
---

{{< figure src="/img/WebODM/Windows/WebODM_Logo.png" >}}  

WebODM merupakan aplikasi Fotogrametri open source yang gratis dan juga berbayar. 
Yang membedakan antara gratis dan berbayar hanya dari cara instalasinya saja 
dan cara updatenya, untuk fitur 100% sama. Namun untuk menggunakannya secara 
gratis, memerlukan setup yang sedikit lebih ruwet dibanding dengan yang berbayar 
yang mana lebih mudah untuk diinstal.
Berikut merupakan syarat dan cara menginstal WebODM dengan cara manual (gratis) 
sistem operasi Windows.  

# Sistem minimum perangkat:  
- 64bit CPU (yang keluar setelah tahun 2010).  
- 20 GB Disk (Ruang Penyimpanan).  
- 4 GB RAM.  

Dalam melakukan proses pengolahan foto, yang paling penting yaitu processor, 
jumlah RAM dan Disk yang tersedia. Semakin kencang processor, maka proses 
pengolahan akan semakin kencang dan semakin banyak jumlah RAM dan Disk, 
maka semakin banyak foto yang bisa diproses. Berikut jumlah RAM yang diperlukan 
terhadap jumlah foto yang diolah. 

| **Jumlah Foto** | **Jumlah RAM / RAM + SWAP (GB)** |
| ----- | -----|
| 40 | 4 |
| 250 | 16 |
| 500 | 32 |
| 1500 | 64 |
| 2500 | 128 |
| 3500 | 192 |
| 5000 | 256 |
  
# Instalasi  

## Prerequisites:  

Sebelum menginstall WebODM, harus menginstall:  
1. Docker Desktop.  
2. Git.  

### Install Docker Desktop  

1. Download [Docker Desktop](https://docs.docker.com/desktop/install/windows-install/). 
Pilih yang x86-64.  
2. Install Docker Desktop. Saat instalasi, kita diminta untuk membuat akun. 
Jika tidak ingin membuat akun, maka bisa pilih Continue without signing in.  
3. Setelah selesai, maka diminta untuk restart.  
4. Docker sudah siap untuk digunakan.  

#### Optional Setting  

Paka kondisi default, docker sudah otomatis mengatur jumlah resources yang 
akan digunakannya. Secara default, docker mengakses:  
- Seluruh **DISK (RUANG PENYIMPANAN)** perangkat.  
- Seluruh jumlah **PROCESSOR** perangkat.  
- 80% dari total **RAM** perangkat.  
- 25% dari total RAM untuk **SWAP**. (**SWAP** merupakan memory yang digunakan dari disk, bukan RAM).  

Khusus untuk Windows, jika ingin mengatur resources sesuai keinginan kita, 
maka bisa dilakukan dengan membuat file `.wslconfig` yaitu sebagai berikut.  

1. Quit Docker Desktop. Bisa diakses pada Icon Tray di kanan bawah dengan 
cara mengklik kanan icon Docker lalu pilih Quit Docker Desktop atau 
dengan mengklik tombol Shutdown dibagian kiri bawah Docker.  
{{< figure src="/img/WebODM/Windows/Docker_Config_1.png" >}}  
2. Pada File Explorer, klik bagian directory lalu ketik **%UserProfile%** 
untuk menuju ke user profile kita.  
{{< figure src="/img/WebODM/Windows/Docker_Config_2.png" >}}  
3. Buat file baru (dengan Text Document) dengan nama `.wslconfig` (pastikan tidak ada .txt diujungnya).  
{{< figure src="/img/WebODM/Windows/Docker_Config_3.png" >}}  
{{< figure src="/img/WebODM/Windows/Docker_Config_4.png" >}}  
4. Setelah terbuat, buka file tersebut dengan Notepad.  
{{< figure src="/img/WebODM/Windows/Docker_Config_5.png" >}}  
5. Isi file tersebut dengan command berikut:  

```code
# Setting untuk menggunakan WSL 2
[wsl2]

# Setting memory (RAM) yang akan digunakan untuk docker
memory=4GB

# Setting jumlah core porcessor yang akan digunakan untuk docker 
processors=4

# Setting untuk mengatur SWAP memory untuk docker
swap=2GB
```

{{< figure src="/img/WebODM/Windows/Docker_Config_6.png" >}}  

Pada command tersebut, bisa diatur berapa jumlah resources yang akan 
dipakai untuk docker nantinya. Jumlah resources bergantung pada spesifikasi 
perangkat yang digunakan.  
* Untuk Ram disarankan untuk menyisakan sekitar 3 GB untuk windows. 
Maka jika anda memiliki ram sebesar 16 GB, yang kita isi 
di file tersebut yaitu memory=13GB.  
* Untuk porcessor bisa menggunakan jumlah core sepenuhnya atau setengahnya 
(50% dari jumlah core processor).  
* Untuk SWAP dapat menggunakan 2 hingga 8 GB.  

6. Setelah selesai, Save file tersebut dengan Ctrl+S dan tutup file tersebut.  
7. Setelahnya anda sudah siap untuk menggunakan docker.  

### Install Git  

Setelah selesai menginstall docker, maka kita harus menginstall Git.  

1. Download [Git](https://git-scm.com/downloads), pilih Windows.  
2. Pilih versi Standalone Installer 64-bit.  
3. Install Git (Saat instalasi bisa klik next sampai akhir).  

## Install WebODM  

Setelah selesai menginstall git dan docker, kita bisa menginstall WebODM. 
Caranya yaitu:  

1. Pastikan Docker Desktop berjalan di latar belakang dengan cara membuka 
Docker Desktop terlebih dahulu.  
2. Buka Git Bash.  
3. Copy command berikut:  

```bash
git clone https://github.com/OpenDroneMap/WebODM --config core.autocrlf=input --depth 1
cd WebODM
./webodm.sh start 
```
{{< figure src="/img/WebODM/Windows/Instalasi_WebODM_1.png" >}}  
4. Lalu tekan Enter. WebODM akan mendownload dan menginstall secara langsung ke perangkat.  
{{< figure src="/img/WebODM/Windows/Instalasi_WebODM_2.png" >}}  
5. Setelah diinstall, WebODM bisa dibuka di browser dengan mengetik 
`http://localhost:8000`. Nantinya akan diminta untuk membuat username dan password. 
Masukkan sesuai yang diinginkan.  
{{< figure src="/img/WebODM/Windows/Instalasi_WebODM_3.png" >}}  
6. Untuk keluar dari WebODM, pada Git Bash ketik Ctrl+C. Lalu tutup Docker Desktop 
dengan cara klik tombol Shutdown dibagian bawah kiri Docker.  
{{< figure src="/img/WebODM/Windows/WebODM_5.png" >}}  

# Menggunakan WebODM (Basic)  

Setelah menghidupkan perangkat. Ada beberapa langkah untuk menggunakan WebODM.  

1. Untuk menggunakan WebODM, pastikan Docker Desktop telah terbuka dan WebODM 
telah berjalan di latar belakang. Untuk mengetahui hal tersebut, pada Containers 
pastikan webodm telah Running pada bagian Status. Jika belum, aktifkan dengan 
menekan tombol Start pada bagian Actions.  
{{< figure src="/img/WebODM/Windows/WebODM_1.png" >}}  
2. Buka Browser, ketik `http://localhost:8000`.  
3. Buat project baru pada bagian Add Project. Nantinya akan diminta untuk mengisi 
nama dan deskripsi project.  
4. Masukkan foto yang akan diolah pada bagian Select Images and GCP.  
5. Setelah selesai mengolah, pada bagian Download Assets kita bisa mendownload 
file yang diperlukan.  
{{< figure src="/img/WebODM/Windows/WebODM_2.png" >}}  
6. Untuk menampilkan secara langsung, bisa memilih View Map. Pada menu tersebut 
kita juga bisa mendownload file foto (Orthophoto, DSM, Kontur, dsb) di bagian 
kanan atas.  
{{< figure src="/img/WebODM/Windows/WebODM_3.png" >}}  
7. Untuk menampilkan secara 3D, bisa memilih View 3D Model. Di menu tersebut, 
kita bisa menghitung luas, volume, dsb. yang diinginkan.  
8. Untuk menutup WebODM, hapus tab WebODM pada browser dan buka Docker lalu 
klik tombol Stop pada bagian Actions.  
{{< figure src="/img/WebODM/Windows/WebODM_4.png" >}}  
9. Tutup Docker dengan mengklik tombol Shutdown dibagian kiri bawah Docker 
atau pada Icon Tray di kanan bawah.  
{{< figure src="/img/WebODM/Windows/WebODM_5.png" >}}  

# Update WebODM

1. Buka Docker Desktop.  
2. Buka Git Bash, ketik command berikut:  

```bash
cd WebODM
./webodm.sh update
```

3. Tekan enter, maka WebODM akan mengupdate.  
{{< figure src="/img/WebODM/Windows/Update_WebODM.png" alt="Update" >}}  
4. Setelah selesai diupdate, ketik `./webodm.sh start`, lalu tekan Enter.  


# Saran  

1. Saat mengolah foto udara di WebODM, tutup semua aplikasi yang tidak 
berhubungan dengan WebODM (con: tab browser selain WebODM, music app, office, dsb). 
Ini dilakukan agar docker bisa menggunakan RAM secara maksimal.  
2. Saat melakukan proses pengolahan foto udara, sebaiknya perangkat tidak 
digunakan agar tidak membebani proses pengolahan.  
3. Setelah memasukkan foto udara pada WebODM, kita bisa mengatur output 
dan/atau proses yang kita inginkan pada menu options. Pada menu edit, kita 
bisa lebih banyak lagi mengatur option tersebut. Untuk penjelasan mengenai 
fungsi-fungsi menu atau command tersebut, dapat diakses pada laman:
https://docs.opendronemap.org/arguments/.  
{{< figure src="/img/WebODM/Windows/Option_Menu.png" alt="Option_Menu" >}}  
4. Bagi yang menggunakan emulator android untuk berbagai hal 
(seperti bermain game android, develop aplikasi android, dsb) seperti 
Bluestack, LDPlayer, dsb. maka diperlukan untuk menonaktifkan WSL pada 
windows agar aplikasi tersebut dapat berjalan. 
Caranya yaitu ketik Windows Features pada tombol Search > matikan Windows 
Subsystem for Linux > klik OK. Nanti akan diminta untuk merestart perangkat. 
Jika ingin menggunakan Docker kembali, maka wajib mengaktifkan WSL.  

# Referensi  

https://github.com/OpenDroneMap/WebODM/  
https://docs.opendronemap.org/  
https://github.com/codeedu/wsl2-docker-quickstart/blob/main/README.en.md  
