---
title: "Python Basic 4: Condition Statement"
date: 2022-08-26T01:34:05+07:00
description: "Mengenal conditional statement (if, else, dan elif) pada python."
tags: ["python", "tutorial"]
---

Condition statement merupakan pernyataan untuk menyatakan suatu keputusan, dimana jika suatu kondisi terpenuhi (bersifat **True**), maka kode akan dijalankan, jika tidak (bersifat **False**) maka akan diabaikan.  

Prinsip kerjanya yaitu jika suatu kondisi awal **False**, maka akan dilanjutkan ke kondisi selanjutnya, dan jika tetap **False**, akan dilanjutkan lagi ke kondisi selanjutnya, sampai menemukan kondisi **True**. Jika tidak ditemukan sama sekali kondisi **True**, maka output tidak akan mengeluarkan apa-apa (hanya blank) atau bahkan bisa error.  

Condition statement ditulis dengan **if**, **else**, dan **elif**.

## **if** Statement  

```python
a = int(input("Variabel a :"))
b = int(input("Variabel b :"))
if b > a:
    print("b lebih besar dari a")
print("Diluar dari if statement")
```  

Setelah kode dijalankan, jika user memasukkan nilai b lebih besar daripada a, yang mana kondisi terpenuhi (bersifat **True**), maka akan mengeluarkan output "b lebih besar dari a". Sebaliknya, jika user memasukkan nilai a lebih besar daripada b, maka tidak akan mengeluarkan output apa-apa, dikarenakan kondisi tidak terpenuhi (bersifat **False**).  

Dari kode tersebut, setelah dijalankan baik statement yang bersifat **True** maupun **False** pasti mengeluarkan output "Diluar dari if statement". Ini dikarenakan pernyataan tersebut tidak termasuk kedalam if statement. Mengapa? karena indentasinya (spasi) yang berbeda. Oleh karena itu dalam penulisan Condition, Loop, dan Function harus sangat memerhatikan indentasi.


## **else** Statement  

Jika menginginkan suatu statement yang berbeda maka dapat menggunakan **else**. Dengan kata lain, jika tidak memenuhi kondisi pertama, maka dapat menggunakan **else** untuk memenuhi kondisi lain.  

```python
a = int(input("Variabel a :"))
b = int(input("Variabel b :"))
if b > a:
    print("b lebih besar dari a")
else:
    print("a lebih besar dari b")
```

Penulisan **else** tidak perlu menjelaskan kondisi yang diinginkan. Oleh karena itu setelah **else** bisa langsung diikuti oleh titik dua.

## **elif** Statement  

**elif** merupakan kepanjangan dari **else** dan **if**. Statement **elif** ini digunakan jika kondisi lebih dari dua dan terletak di antara **if** dan **else**.

```python
n = int(input("Masukkan Nilai: "))
if n >= 85:
    print("Nilai = A")
elif (n < 85) and (n >= 80):       # Dapat menambahkan tanda kurung agar mudah dibaca
    print("Nilai = A-")
elif n < 80 and n >= 75:
    print("Nilai = B")
elif n < 75 and n >= 70:
    print("Nilai = B-")
else:
    print("Dibawah Rata-rata")
```  

## Nested **if**  
Yaitu **if** yang didalamnya terdapat **if** lagi. Indentasi harus lebih masuk lagi untuk membuat kondisi **if** baru. Fungsinya yaitu berguna untuk menjelaskan lebih detail dari kondisi **if** sebelumnya.  

Nested **if** dapat dilakukan berulang-ulang kali, tidak ada batasan.  

```python
a = int(input("Angka: "))
if a>10:
    print(">10")
    print("didalam if pertama")
    if a>20:
        print(">20")
        print("didalam nested if")
    else:
        print("<20")
        print("didalam kondisi else dari nested if")
```

Contoh lain yang lebih kompleks:

```python
a = int(input("Angka: "))
if a>10:
    print(">10")
    print("didalam if pertama")
    if a>20:
        print(">20")
        print("didalam nested if")
        if a>30:
            print(">30")
            print("didalam nested if dari if pertama")
        else:
            print("<=30")
            print("didalam kondisi else dari nested if dari if pertama")
    else:
        print("<=20")
        print("didalam kondisi else dari nested if")
else:
    print("<=10")
    print("didalam kondisi else")
```


> **Indentasi sangat berpengaruh terhadap kondisi if-else-elif, oleh karena itu harus sangat diperhatikan.**
