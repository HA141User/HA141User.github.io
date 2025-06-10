---
title: "07 - Breadth-First Search (BFS)"
date : 2025-5-27 00:00:00
categories : [Breadth-First Search (BFS)]
tags : [Breadth-First Search (BFS)]


---

# Breadth-First Search (BFS)
**Kelompok 7**
- Muh. Hanif Nurmahdin
- Kevin Anugrah Somakila’
- Moch. Syech Yusuf. M
- Raihan Ramadhan

## Breadth-First Search (BFS)
Breadth-First Search (BFS) adalah algoritma penelusuran graf atau pohon yang menjelajahi simpul-simpul berdasarkan jaraknya dari titik awal. BFS akan mengeksplorasi semua simpul yang paling dekat terlebih dahulu, baru kemudian beralih ke simpul yang lebih jauh. BFS menggunakan struktur data queue untuk memastikan bahwa simpul yang lebih dekat dieksplorasi lebih dahulu, yang membuat algoritma ini cocok untuk mencari jalur terpendek pada graf tak berbobot.

## Konsep Dasar:
- Inisialisasi: Tentukan simpul awal dan masukkan ke dalam antrian.
- Proses:
    1. Ambil simpul terdepan dari antrian, tandai sebagai telah dikunjungi.
    2. Kunjungi semua tetangga dari simpul tersebut yang belum dikunjungi dan tambahkan ke dalam antrian.
    3. Penyelesaian: Ulangi proses ini sampai simpul tujuan ditemukan atau antrian kosong.

# Kelebihan:
- Optimal: Menjamin ditemukannya solusi terbaik (jika ada solusi) pada graf tak berbobot.
- Sederhana dan Mudah Diimplementasikan: BFS mudah diimplementasikan dan efektif untuk aplikasi pencarian jalur.

## Kekurangan:
- Memori dan Waktu: BFS membutuhkan banyak memori dan waktu untuk graf besar karena harus menyimpan semua simpul yang dikunjungi dalam antrian.

## Pseucode
    BFS(graph, start):
    // Inisialisasi antrian untuk menyimpan simpul yang akan dikunjungi
    queue = empty queue
    visited = empty set

    // Masukkan simpul awal ke dalam antrian
    enqueue(queue, start)
    add start to visited

    while queue is not empty:
        // Ambil simpul terdepan dari antrian
        node = dequeue(queue)

        // Proses simpul (misal, tampilkan simpul atau cek tujuan)
        process(node)

        // Kunjungi semua tetangga dari simpul
        for each neighbor of node:
            if neighbor not in visited:
                enqueue(queue, neighbor)
                add neighbor to visited

    return visited  // Atau hasil lainnya, jika diperlukan

- Inisialisasi: Mulai dengan menentukan simpul awal dan memasukkannya ke dalam antrian serta set visited untuk melacak simpul yang telah dikunjungi.

- Proses: Ambil simpul dari antrian, proses simpul tersebut, dan kunjungi semua tetangga yang belum dikunjungi.

- Penyelesaian: Ulangi proses ini hingga antrian kosong, artinya semua simpul yang dapat dijangkau telah diproses.

## Aplikasi Nyata:
- Media Sosial: Digunakan untuk menemukan teman atau koneksi dalam jarak tertentu, seperti di Facebook atau LinkedIn.
- Jaringan Komputer: Memetakan perangkat dalam jaringan komputer, mulai dari router utama hingga perangkat yang terhubung.
- Transportasi dan Navigasi: Digunakan dalam aplikasi seperti Google Maps untuk mencari rute terpendek antar titik.
- Permainan dan Labirin: Digunakan dalam game untuk mencari jalur terpendek atau dalam game seperti Pac-Man untuk menghitung rute.

BFS adalah algoritma penelusuran graf yang efektif dalam mencari jalur terpendek pada graf tak berbobot. Dengan menggunakan antrian, BFS memastikan bahwa simpul yang lebih dekat dieksplorasi terlebih dahulu, sehingga sangat cocok untuk aplikasi pencarian jalur dalam game, peta, dan pencarian data lainnya.
