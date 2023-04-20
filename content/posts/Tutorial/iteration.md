---
title: "Python Basic 5: Iteration"
date: 2022-08-27T01:34:40+07:00
description: "Mengenal iteration (loop) pada python."
tags: ["python", "tutorial"]
---

Iteration (loop) digunakan untuk menjalankan kode yang sama dan berulang-ulang.  

Terdapat dua jenis loop: **while** dan **for**.

Keduanya dapat memiliki fungsi yang sama, hanya berbeda dari penulisan syntax-nya saja, tetapi biasanya **while** loop digunakan pada saat data yang ingin diiterasikan tidak diketahui pasti berapa jumlahnya, sedangkan **for** loop digunakan pada saat data yang diiterasikan diketahui pasti berapa jumlahnya.  

## **while** loop   

```python
n = int(input("Angka:"))
i = 1
while i < n:
    print (i**2)
    print ("Ini merupakan iterasi ke-",i)
    i+=1       #sama seperti i = i+1
print("Iterasi selesai")
```  

### *pass* Statement  

*pass* merupakan statement untuk tidak melakukan apa-apa, yang berarti tidak ada yang perlu dilakukan didalam badan loop.  

Statement tersebut tersebut bisa saja tidak dibuat, tetapi dengan adanya statement tersebut, kode lebih mudah untuk dipahami dan dibaca.  

```python
n = int(input('Max iteration :'))
i = 1
while i < n:
    if i%2 == 0:
        print(i)
    else:
        pass
    i += 1
print('Done')
```  

### *break* dan *continue* statement

*break* merupakan statement yang ketika berjalan maka fungsinya yaitu keluar dari loop (berhenti melakukan loop).

*continue* merupakan statement yang ketika berjalan maka fungsinya yaitu akan melanjutkan loop dengan tidak memerhatikan statement atau kode lain dibawah dari statement *continue* tersebut. Yang berarti statement ini akan men-skip kode pada badan loop yang berada dibawahnya. Kedua statement ini dapat digunakan pada **while** dan **for** loop.  

```python
i = 1
while True:
    if i%10 == 0:
        print('break')
        break
    else:
        i = i+1
        print('continue')
        continue
print('Done')
```  

Contoh lain:  

```python
i = 1
while True:
    if i%9 != 0:
        print("inside if")
        i += 1
        continue
    print("continue?")
    break
print('Done')
```

> Pada **while** loop menggunakan syntax yang mirip seperti **if** condition, yakni menggunakan comparisons/boolean.

## **for** loop  

```python
L = []
for i in range(10):    # range(10) berarti dari 0 hingga 9
    print(i+1)
    L.append(i**2)     # .append untuk memasukkan kembali hasil iterasi kedalam list diatasnya (sebelum iterasi)
print(L)
```

Contoh lain:

```python
L = []
for i in range(1,10,2):    # range(x,y,z) berarti mulai dari x sampai sebelum y, dan dengan interval z
    print(i)
    L.append(i**2)
print(L)
```  

## **else** pada **for** loop  

Bagian **else** akan dijalankan ketika loop pada **for** telah selesai dijalankan (kecuali jika terdapat *break* statement pada bagian **for** loop).  

```python
S = {"apple", 3.14, "mango"}
for i in S:
    print(i)
else:
    print("Iterasi telah selesai")
print("diluar loop")
```

> Pada **for** loop biasanya menggunakan data structure seperti List, Tuple, Dictionary, dsb..
