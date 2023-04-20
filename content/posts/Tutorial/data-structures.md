---
title: "Python Basic 8: Data Structures"
date: 2022-09-07T01:35:24+07:00
description: "Mengenal Data structures (list, tuple, set, dan dictionary) pada python"
tags: ["python", "tutorial"]
katex: false
---

Data structures adalah koleksi atau kumpulan dari banyak data. Data tersebut bersifat heterogen yang berarti dapat berjenis integer, string, float, dsb..  

Terdapat 4 jenis Data structures yang umum yaitu : List, Tuple, Set, dan Dictionary.  

Masing-masing memiliki karakteristiknya sendiri. Berikut merupakan karakteristiknya:  

| Data Structures | Ordered or Not? | Mutable or Immutable? | Can Have Duplicates or Not? | Symbol |
|-----------------|-----------------|-----------------------|-------------------------|------------|
| List | Ordered | Mutable (Changeable) | Yes | [] |
| Tuple | Ordered | Immutable (Unchangeable) | Yes | ( ) |
| Set  | Unordered | Immutable, but Addable and Removable | No | { } |
| Dictionary | Unordered | Mutable (Changeable) | No | { } |  

Ordered yaitu elemen (data) mempunyai posisi yang berarti bisa dilakukan index terhadap elemen didalamnya terhadap posisinya.  

Mutable yaitu data structures element-nya bisa diubah, sedangkan immutable tidak.  

Duplicates yaitu didalam data structures bisa terdapat lebih dari satu element/data yang sama.  

```python
L = [1,3,4.9,"name",3]
T = (1,3,4.9,"name",3)
S = {1,3,4.9,"name",3}
D = {23:"twothree",'B':43,'C':'CCD'}

print("The type of L is:", type(L))
print("The type of T is:", type(T))
print("The type of S is:", type(S))
print("The type of D is:", type(D))
```  

## Indexing  (& Duplicates)  

Indexing pada List dan Tuple dilakukan dengan menggunakan tanda [ ], yang didalamnya berisi posisi dari yang mau di-index. Posisi dimulai dari 0.  

Pada Set, tidak bisa dilakukan indexing, hanya bisa mencari apakah terdapat element tertentu didalam set atau tidak.  

Pada Dictionary, hanya bisa mengakses value dengan menulis key-nya.  

```python
print (L[1])    # index data dengan list
print (T[1])    # index data dengan tuple
print (3 in S)  # index data dengan set
print (D[23])   # index data dengan dictionary
print (D["C"])  # index data dengan dictionary
```  

Pada set, dua atau lebih element yang sama hanya ditulis sekali

```python
print(L)
print(T)
print(S)
```  

Dapat dilihat pada output bahwa elemen didalam set tidak akan menampilkan elemen yang sama.  

### Slicing pada List dan Tuple  

Slicing pada list dan tuple sama seperti string. Berikut contohnya:  

```python
L[1:3]
```

```python
L[::-1]
```  

```python
T[:3]
```  

## Mutable & Immutable  

### List  

Menambahkan elemen kedalam list, contohnya:  

```python
L = L + ["how","are",6,"you"]
print(L)
```  

> Output:  

> ```python
> [1, 3, 4.9, 'name', 3, 'how', 'are', 6, 'you']
> ```  

Bisa juga dengan menuliskan *.append*. Syntax tersebut hanya bisa untuk menambahkan satu elemen.  

```python
L.append(6.8)
print(L)
```  
> Output:  

> ```python
> [1, 3, 4.9, 'name', 3, 'how', 'are', 6, 'you', 6.8]
> ```  

Untuk menghapus element, menggunakan *del* diikuti dengan index.  

```python
del L[3]
print (L)
```  

> Output:  

> ```python
> [1, 3, 4.9, 3, 'how', 'are', 6, 'you', 6.8]
> ```  

Bisa juga menghapus list dengan menggunakan *del* diikuti dengan nama variabel dari list tersebut.  

### Tuple  

Tuple tidak bisa ditambah atau dihapus elementnya, tetapi bisa digabungkan dua tuple menjadi tuple baru.  

```python  
T2 = ("A", "b", 90)
T3 = T + T2
print(T3)
```
> Output:  

> ```python
> (1, 3, 4.9, 'name', 3, 'A', 'b', 90)
> ```  

Untuk menghapus tuple dengan menggunakan *del* diikuti dengan nama variabel dari tuple tersebut.  

### Set  

Menambahkan satu elemen kedalam set dengan menuliskan *.add*.  

```python
S.add(56)
print(S)
```  

> Output (bisa jadi urutan berbeda dikarenakan Set bersifat unordered):  

> ```python
> {1, 3, 4.9, 'name', 56}
> ```  

Jika ingin menambahkan banyak elemen, dapat menuliskan *.update*  

```python
S.update({23,"game",3})
print(S)
```  

> Output (bisa jadi urutan berbeda dikarenakan Set bersifat unordered):  

> ```python
> {1, 3, 4.9, 'name', 23, 56, 'game'}
> ```  

Untuk menghapus elemen bisa menggunakan *.remove*.  

```python
S.remove('game')
print(S)
```

> Output (bisa jadi urutan berbeda dikarenakan Set bersifat unordered):  

> ```python
> {1, 3, 4.9, 23, 56, 'name'}
> ```  

Untuk menghapus set dengan menggunakan *del* diikuti dengan nama variabel dari set tersebut.  

### Dictionary  

Menambahkan key dan value kedalam dictionary, berikut contohnya:  

```python
D['New'] = 'newValue'
print(D)
```  

> Outuput:  

> ```python
> {23: 'twothree', 'B': 43, 'C': 'CCD', 'New': 'newValue'}
> ```  

Untuk menghapus elemen bisa menggunakan *del* diikuti dengan key-nya.  

```python
del D['C']
print(D)
```  

> Outuput:  

> ```python
> {23: 'twothree', 'B': 43, 'New': 'newValue'}
> ```  

Jika ingin menggabungkan dua dictionary, bisa menggunakan *.update*.  

```python
D2 = {"y":"Y", "z":10}
D.update(D2)
print (D)
```  

> Outuput:  

> ```python
> {23: 'twothree', 'B': 43, 'New': 'newValue', 'y': 'Y', 'z': 10}
> ```  

## Copy of Data Structures  

Pada data structures list, set dan dictionary, jika suatu variabel sudah terdapat list, set dan dictionary didalamnya dan kita men-assign variabel tersebut ke variabel lain, maka kita sebenarnya **TIDAK** men-copy list, set dan dictionary tersebut kedalam variabel lain. Variabel baru tersebut hanya merujuk kepada variabel lama.  

Berikut contohnya dengan menggunakan list.  

```python
L = [1, 3, 4.9, 3, 'how', 'are', 6, 'you', 6.8]

L2 = L
print ("L2:", L2)

L2[2] = "four point nine"
print ("L2:", L2)
print ("L:", L)
```  

> Output:  

> ```python
> L2: [1, 3, 4.9, 3, 'how', 'are', 6, 'you', 6.8]
> L2: [1, 3, 'four point nine', 3, 'how', 'are', 6, 'you', 6.8]
> L: [1, 3, 'four point nine', 3, 'how', 'are', 6, 'you', 6.8]
> ```  

Dapat dilihat dari output bahwa hasil perubahan *'four point nine'* juga mempengaruhi variabel yang lama yaitu *L*.  

Jika ingin melakukan copy dari variabel satu ke variabel lain, maka dapat menggunakan  *.copy()*  

```python
L2 = L.copy()

L2[2] = 4.9
print ("L2:", L2)
print ("L:", L)
```  

> Output:  

> ```python
> L2: [1, 3, 4.9, 3, 'how', 'are', 6, 'you', 6.8]
> L: [1, 3, 'four point nine', 3, 'how', 'are', 6, 'you', 6.8]
> ```  

Dapat dilihat dari output bahwa hasil perubahan tidak mempengaruhi variabel yang lama.  

Pada data structure tuple, tidak ada fungsi *.copy*. Ini dikarenakan tuple bersifat immutable. Elemen didalam tuple juga tidak bisa dirubah, oleh sebab itu tidak ada fungsi *.copy*. Yang ada hanya bisa men-assign kedalam variabel lain.  

```python
T = (1, 3, 4.9, 'name', 3)

T2 = T
print ("T:", T)
print ("T2:", T2)
```  

### Melakukan copy dengan menggunakan slicing  

Jika menggunakan slicing untuk men-assign pada variabel baru, maka variabel baru tersebut sudah termasuk hasil copy-an baru (sama seperti fungsi *copy* sebelumnya). Jadi jika mengganti element pada variabel baru, maka variabel lama tidak akan berubah elementnya.  

```python
L3 = L[1:5]
print(L3)
```  

> Output:  

> ```python
> [3, 'four point nine', 3, 'how']
> ```

```python
L3[0] = 'Three'

print("L3:", L3)
print("L:", L)
```  

> Output:  

> ```python
> L3: ['Three', 'four point nine', 3, 'how']
> L: [1, 3, 'four point nine', 3, 'how', 'are', 6, 'you', 6.8]
> ```  

## The Abstractness of Data Structures  

Didalam suatu data structures, bisa dimasukkan beberapa data structures lainnya didalam suatu data structures tersebut.  

Berikut contoh dengan menggunakan dictionary:

```python
D2 = {'A':L, 'B':T, 'C':S, 'D':D}
```  

```python  
# Mengakses List pada index ke 2  
D2['A'][3] 
```  

```python
# Mengakses key D  
K = D2['D']
print(K)
```  

```python
# Mengakses key dan value D dengan menggunakan loop  
for x in K:
    print(x,K[x])
```

Berikut contoh dengan menggunakan list:  

```python
L3 = [L,T,D,23,"Game"]
print(type(L3[2]))
```  
