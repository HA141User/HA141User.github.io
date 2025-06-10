---
title: "01 - Activity Selection Problem"
date : 2025-5-06 00:00:00
categories : [Activity Selection Problem]
tags : [Activity Selection Problem]


---

# Activity Selection Problem

**Kelompok 1**

Daftar anggota :  
- Ahmad Hidayat  
- Julio Rema Palotongan  
- Suci Sri Aulia  
- Naailah Mazaya  
- Yud Bryawan  

## Activity Selection Problem ##
Activity Selection Problem adalah masalah optimasi yang bertujuan memilih aktivitas sebanyak mungkin tanpa tumpang tindih. Diberikan sejumlah aktivitas dengan waktu mulai (s) dan waktu selesai (f), tantangannya adalah memilih subset aktivitas terbesar yang tidak saling bertabrakan. Algoritma yang digunakan untuk menyelesaikan masalah ini adalah Greedy Algorithm, yang berfokus pada memilih aktivitas yang selesai paling awal.

## Langkah Penyelesaian ##
1. Urutkan aktivitas berdasarkan waktu selesai.
2. Pilih aktivitas pertama yang selesai paling awal.
3. Pilih aktivitas berikutnya jika waktu mulai lebih besar atau sama dengan waktu selesai aktivitas sebelumnya.

## Pseudocode untuk Activity Selection Problem ##


    for i = 2 to n
        if s[i] >= f[j]  // Jika waktu mulai aktivitas lebih besar atau sama dengan waktu selesai aktivitas terakhir
            A = A ∪ {ai}  // Pilih aktivitas ai
            j = i  // Update indeks aktivitas terakhir yang dipilih

    return A  // Kembalikan himpunan aktivitas yang terpilih

# Penjelasan Pseudocode #
- s[] adalah array yang berisi waktu mulai dari setiap aktivitas.

- f[] adalah array yang berisi waktu selesai dari setiap aktivitas (sudah diurutkan).

- n adalah jumlah total aktivitas yang tersedia.

- A adalah himpunan aktivitas yang terpilih.

- j adalah indeks aktivitas terakhir yang dipilih.

Algoritma ini memilih aktivitas sebanyak mungkin tanpa ada tumpang tindih dengan memilih aktivitas yang selesai paling awal dan melanjutkan ke aktivitas berikutnya yang kompatibel dengan aktivitas yang sudah dipilih sebelumnya.