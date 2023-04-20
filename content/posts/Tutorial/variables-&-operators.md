---
title: "Python Basic 1: Variables & Operators"
date: 2022-08-24T01:06:48+07:00
description: "Mengenal variabel dan operator pada python."
tags: ["python", "tutorial"]
---

*Semua penjelasan mengenai `python` basic pada website ini bersumber dari video [freeCodeCamp.org](https://www.youtube.com/watch?v=LHBE6Q9XlzI&list=PLWKjhJtqVAblQe2CCWqV4Zy3LY01Z8aF1&index=3), dan penulis menjalankan pemograman `python` melalui Jupyter.*

Variablel dan operator merupakan hal yang paling basic dalam bahasa pemograman, dimana dengan menggunakan variabel, kita dapat menyimpan suatu data kedalam variabel yang telah ditentukan. Sedangkan operator digunakan untuk menggabungkan atau menghitung dari dua data atau lebih seperti pada operasi matematika.  

## Variables  

Dengan menggunakan variabel, kita dapat menyimpan suatu data. Khusus pada awal ini, kita hanya menggunakan 4 jenis data yang umum terlebih dahulu, yaitu: Integer, Float, Complex dan String.  

- Integer merupakan bilangan real yang tidak memiliki koma  
- Float merupakan bilangan real yang yang memiliki koma
- Complex merupakan bilangan kompleks (Bilangan imajiner atau penggabungan antara bilangan real dan bilangan imajiner)
- String merupakan kumpulan karakter, bisa angka maupun huruf yang nantinya membentuk suatu teks.



Berikut merupakan contohnya:  



```python
x = 4
y = 5.0
xy = 9.98
a = -7
```  



pada data diatas, angka-angka disimpan dengan menggunakan variabel, yaitu x merujuk pada 4, y merujuk pada 5.0, xy merujuk pada 9.98, dan a merujuk pada -7. Data-data tersebut tersimpan dalam variabel, yang mana nanti bisa dipanggil kembali dengan menggunakan perintah **print**.  



```python
print(x)
print(y)
print(xy)
print(a)
```  



Untuk mengetahui jenis-jenis dari variabel yang telah disimpan, dapat menggunakan perintah **print(type())** pada masing-masing variabel yang ingin diketahui jenisnya atau menggunakan perintah **%whos**.  



```python
print(type(x))
print(type(y))
print(type(xy))
print(type(a))
```



ATAU



```python
%whos
```  



Contoh untuk jenis complex dan string:  



```python
c = 4+20j
s = "Hi"
t = "1020"

print(c)
print(s)
print(t)

print(type(c))
print(type(s))
print(type(t))
```  



Dapat dilihat pada variabel t, termasuk jenis string, padahal terdapat angka didalamnya. Angka tersebut berubah menjadi string dikarenakan diapit oleh tanda petik. Maka semua pernyataan yang diapit oleh tanda petik akan menjadi string, tidak peduli seperti apa jenis datanya.  



Untuk menghapus variabel yang telah dijalankan sebelumnya agar tidak tersimpan didalam memory, bisa menggunakan perintah **del**.  



```python
del a
```  



Variabel tidak bisa diawali dengan nomor dan simbol seperti *, &, @, kecuali _ yang diikuti oleh huruf atau angka.



> Variabel sebaiknya dideskripsikan dengan nama yang jelas dan sesuai agar jelas maksud dari variabel tersebut.



## Operators

Operators fungsinya sama seperti operasi pada matematika. Pada `python` terdapat tambahan jenisnya lagi dan ada juga yang berbeda simbol dibandingkan dengan menggunakan operasi matematika biasa. Berikut merupakan jenis-jenis operators:  

| Operators | Description |
| ---- | ---- |
| + | Penambahan |
| - | Pengurangan |
| * | Perkalian |
| / | Pembagian |
| % | Sisa dari angka pembagian yang tidak bisa dibagi |
| // | Pembagian, yang mana angka dibelakang koma tidak diambil |
| ** | Pangkat |  



Berikut merupakan contohnya:  



```python
print(10+6)
```  



Bisa juga dengan menggunakan variabel yang telah ditentukan sebelumnya:



```python
print(x+xy)
```



Contoh lainnya dengan menggunakan variabel baru:



```python
pembagian = xy/y
v = ((x+y)**3)/4

print(pembagian)
print(v)
```  
