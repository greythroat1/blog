---
title: "Python Basic 2: Boolean & Comparisons"
date: 2022-08-25T01:28:05+07:00
description: "Mengenal boolean dan comparisons pada python."
tags: ["python", "tutorial"]
---

Boolean menyatakan kebenaran dari suatu data, bisa berupa **True** dan **False**. Boolean ini sangat erat hubungannya dengan comparisons. Dengan adanya perbandingan menggunakan comparisons, data akan menjadi **True** ataupun **False**.

## Boolean
Terdapat 3 jenis penghubung utama dari Boolean ini yaitu:  

- **and** ; jika 2 objek True, maka output akan True. Selain itu akan False
- **or** ; jika 2 objek False, maka output akan False. Selain itu akan True
- **not( )** ; merupakan kebalikan dari output yang dihasilkan (True menjadi False dan sebaliknya)  

```python
a = True
b = True
c = False
d = False

%whos
```  

Jika di run akan menghasilkan type/jenis data dari variabel-variabel tersebut (bisa juga menggunakan **type()**).  

Kemudian kita bisa membandingkan antara kedua jenis atau lebih variabel dengan menggunakan ketiga penghubung.  

Contoh dengan menggunakan **and**:

```python
print (a and b)
print (a and c)
print (c and b)
print (c and d)
```

> Output:

> ```python
> True
> False
> False
> False
> ```

Dilihat pada hasil dengan menggunakan **and**, penggabungan antara True dan True akan selalu menghasilkan True. Sedangkan penggabungan antara True dan False atau False dan False akan selalu menghasilkan False.  

Contoh dengan menggunakan **or**:

```python
print(a or b)
print(a or c)
print(c or b)
print(c or d)
```

> Output:

> ```python
> True
> True
> True
> False
> ```

Dilihat pada hasil dengan menggunakan **or**, penggabungan antara True dan True serta True dan False, akan selalu menghasilkan True. Sedangkan penggabungan antara False dan False akan selalu menghasilkan False.  

Penggunaan **not()** akan menghasilkan kebalikan dari jenis bool yang telah diketahui/didapat. Jika awalnya True maka akan menjadi False, dan jika awalnya False maka akan menjadi True.  

```python
print(not(a))
print(not(d))
```  

Contoh dari penggabungan ketiganya:

```python
print(not((a and d) or (c or d)))
```  

| Jenis Penghubung Boolean |Penggabungan | Hasil |
| :---: | :---: | :---: |
| And | True x True | True |
| And    | True x False | False |
| And   | False x False | False |
| Or  | True x True | True |
| Or  | True x False | True |
| Or  | False x False | False |

## Comparisons  
Setiap comparisons akan berjenis bool, maka hasil dari comparisons akan menghasilkan **True** atau **False**. Berikut merupakan jenis-jenis comparisons:  

| Symbol | Task |
| :---:    | --- |
| ==     | True, jika sama dengan |
| !=     | True, jika tidak sama dengan |
| <      | kurang dari |
| >      | lebih dari |
| <=     | kurang sama dengan |
| >=     | lebih sama dengan |  

```python
print(2<3)
print(3==4)
print(3==3.0)
```  

Comparison ini bisa juga digabungkan dengan jenis penghubung boolean sebelumnya. Contohnya:  

```python
x = 4
y = 9
z = 8.4
r = -3

print((x<y) and (z<y) or (r==x))
```

Penggunaan **and** dan **or** jika dibuat bersamaan akan mendahulukan **and** walaupun dalam penulisan dibuat **or** terlebih dahulu.  

```python
print(False and False or True)
```  

> Output:

> ```python
> True
> ```  

Dengan penggunaan **or** terlebih dahulu:

```python
print(True or False and False)
```  

> Output:

> ```python
> True
> ```  

Dari hasil diatas, seharusnya output menjadi False. Tetapi dikarenakan yang dibaca terlebih dahulu adalah **and** dan **or** terakhir, maka output akan menjadi True.  

Jika ingin menggunakan **or** terlebih dahulu, dapat menggunakan tanda kurung pada bagian **or**.  

```python
print((True or False) and False)
```

> Output:  

> ```python
> False
> ```
