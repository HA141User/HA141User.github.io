---
title: "09 - Khan's Algorithm"
date : 2025-6-03 00:00:00
categories : [Khan's Algorithm]
tags : [Khan's Algorithm]

---

# Khan's Algorithm
**Kelompok 9**

- Nurul Marisa Clara Waldi
- Agung Allo Karaeng
- Ahmad Rizky Amis
- Mahesa Putri Lukman

## Kahn’s Algorithm
Kahn's Algorithm adalah algoritma yang digunakan untuk melakukan penyusunan topologi (topological sorting) dalam Directed Acyclic Graph (DAG). Algoritma ini membantu menentukan urutan simpul dalam graf berdasarkan ketergantungan antar simpul. Dengan menggunakan pendekatan Breadth-First Search (BFS), Kahn’s Algorithm mengidentifikasi urutan yang valid di mana setiap simpul dengan ketergantungan akan muncul setelah simpul yang menjadi prasyaratnya.

## Prinsip Kerja:
- In-degree: Setiap simpul dihitung berdasarkan jumlah sisi masuk (in-degree).
- Antrean: Simpul-simpul dengan in-degree 0 (tidak ada ketergantungan) dimasukkan ke dalam antrean (queue).
- Proses:
    1. Proses simpul dari antrean satu per satu.
    2. Untuk setiap simpul yang diproses, kurangi in-degree dari simpul tetangga yang terhubung.
    3. Jika in-degree dari simpul tetangga menjadi 0, tambahkan simpul tersebut ke antrean.
    4. Pendeteksian Siklus: Jika setelah memproses semua simpul masih ada simpul yang belum diproses (graf memiliki simpul dengan in-degree > 0), maka graf mengandung siklus.

## Aplikasi:
- Penjadwalan Tugas: Digunakan untuk menyusun urutan tugas berdasarkan ketergantungan (misalnya, urutan mata kuliah atau tugas dalam proyek).
- Kompilasi Program: Digunakan untuk menyusun urutan kompilasi file sumber yang saling bergantung.
- Manajemen Prasyarat Mata Kuliah: Menentukan urutan mata kuliah yang harus diambil berdasarkan prasyarat.

## Kelebihan:
- Algoritma sangat efisien dengan kompleksitas waktu O(V + E), di mana V adalah jumlah simpul dan E adalah jumlah sisi dalam graf.
- Dapat mendeteksi keberadaan siklus dalam graf berarah.
- Memungkinkan lebih dari satu urutan topologis yang valid jika ketergantungan memungkinkan.

## Kekurangan:
- Tidak bisa digunakan pada graf yang mengandung siklus.
- Memerlukan struktur data tambahan, seperti in-degree dan graf, untuk implementasinya.

Kahn's Algorithm adalah metode yang efisien dan sistematis untuk melakukan topological sorting pada Directed Acyclic Graph (DAG). Dengan pendekatan yang memanfaatkan struktur in-degree dan antrean, algoritma ini cocok digunakan dalam berbagai aplikasi, seperti penjadwalan tugas, kompilasi program, dan pengelolaan prasyarat mata kuliah, serta memiliki waktu eksekusi yang optimal.