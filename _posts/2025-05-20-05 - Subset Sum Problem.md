---
title: "05 - Subset Sum Problem"
date : 2025-5-20 00:00:00
categories : [Subset Sum Problem]
tags : [Subset Sum Problem]

---

# Subset Sum Problem
**Kelompok 5**
- Ishmah Nurwasilah
- Trivania Buli Karoma
- Diani Annisah
- Diesty Mendila Tappo
- Muhammad Fatir Syabhan

## Subset Sum Problem (SSP)
Subset Sum Problem adalah masalah klasik dalam ilmu komputer yang tergolong dalam kategori NP-Complete. Masalah ini bertujuan untuk menentukan apakah ada subset dari sebuah himpunan bilangan bulat yang jumlah elemennya sama dengan nilai target tertentu. Dalam implementasinya, masalah ini dapat diselesaikan dengan berbagai pendekatan, baik menggunakan teknik brute-force atau dynamic programming yang lebih efisien.

## Variasi Masalah

- Bounded Subset Sum Problem: Setiap elemen dalam himpunan hanya dapat digunakan sekali.
- Partition Problem: Membagi himpunan bilangan bulat menjadi dua subset dengan jumlah yang sama.
- Exact k Elements Subset Sum: Menemukan subset yang terdiri dari tepat k elemen dan jumlahnya sama dengan target.
- Unbounded Subset Sum Problem: Elemen boleh digunakan berulang kali untuk mencapai target.
- Multi-target Subset Sum Problem: Mencari subset yang memenuhi lebih dari satu kriteria atau batasan secara bersamaan.
- Approximate Subset Sum: Menemukan subset yang paling mendekati target jika tidak ada yang cocok.

## Pseucode
    SUBSET-SUM(arr, target)
    // Inisialisasi tabel dp dengan ukuran (n+1) x (target+1)
    n = length(arr)
    dp = 2D array of size (n+1) x (target+1)

    // Set dp[i][0] = True, karena subset kosong selalu dapat membentuk sum 0
    for i = 0 to n:
        dp[i][0] = True

    // Set dp[0][j] = False untuk j > 0, karena tidak ada subset yang dapat membentuk sum > 0 tanpa elemen
    for j = 1 to target:
        dp[0][j] = False

    // Isi tabel dp
    for i = 1 to n:
        for j = 1 to target:
            if arr[i-1] <= j:
                dp[i][j] = dp[i-1][j] or dp[i-1][j - arr[i-1]]  // Termasuk atau abaikan elemen arr[i-1]
            else:
                dp[i][j] = dp[i-1][j]  // Abaikan elemen arr[i-1]

    return dp[n][target]  // Jika True, ada subset yang jumlahnya sama dengan target

- Inisialisasi Tabel dp: Membuat tabel dp dengan ukuran (n+1) x (target+1) untuk menyimpan apakah suatu sum dapat dibentuk menggunakan subset dari elemen yang sudah dipilih.

- Isi Tabel dp: Untuk setiap elemen, tentukan apakah dengan memasukkan elemen tersebut, jumlah sum tertentu dapat dicapai. Jika bisa, set nilai dp[i][j] menjadi True.

- Kembalikan Hasil: Pada akhir tabel, dp[n][target] akan menunjukkan apakah ada subset yang jumlahnya sama dengan nilai target.

## Pendekatan Penyelesaian:
- Pendekatan Rekursif: Mengecek semua subset secara eksplisit. Kompleksitas: O(2ⁿ), kurang efisien untuk array besar.
- Dynamic Programming (Memoization dan Tabulation):
- Memoization (Top-Down): Kombinasi rekursi dan penyimpanan hasil submasalah untuk mengurangi pemanggilan ulang.
- Tabulation (Bottom-Up): Menggunakan tabel untuk menyimpan solusi dari submasalah dan iterasi solusi dari bawah ke atas.
- Optimasi Ruang: Menggunakan dua array 1D untuk mengurangi penggunaan memori dari O(n × sum) menjadi O(sum).

## Aplikasi Dunia Nyata:
- Kriptografi: Digunakan dalam sistem kriptografi berbasis ransel.
- Alokasi Sumber Daya: Membantu memilih subset proyek yang sesuai dengan anggaran atau target.
- Genetika dan Bioinformatika: Menganalisis kombinasi gen atau fragmen DNA.
- Keuangan dan Investasi: Membantu menentukan kombinasi aset untuk mencapai target investasi.
- Perancangan Permainan dan Teka-Teki: Digunakan dalam permainan atau teka-teki yang melibatkan pencarian kombinasi angka.

Subset Sum Problem adalah masalah penting dalam teori dan praktik yang melibatkan pencarian kombinasi angka untuk mencapai target jumlah tertentu. Dengan menggunakan pendekatan rekursif dan dynamic programming, masalah ini dapat diselesaikan secara efisien, dengan aplikasi luas dalam bidang kriptografi, pengelolaan sumber daya, dan kecerdasan buatan.