---
title: "Python Basic 6: Function"
date: 2022-08-29T01:34:52+07:00
description: "Mengenal function pada python."
tags: ["python", "tutorial"]
katex: false
mathjax: false
---

Function adalah perintah untuk menyimpan suatu argumen, yang nantinya dapat digunakan kembali argumen tersebut ketika diinginkan.  

Kegunaan dari function ini yaitu kita dapat menyimpan argumen atau rumus yang sangat panjang kedalam function tersebut, sehingga nantinya jika ingin menggunakan argumen atau rumus tersebut kembali, kita dapat memanggil function tersebut, tidak perlu membuat kode berulang-ulang kali.  

Function memiliki kata kunci **def** yang berarti define.  


## Basic  

Cara penulisan function yaitu menuliskan **def** terlebih dahulu, diikuti oleh nama dari function tersebut dan diakhiri oleh tanda kurung. Penamaan function bebas, akan tetapi lebih baik jika nama function dapat mendefinisikan maksud dari isi function.

```python
def printSuccess():
    print("Tugas telah selesai")
    print("Tolong kirimkan tugas yang lain")
```  

Ketika kode tersebut telah dijalankan, maka kita dapat kembali memanggil isi dari kode tersebut dengan mengetik nama function-nya saja.  

```python
printSuccess()
```

Maka output akan menghasilkan argumen yang telah disimpan/diisi kedalam function tersebut

> Output:

> ```python
> Tugas telah selesai
> Tolong kirimkan tugas yang lain
> ```

### Doc string  

Function yang telah dibuat dapat dijelaskan agar lebih mudah dipahami. Cara menjelaskannya yaitu dengan menggunakan doc string. Doc string ini sifatnya opsional, yakni boleh dilakukan maupun tidak. Tetapi dengan adanya doc string, kita dapat memberikan deskripsi secara detail terhadap apa maksud atau tujuan dari function yang telah dibuat.  

Penulisan doc string dilakukan sebelum membuat argumen kedalam function. Caranya yaitu dengan meletakkan tiga tanda petik diawal penjelasan dan diakhir penjelasan.

Untuk mengetahui function yang telah dibuat, dapat menggunakan tanda tanya di belakang function tersebut atau menggunakan help.  

```python
def printHello():
    """Function ini memberikan pesan, yang mana pesan tersebut yaitu 'Hello' """
    print("Hello")  
```

```python
printHello?
```

Jika ingin mengetahui kembali apa argumen yang telah ditulis sebelumnya, maka dapat menggunakan dua tanda tanya.  

```python
printHello??
```

## Input Argument 

Apabila ingin argumen didalam function bisa diubah-ubah sesuai yang diinginkan, maka dapat menggunakan input argument.  

Input argument pada function ini dapat dilakukan dengan memberikan huruf atau kata didalam kurung sesudah nama function. Kemudian argumen dari function tersebut harus memiliki huruf atau kata yang sama.  

```python
def printMsg(msg):
    """Function ini menjelaskan suatu input yang mana merupakan jenis string, yang mana bukan"""
    if isinstance (msg, str):
        print("Ini merupakan string :", msg)
    else:
        print("Argumen yang dimasukkan bukan string")
        print("Ini merupakan tipe argumen yang anda masukkan:", type(msg))
```

```python
printMsg("Mouse")
```  

```python
printMsg(90)
```

Dapat diketahui dari output bahwa argumen yang terdapat didalam tanda kurung akan mempengaruhi argumen dari function tersebut.  

Selain ditulis langsung, dapat juga memberikan variabel yang merujuk kepada suatu jenis data.  

```python
y = "Keyboard"
printMsg(y)
```  

### Input argument lebih dari 1

Input argumen ini juga dapat menggunakan lebih dari 1 argument. Jika jumlah argumen yang diinput tidak sesuai, maka akan menghasilkan error  

```python
def rumusGaya(m,a):
    """Function ini merupakan rumus dari gaya"""
    Gaya = m*a
    print("F =", Gaya)

rumusGaya(20, 13)
```  

> Output:

> ```python
> F = 260
> ```  

```python
def checkArgs(a,b,c):
    if isinstance(a, (int,float)) and isinstance(b, (int,float)) and isinstance(c, (int,float)):
        print ((a+b)*c)
    else:
        print("Error: salah satu argumen atau lebih bukan merupakan jenis integer ataupun float ")
```

```python
checkArgs(2,3,5)
```

```python
checkArgs(2,3,"g")
```

```python
checkArgs(2,3)  # jumlah argumen tidak sesuai sehingga akan menghasilkan error
```

### Urutan pada input argument

Urutan sangat berpengaruh dalam function. Jika ingin lebih spesifik, dapat memberikan variabel beserta input yang dimasukkan pada function ketika function ingin dijalankan.  

Maka dari itu, sebaiknya dalam membuat function harus diperhatikan urutannya agar tidak membingungkan ketika menjalankan kode tersebut (urutan pada arugumen pada function harus sesuai dengan apa yang di print didalamnya).  

```python
def f(c2,c1,c3):
    print(c1,c2,c3)

f(1,2,3)
```
> Output:

> ```python
> 2 1 3
> ```

Dapat dilihat dari output bahwa hasil tidak berurutan.

```python
f(c1 = 1, c2 = 2, c3 = 3) 
```

> Output:

> ```python
> 1 2 3
> ```

Dengan memberikan variabel secara spesifik, hasil akan menjadi berurutan.  


## Variable Scope  

Didalam function, suatu variabel dapat terbaca atau tidak tergantung dari peletakan variabelnya. Variable scope terbagi menjadi dua jenis, yaitu:
- Local : hanya terletak didalam function 
- Global : terletak diluar function.  

Jika variabel berada di dalam function (local), maka variabel hanya dapat diketahui oleh function tersebut saja. Jika variabel berada di luar function, maka variabel dapat diketahui oleh function dan yang diluar dari function.  

```python
a = 5
def f():
    a = 2
    print(a)

f()  
print(a)
```  

Dari output, didapatkan hasil 2 dengan menjalankan function tersebut dikarenakan yang diprioritaskan adalah variabel didalam function walaupun terdapat variabel yang sama (yaitu *a = 5*) diluar function. Sedangkan saat melakukan *print(a)*, maka hasil yang didapat adalah 5 karena variabel *a* didalam function tidak bisa terbaca selain oleh function itu sendiri. Maka dari itu ia akan membaca variabel *a* yang berada diluarnya yakni 5.  

```python
b = 91
def g():
    print(b)

g()
print(b)
```  

Walaupun didalam function tidak terdapat variabel *b*, hasil masih bisa didapatkan yaitu 91. Ini dikarenakan variabel *b* yang bersifat Global sehingga dapat dibaca oleh function.  

```python
def h():
    c = 11
    print (c)
    
h()
print(c)
```

Pada kode tersebut, perintah *h()* dapat berjalan dikarenakan terdapat variabel *c* didalam function, tetapi perintah *print(c)* tidak berjalan (error) dikarenakan variabel *c* hanya terdapat didalam function tersebut.


## *return* Statement  

Statement ini fungsinya yaitu untuk mengubah Local scope variable (variabel didalam function) menjadi Global scope variable (diluar function).  

Dengan kata lain, jika ingin menggunakan variabel yang terdapat didalam function menjadi variabel yang dapat digunakan diluar function, maka dapat menggunakan **return** statement didalam function tersebut.  


Jika ingin menggunakan kembali hasil return pada function untuk digunakan pada waktu kedepannya, maka harus membuat variabel terlebih dahulu yang merujuk terhadap function, kemudian variabel yang merujuk kepada function di *print*. Tetapi, jika hanya sekali saja memanggil kode tersebut, dapat langsung memanggil function seperti biasa.

Hasil yang di return akan menghasilkan jenis data (con: list, integer, float, dll). Yang telah di *print* didalam function tidak termasuk kedalam jenis data (tidak bertipe apa-apa).  

```python
def penjumlahan(a,b):
    sumValue = a+b
    return sumValue

y = penjumlahan(2,5)   # memberikan variabel terhadap function
print(y)
print(type(y))
```  

Output dari function tersebut akan berjenis integer.  

Jika hanya ingin menjalankan kode tersebut sekali saja, dengan kata lain tidak ingin menyimpannya kedalam variabel, dapat langsung memanggil function seperti biasa.

```python
penjumlahan(2,5)
```

Statement **return** juga berfungsi seperti **break** pada iteration.  

```python
def h():
    print("A")
    a = 3
    b = 5
    c = a*b
    print("B")
    return
    print("C")
    print("D")  

h()
```  

> Output: 

> ```python
> A
> B
> ```  

Dari output, dapat dilihat bahwa function tidak menjalankan *print("C)* dan *print("D")*.  

Jika didalam function tersebut terdapat variabel (disini yaitu variabel *a*, *b*, dan *c*), untuk mengeluarkannya dapat menentukan variabel didepan statement return.  

```python
def h():
    print("A")
    a = 3
    b = 5
    c = a*b
    print("B")
    return c        # Memberikan variabel didepan statement return
    print("C")
    print("D")  

h()
```  

Masih menggunakan kode diatas, jika function tersebut dicari tau jenisnya (dengan *print(type(h()))*), maka akan menghasilkan jenis data. Sedangakan yang telah di *print* didalam function tidak termasuk kedalam jenis data.  

> Output dari perintah *print(type(h()))*:  

> ```python
> A                 # Tidak tampak jenisnya dikarenakan telah di print di dalam function
> B                 # Tidak tampak jenisnya dikarenakan telah di print di dalam function
> <class 'int'>     # Berjenis Integer dikarenakan telah di return oleh function dan tidak di print didalam function  
>```

Contoh lain:

```python
def r():
    a = 5
    b = 6
    d = "Something"
    return a,b,d

x,y,z = r()
print (x,y,z)
print(type(x))
print(type(y))
print(type(z))
print(type(r))
```


## Variable Number of Input Argument  

Jika ingin menambahkan argumen sebanyak yang diinginkan maka dapat menggunakan tanda * pada function. Data yang dimasukkan akan bertindak sebagai jenis List.  

```python
def add(*args):
    sum = 0
    for i in range (len(args)):
        sum+=args[i]
    return sum

add(5,6,7)
add(10,1,33,12,90,21)
```

Jika ingin menambahkan angka dengan variabel tertentu, maka dapat menggunakan tanda **.

```python
def printAllVariableNamesAndValues(**Var):
    for x in Var:
        print("Nama variabel :",x , "dan Nilainya :", Var[x])

printAllVariableNamesAndValues(a = 3, b = "CCC", c = 6.90, d = 50)
```

## Default Value  

Yaitu nilai bawaan (default) yang telah ditentukan jika tidak memasukkan nilai kedalam function yang telah ada.  

```python
def dv(s = 20):
    print(s)

dv()
```  

> Output:

> ```python
> 20
> ```


Jika nilai dimasukkan saat memanggil function, maka nilai akan berubah (tidak lagi mengambil dari nilai bawaan).

```python
dv(510)
dv("Test")
```

> Output:

> ```python
> 510
> Test
> ```

Contoh lain:  

```python
def gg(L = [2,3]):
    for i in L:
        print(i)

gg()
```

Dengan memberikan nilai yang berbeda:

```python
L2 = [12,22,31,42,56]
gg(L2)
```
