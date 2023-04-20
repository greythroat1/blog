---
title: "Python Basic 7: String"
date: 2022-09-01T01:35:05+07:00
description: "Mengenal string pada python."
tags: ["python", "tutorial"]
katex: false
mathjax: false
---

Semua tulisan yang diapit oleh tanda petik (' atau ") dikatakan sebagai string. Contoh penulisannya yaitu: 'kata' atau "kata", tetapi tidak boleh digabung antara tanda petik 1 dan tanda petik 2 seperti: 'kata".  

## Merging String

Untuk menggabungkan banyak string, dapat menambahkan tanda tambah (+).

```python
s = "Python is the best language for data science"
t = 'Its very easy to write'
print(s+'and'+t)
print(s+' and '+t)  # Ditaruh spasi agar output memiliki spasi diantara dua string
```  

Selain dengan menambahkan dengan tanda tambah (+), dapat juga menggunakan tanda koma (,).  

Penggabungan dengan cara menggunakan tanda tambah (+) hanya bisa dengan data yang berjenis string, jika data tidak berjenis string (con: integer, float, dsb.) maka harus diubah terlebih dahulu menjadi string. Sedangkan jika menggunakan tanda koma (,) maka tidak perlu mengubah kedalam jenis string.

```python
Harga = 12000
p = "Harga buku ini"
v = p + ' yaitu: '+ str(Harga)  # untuk yang selain jenis string, harus diubah dahulu menjadi string agar bisa digabungkan dengan string lain
print(v)
#atau
print(p, 'yaitu:', Harga)  #jika ditulis dengan tanda koma, maka tidak perlu spasi tambahan karena sudah terotomatis membuat spasi
```

## Multiline String  

Yaitu dengan menggunakan 3 tanda petik diawal dan diakhir.  

```python
multiline1 = """This is the first line of string,
and here is the second line,
and here is the third and final line"""
print(multiline1)
```  

```python
print('''The following options are available:
        -a   : does something
        -b   : does nothing
''')  
```

## Indexing & Slicing  

Indexing yaitu mengakses tulisan yang ada didalam string. Untuk mengaksesnya bisa menggunakan tanda []. Tanda tersebut bisa digunakan untuk semua jenis data struktur seperti tuple, list, string, dict, dll. Index dimulai dari 0 untuk huruf/angka yang pertama.  

```python
a = 'Game of programming'
print(a[0])
print(a[3])
print(a[4])  # karena hasil spasi, maka hasil tidak tampak di output  
```

Index bisa juga diakses dengan jarak tertentu yang dinamakan sebagai slicing. Formatnya: [start:end:step]. Penulisan *start* dimulai dari 0. *end* disini tidak sampai pada baris yang ditujukan. Contohnya jika *end* ditulis pada baris 8, maka hanya akan sampai baris ke-7. *step* yaitu berapa banyak selang perpindahan huruf.

Jika hanya memiliki dua komponen, maka hanya akan terbuat *start* dan *end* saja.

```python
s = "How are you and who are you"
print(s[3:8])
```

Selain dengan angka positif, bisa juga melakukan indexing dan slicing dengan angka negatif/minus. Index dengan negatif/minus dimulai dari -1 

```python
s = "How are you and who are you"
print(s[-1])
print(s[-12:-3])
```

Contoh slicing lainnya:

```python
print(s[0:12:2])
print(s[:12])    # dimulai dari awal hingga baris 11
print(s[3:])     # dari baris 4 sampai akhir
print(s[1:12:])  # step 1
print(s[::-1])   # tulisan akan menjadi invers
```

## Built-in Function pada String  

Terdapat banyak built-in function pada string. Pada kali ini hanya beberapa saja yang dijelaskan.  

Cara penulisan function ini yaitu diawali dengan cara menuliskan string terlebih dahulu atau memberikan variabel (yang telah merujuk pada string), kemudian diikuti oleh function itu sendiri.  

### .strip()  

**.strip()** adalah function untuk menghilangkan spasi diawal dan diakhir  

```python
a = "     abc def     ghi jklmnop    "
b = a.strip()
print(b)
```

### .lower(), .upper() & .capitalize()

- **.lower()** adalah function untuk membuat semua huruf menjadi huruf kecil.  
- **.upper()** adalah function untuk membuat semua huruf menjadi huruf besar.  
- **.capitalize()** adalah function untuk membuat huruf awal menjadi huruf besar (kapital)  

```python
a = "ABC DeFg ;; sadFa qG"
b = a.lower()
c = a.upper()
d = a.capitalize()
print(b)
print(c)
print(d)
```  

### .replace()  

**.replace()** adalah function untuk mengubah suatu tulisan didalam string menjadi tulisan lain.  

```python
a = "ABC DeFg ;; sadFa qG"
x = a.replace("A", "#")
y = a.replace(";;", "two semi colons")
print(x)
print(y)
```  

### .split()  

**.split()** adalah function untuk memisahkan string. Output akan menjadi List.  

```python
k = "abc;def;ghi;sfsa14"
L = k.split(";")
print (L)
```  

Dikarenakan output menjadi list, maka dapat menerapkan perlakuan-perlakuan terhadap list, contohnya seperti mengaksesnya.  

```python
print(L[0])
print(L[2])
```  

## Other Manipulation with String  

### in & not in  

**in** dan **not in** akan mencari apakah suatu tulisan terdapat didalam string tersebut atau tidak. Output akan menghasilkan Boolean (**True** & **False**).  

```python
print("at" in "asfdfatsgk")
```

```python
print("at" not in "asfdsfatgk")
```

### Escape Corrector  

```python
print("We are learning "string" here")
```

Jika ingin hendak menuliskan seperti cara diatas, maka akan menghasilkan error. Oleh karena itu jika ingin memberikan tanda petik didalam string, diberikan *escape corrector* berupa tanda **garis miring terbalik** atau **backlash ( \ )** agar tidak beradu dengan tanda petik yang mengapit string.  

```python
print("We are learning \"string\" here")
```  

Selain dengan cara diatas, dapat juga dengan memberikan tanda petik yang berbeda dengan tanda petik yang mengapit string.

```python
print("We are learning 'string' here")
```  

### New Line

Jika ingin membuat baris baru, maka dapat menggunakan **\n**. Penulisan setelahnya tidak perlu memberikan spasi.  

```python
print("We are \n now on another line")  # Jika menggunakan spasi, maka baris baru akan memiliki spasi
print("We are \nnow on another line")   # Baris baru tidak akan memiliki spasi
```

Khusus pada penulisan path pada Windows, penulisan dengan \n ini akan membuat baris baru kebawah jika penamaan setelah \ memiliki huruf n.  

```python
print("c:\name\drive")  # Output akan menghasilkan baris baru
```  

Untuk menghindarinya, dapat memberikan huruf **r** sebelum penulisan string yang berisi path tersebut.  

```python
print(r"c:\name\drive")
```
