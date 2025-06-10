---
title: "03 - Huffman Coding"
date : 2025-5-20 00:00:00
categories : [Huffman Coding]
tags : [Huffman Coding]


---
# Huffman Coding

**Kelompok 3**

Daftar anggota :  
- Dalvyn Suhada
- Sarham San
- Hilmy Affayyad Akbar
- Ivan Ramadhan
- Gyerend Nydle Linta Mangaluk

## Definisi Huffman Coding
Huffman Coding adalah algoritma kompresi data lossless yang digunakan untuk mengurangi ukuran data dengan mengganti simbol yang sering muncul dengan kode bit yang lebih pendek. Huffman Coding banyak digunakan dalam format kompresi seperti ZIP, JPEG, dan MP3. Prinsip kerjanya adalah karakter dengan frekuensi tinggi akan mendapatkan kode yang lebih pendek, sedangkan karakter dengan frekuensi rendah mendapatkan kode yang lebih panjang.

## Strategi Penyelesaian:
- Hitung frekuensi setiap karakter dalam data.
- Gabungkan dua simpul dengan frekuensi terkecil dan ulangi proses hingga terbentuk pohon Huffman.
- Tentukan kode biner untuk setiap karakter, dengan 0 untuk sisi kiri dan 1 untuk sisi kanan.

## Kompleksitas:
- Waktu: O(N log N), di mana N adalah jumlah karakter unik.
- Ruang: O(N), untuk menyimpan data barang.

## Pseucode

    HUFFMAN-CODING(input)
    // Hitung frekuensi setiap karakter dalam data input
    for each character in input:
        frequency[character]++  // Hitung frekuensi karakter

    // Buat simpul untuk setiap karakter
    create a priority queue (min-heap) to store nodes
    for each character in frequency:
        create a node with character and its frequency
        insert node into the priority queue

    // Gabungkan simpul dengan frekuensi terkecil hingga hanya ada satu pohon
    while size of priority queue > 1:
        // Ambil dua simpul dengan frekuensi terkecil
        node1 = extractMin(priorityQueue)
        node2 = extractMin(priorityQueue)

        // Gabungkan kedua simpul menjadi satu simpul baru
        newNode = createNode(node1.frequency + node2.frequency)
        newNode.left = node1
        newNode.right = node2

        // Masukkan simpul baru kembali ke dalam priority queue
        insert(newNode, priorityQueue)

    // Traversal pohon Huffman dan tentukan kode biner untuk setiap karakter
    root = extractMin(priorityQueue)  // Pohon Huffman yang terbentuk
    assignCodes(root, "", huffmanCodes)  // Traversal pohon dan tentukan kode biner

    return huffmanCodes  // Kembalikan kode biner untuk setiap karakter

- Hitung Frekuensi: Menghitung berapa kali setiap karakter muncul dalam data input.

- Membuat Pohon Huffman: Menggunakan struktur data min-heap untuk menggabungkan simpul berdasarkan frekuensi terkecil.

- Traversal Pohon: Melakukan traversal dari akar pohon untuk menentukan kode biner bagi setiap karakter (kode 0 untuk sisi kiri, kode 1 untuk sisi kanan).

- Kembalikan Kode Biner: Kode biner untuk setiap karakter yang dihasilkan selama traversal pohon dikembalikan sebagai output.


## Aplikasi:
- Kompresi file (ZIP, JPEG, MP3)
- Pengkodean data dalam komunikasi digital
- Pengoptimalkan penyimpanan dan transmisi data

Huffman Coding adalah algoritma kompresi lossless yang menggunakan pendekatan greedy untuk mengurangi ukuran data dengan mengganti simbol berdasarkan frekuensi kemunculannya. Algoritma ini efisien dan efektif untuk data dengan distribusi karakter tidak merata, namun kurang optimal jika karakter memiliki frekuensi yang hampir sama. Dengan kompleksitas waktu yang rendah, Huffman Coding banyak digunakan dalam sistem kompresi file dan pengkodean data digital.