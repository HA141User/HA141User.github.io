---
title: "08 - Depth-First Search (DFS)"
date : 2025-5-27 00:00:00
categories : [Depth-First Search (DFS)]
tags : [Depth-First Search (DFS)]
---

# Depth-First Search (DFS)
**Kelompok 8**

- Bismillah Ghaniyyu Putra Darmin
- Maynova Christin Gabryela Simamora
- Nabila Salsabila
- Moh. Ichwanul Muslimin Mayang

## DEPTH-FIRST SEARCH (DFS)  
Algoritma pencarian atau penelusuran pada struktur data graf atau pohon yang bekerja 
dengan menjelajahi satu cabang sedalam mungkin sebelum (backtrack) dan melanjutkan ke
cabang berikutnya.

## Prinsip utama

- Masukkan simpul (node) akar ke dalam stack
- Ambil node dari stack teratas, lalu cek apakah node tersebut merupakan solusi?
- Jika node merupakan solusi, pencarian selesai dan hasil dikembalikan
- Jika node bukan solusi, masukkan seluruh node anak ke dalam stack
- Jika stack tidak kosong, ulangi pencarian mulai langkah ke-2
- Jika stack kosong, dan setiap node sudah dicek, pencarian berakhir

## Pseucode 
    DFS(graph, start):
    // Inisialisasi stack dan visited set
    stack = empty stack
    visited = empty set

    // Masukkan simpul awal ke dalam stack
    push(stack, start)
    add start to visited

    while stack is not empty:
        // Ambil simpul teratas dari stack
        node = pop(stack)

        // Proses simpul (misal, tampilkan simpul atau cek tujuan)
        process(node)

        // Kunjungi semua tetangga dari simpul tersebut yang belum dikunjungi
        for each neighbor of node:
            if neighbor not in visited:
                push(stack, neighbor)
                add neighbor to visited

    return visited  // Atau hasil lainnya, jika diperlukan

- Inisialisasi: Mulai dengan menentukan simpul awal dan memasukkannya ke dalam stack serta set visited untuk melacak simpul yang telah dikunjungi.

- Proses: Ambil simpul dari stack, proses simpul tersebut, dan kunjungi semua tetangga yang belum dikunjungi.

- Penyelesaian: Ulangi proses ini hingga stack kosong, artinya semua simpul yang dapat dijangkau telah diproses.



## Kelebihan & Kekurangan

### Kelebihan 

- Penggunaan memori lebih efisien
- Mudah diimplementasikan
- Digunakan dalam banyak algoritma penting
- Cocok untuk menemukan solusi kedalaman maksimal

### Kekurangan

- Tidak menjamin solusi terbaik
- Bisa masuk ke infinite loop (pada graf siklik)
- Kurang efisien di graf luas tapi dangkal
- Tidak cocok untuk semua masalah

Depth-First Search (DFS) merupakan algoritma penelusuran pada struktur data graf atau pohon yang menjelajahi simpul sedalam mungkin sebelum kembali (backtracking) dan melanjutkan ke simpul lainnya. Proses penelusuran ini dilakukan dengan menggunakan struktur data stack yang mengikuti prinsip LIFO (Last In First Out). DFS dimulai dari simpul akar, kemudian terus menyusuri anak-anak simpul hingga mencapai simpul terdalam, sebelum kembali ke simpul sebelumnya untuk menjelajahi cabang lain yang belum dikunjungi. DFS cocok digunakan untuk pencarian solusi pada kedalaman maksimal dan dapat menghasilkan jalur penelusuran yang berbeda tergantung pada urutan pemrosesan simpul.

