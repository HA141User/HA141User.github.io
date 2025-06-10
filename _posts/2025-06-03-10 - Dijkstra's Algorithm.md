---
title: "10 - Dijkstra's Algorithm"
date : 2025-6-03 00:00:00
categories : [Dijkstra's Algorithm]
tags : [Dijkstra's Algorithm]


---

# Dijkstra's Algorithm

**Kelompok 10**

- Akmal
- Muhammad Arlis
- Muhammad Hairi
- Zahra Aulia Putri

## Dijkstra's Algorithm
Dijkstra's Algorithm adalah algoritma yang digunakan untuk mencari jalur terpendek antara dua titik dalam sebuah graf berbobot. Algoritma ini bekerja dengan memilih jalur terpendek berdasarkan bobot sisi yang ada, dan mencari jalur optimal dari titik awal ke tujuan. Dijkstra menggunakan pendekatan greedy dengan mengutamakan simpul yang memiliki jarak terpendek dari titik awal.

## Cara Kerja:
- Buat tabel yang berisi jarak dari simpul awal ke setiap simpul lainnya.
- Tentukan simpul awal dan tujuan, dengan asumsi simpul tersebut terhubung langsung.
- Hitung jarak ke beberapa simpul tujuan yang telah dipilih.
- Pilih jarak yang terpendek setelah semua simpul diuji.
- Ulangi langkah ini sampai semua simpul telah diuji.

## Pseucode 
    DIJKSTRA(graph, start):
    // Inisialisasi jarak untuk semua simpul
    dist = array of size V (jumlah simpul), set all to infinity
    dist[start] = 0  // Jarak ke simpul awal adalah 0

    // Inisialisasi set visited untuk melacak simpul yang sudah diproses
    visited = empty set

    // Buat priority queue untuk memilih simpul dengan jarak terpendek
    pq = empty priority queue
    enqueue(pq, start, dist[start])

    while pq is not empty:
        // Ambil simpul dengan jarak terpendek dari priority queue
        u = dequeue(pq)

        // Tandai simpul u sebagai sudah diproses
        add u to visited

        // Periksa semua tetangga dari simpul u
        for each neighbor v of u:
            if v not in visited:
                // Jika jarak baru lebih pendek, perbarui jarak v
                if dist[u] + weight(u, v) < dist[v]:
                    dist[v] = dist[u] + weight(u, v)
                    enqueue(pq, v, dist[v])

    return dist  // Kembalikan jarak terpendek dari start ke semua simpul

- Inisialisasi: Menetapkan jarak awal untuk semua simpul sebagai tak terhingga, kecuali simpul awal yang jaraknya 0.

- Priority Queue: Menggunakan priority queue untuk memilih simpul dengan jarak terpendek yang belum diproses.

- Proses: Setiap simpul diambil dari queue, dan jarak ke semua tetangganya diperbarui jika ditemukan jalur yang lebih pendek.

- Penyelesaian: Proses ini diulang sampai semua simpul diproses, dan akhirnya, jarak terpendek dari simpul awal ke semua simpul lain dikembalikan.

## Kelebihan:
- Jaminan Jalur Terpendek: Dijkstra selalu menemukan jalur terpendek dari titik asal ke semua titik lain jika semua bobot sisi positif.
- Efisien untuk Graf Padat: Sangat cocok untuk graf padat dan banyak digunakan dalam aplikasi seperti GPS dan sistem navigasi.
- Menyelesaikan Banyak Tujuan: Sekali dijalankan, Dijkstra bisa memberikan informasi jarak terpendek ke semua titik lainnya dalam graf.

## Kekurangan:
- Tidak Bekerja dengan Bobot Negatif: Algoritma ini tidak dapat digunakan jika ada sisi dengan bobot negatif.
- Kurang Efisien untuk Graf Besar yang Jarang Terhubung: Pada graf yang sangat besar dan jarang terhubung, Dijkstra bisa menjadi lambat jika tidak dioptimalkan dengan struktur data seperti priority queue.
- Perhitungan Terlalu Luas: Jika hanya ingin jalur dari titik A ke B, Dijkstra tetap menghitung semua kemungkinan ke titik lain, yang kadang tidak efisien. Dalam kasus ini, algoritma A* bisa lebih baik.

## Aplikasi Nyata:
- Navigasi Jalan: Dijkstra digunakan untuk mencari rute terpendek dalam sistem navigasi, seperti Google Maps.
- Pengiriman Barang: Dijkstra membantu menentukan rute pengiriman yang paling efisien.
- Jaringan Komputer: Digunakan untuk menemukan jalur terbaik antar perangkat dalam jaringan.

Dijkstra's Algorithm adalah algoritma yang efisien dan banyak digunakan untuk mencari jalur terpendek dalam graf berbobot non-negatif. Meskipun memiliki keterbatasan seperti tidak dapat menangani bobot negatif, algoritma ini sangat berguna dalam aplikasi praktis seperti jaringan komputer, sistem navigasi, dan pemodelan transportasi.