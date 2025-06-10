---
title: "04 - N-Queens Problem"
date : 2025-5-20 00:00:00
categories : [N-Queens Problem]
tags : [N-Queens Problem]


---

# N-Queens Problem
**Kelompok 4**
- Aditya Hisbul Bahri
- Jonas Baka
- Akhmad Hidayat
- As’syiekril Fikryan Sarda
- M. Fadhil Mulyadi


## N-Queens Problem
N-Queens Problem adalah permasalahan klasik dalam ilmu komputer dan matematika kombinatorik, yang melibatkan penempatan N buah ratu pada papan catur berukuran N×N. Tujuannya adalah menempatkan ratu sedemikian rupa sehingga tidak ada dua ratu yang saling menyerang, baik secara horizontal, vertikal, maupun diagonal.

## Tujuan Masalah:
- Menemukan semua konfigurasi penempatan ratu yang memenuhi syarat.
- Mengembangkan algoritma pencarian dan optimasi, seperti backtracking, DFS, atau algoritma genetika.
- Melatih pemrograman logika dan pemecahan masalah dalam konteks constraint satisfaction problem (CSP).

## Pseucode 
    N-QUEENS(N)
    // Inisialisasi papan catur NxN dengan nilai 0 (kosong)
    board = array of size N×N, set to 0

    // Panggil fungsi untuk mencoba menempatkan ratu pada baris pertama
    if solveNQueens(board, 0, N) is true:
        print(board)  // Menampilkan solusi
    else:
        print("Tidak ada solusi ditemukan")

    solveNQueens(board, row, N)
    // Jika sudah menempatkan semua ratu, return true (solusi ditemukan)
    if row == N:
        return true

    // Coba tempatkan ratu di setiap kolom pada baris saat ini
    for col = 0 to N-1:
        // Periksa apakah posisi (row, col) aman
        if isSafe(board, row, col, N):
            // Tempatkan ratu di posisi (row, col)
            board[row][col] = 1

            // Rekursif untuk mencoba menempatkan ratu di baris berikutnya
            if solveNQueens(board, row + 1, N) is true:
                return true

            // Jika solusi tidak ditemukan, mundur (backtrack) dan coba posisi lain
            board[row][col] = 0

    return false  // Tidak ada posisi yang aman pada baris ini, backtrack

    isSafe(board, row, col, N)
    // Periksa kolom apakah ada ratu lain
    for i = 0 to row-1:
        if board[i][col] == 1:
            return false

    // Periksa diagonal kiri atas
    for i = row-1, j = col-1; i >= 0 && j >= 0; i--, j--:
        if board[i][j] == 1:
            return false

    // Periksa diagonal kanan atas
    for i = row-1, j = col+1; i >= 0 && j < N; i--, j++:
        if board[i][j] == 1:
            return false

    return true  // Posisi aman

- N-QUEENS(N): Fungsi utama untuk menginisialisasi papan catur dan memulai pencarian solusi.

- solveNQueens(board, row, N): Fungsi rekursif untuk menempatkan ratu di baris yang sesuai, mencoba setiap kolom untuk setiap baris, dan menggunakan backtracking jika perlu.

- isSafe(board, row, col, N): Fungsi untuk memeriksa apakah tempat (row, col) aman untuk ditempati oleh ratu, dengan memeriksa kolom dan kedua diagonal.


## Penerapan:
- Studi Kasus dalam AI dan Algoritma: Mengajarkan teknik pencarian seperti backtracking dan algoritma heuristic.
- Model Permasalahan Constraint Satisfaction: Contoh ideal dari masalah CSP.
- Aplikasi Dunia Nyata: Penjadwalan tugas, penempatan modul dalam sirkuit elektronik, dan pengalokasian sumber daya yang saling eksklusif.
- Kompleksitas dan Skalabilitas: Menilai efisiensi algoritma dalam skala besar.

## Pentingnya Masalah N-Queens:
- Studi Kasus Teknik Backtracking: Masalah N-Queens digunakan untuk mengilustrasikan teknik backtracking dalam pemrograman.
- Analisis Kompleksitas Algoritma: Membantu memahami perbedaan antara algoritma brute-force dan algoritma backtracking.
- Pengenalan Constraint Satisfaction Problem (CSP): Memperkenalkan CSP dalam kecerdasan buatan dan optimasi.