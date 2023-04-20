---
title: "Python Basic 3: Built in Function"
date: 2022-08-26T01:33:30+07:00
description: "Penggunaan beberapa jenis built in function pada python."
tags: ["python", "tutorial"]
---

Terdapat banyak jenis function yang telah tertanam pada `python` itu sendiri. Kegunaan function ini yaitu kita dapat mengatur atau memerintahkan kode yang telah dibuat menjadi lebih spesifik. Dengan adanya function ini juga, akan memudahkan pembuatan kode yang ingin dibuat nantinya.  

Dalam tutorial ini, hanya beberapa jenis saja yang dijelaskan.  

## **round( )**   
**round( )** adalah function yang digunakan pada angka untuk pembulatan terdekat (bisa keatas maupun kebawah)  

```python
print (round(5.6391))
```

Jika ingin mengambil beberapa angka dibelakang koma, dapat menulis jumlah angkanya dengan tanda koma setelah angka yang ingin dicari.

```python
# angka setelah koma merupakan pembulatan yang diinginkan berapa dibelakang koma
print (round(11.198713, 3))
```

> Output:

> ```python
> 11.199
> ```  

## **divmod(x,y)**  
**divmod(x,y)** adalah function untuk pembagian yang outputnya akan menghasilkan **hasil pembagian** dan **sisa dari pembagian**. x merupakan pembilang dan y merupakan penyebut.  

Sisa dari pembagian yang dimaksud bukan sisa hasil, tetapi sisa dari angka yang tidak bisa dibagi. Output akan berjenis tuple (untuk tuple akan dipelajari pada tutorial selanjutnya).  

Fungsi divmod ini sama seperti penggabungan antara operator **//** dan operator **%**  

```python
divmod (27,5)
```  

> Output:

> ```python
> (5, 2)
> ```

Output/hasil akan berjenis tuple.

```python
b = divmod(34,9)
print (type(b))
print (b)
```  

> Output:

> ```python
> <class 'tuple'>
> (3, 7)
> ```

## **isinstance( )**  
**isinstance( )** adalah function untuk menentukan apakah objek termasuk jenis data tertentu. Output akan menghasilkan **True** ataupun **False**.  
Jika salah satu jenis data terpenuhi, maka tetap akan menghasilkan output **True**.

```python
print(isinstance(1, int))
```  

```python
print(isinstance(1.0, int))
```

```python
a = isinstance(2.0, (int, float, complex))  # akan menghasilkan True karena salah satu jenis data terpenuhi
b = isinstance(40+9j, (int, str))
print(a)
print(b)
```  

## **pow(x,y,z)**  
**pow(x,y,z)** adalah function untuk menghasilkan pangkat dari suatu angka.  

Function ini sama seperti operator biasa yaitu ** , tetapi terdapat tambahan yaitu z yang fungsinya sama seperti operator %.  
Maka dapat dirumuskan **pow(x,y,z)** = x ** y % z  

```python
pow(2,4)
```  

```python
pow(2,4,6)
```  

## **input( )**  
**input( )** merupakan function interactive yang mana untuk memasukkan input, dapat dilakukan setelah kode di run. Objek yang dimasukkan bebas kedalam input tersebut. Objek yang dihasilkan selalu berjenis ***string***. Jadi walaupun memasukkan angka, maka angka tersebut akan diubah kedalam bentuk string.

Jika ingin data yang diinput berjenis integer, float, dsb. maka perlu diubah terlebih. Perubahan bisa dilakukan di akhir setelah mendapatkan hasil, maupun di awal dalam pembuatan code. Jika diawal, maka semua objek yang dimasukkan akan diubah sesuai dengan yang ditentukan.  

```python
a = input("Enter a number :")
```

*nb: Tanda petik berupa data string, hanya untuk menjelaskan kode yang akan dijalankan nanti.*

Maka, output akan selalu berjenis string.

```python
type(a)
```

> Output:

> ```python:
> str
> ```

Untuk mengubahnya dapat dilakukan setelah kode dijalankan atau pada saat awal pembuatan kode.

```python
# Merubah jenis data dengan yang diinginkan dari kode yang telah dibuat sebelumnya, mis: integer
a = int(a)
type(a)
```  

> Output:

> ```python:
> int
> ```  

```python
# Merubah jenis data dengan yang diinginkan pada awal pembuatan kode, mis: float
x = float(input("Masukkan angka:"))
```  

Maka, output akan selalu berjenis float.

```python
type(x)
```

> Output:

> ```python:
> float
> ```

Untuk jenis-jenis Built-in Function lainnya dapat dilihat pada [Link](https://docs.python.org/3/library/functions.html)  

Pada `python` itu sendiri, bisa juga mengetahui kegunaan dan bagaimana cara memakai dari masing-masing Built-in Function, yaitu dengan menuliskan tanda tanya atau help.  

```python
abs?
```

Atau

```python
help(abs)
```
