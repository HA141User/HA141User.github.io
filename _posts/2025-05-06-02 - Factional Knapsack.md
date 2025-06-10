---
title: "02 - Factional Knapsack"
date : 2025-5-06 00:00:00
categories : [Factional Knapsack]
tags : [Factional Knapsack]


---

# Factional Knapsack
**Kelompok 2**

Daftar anggota :  
- Zalfa Syauqiyah Hamka
- Davidzen
- Maisyah Mahdiyyah
- Muhammad Fadel Aryasatya Makkulau
- Hezekiah Reynard Tikupadang

## Definisi Fractional Knapsack Problem ##
Fractional Knapsack Problem adalah masalah optimasi di mana tujuannya adalah untuk memaksimalkan nilai total barang yang dimasukkan ke dalam knapsack (tas) dengan kapasitas terbatas, dengan kemungkinan mengambil sebagian dari barang tersebut. Ini berbeda dengan 0/1 Knapsack yang hanya membolehkan barang diambil seluruhnya. Pada Fractional Knapsack, barang dapat dipotong sesuai kebutuhan.

## Strategi Penyelesaian:
- Hitung rasio value/weight untuk setiap item.
- Urutkan item berdasarkan rasio tersebut secara menurun.
- Ambil sebanyak mungkin dari item dengan rasio tertinggi hingga kapasitas tas penuh.
- Jika tidak bisa mengambil seluruh item karena kapasitas tersisa, ambil sebagian dari item terakhir.

## Pseudocode

    FRACTIONAL-KNAPSACK(items, capacity)
    for each item:
        item.ratio = item.value / item.weight  // Hitung rasio value/weight

    sort(items) by item.ratio in descending order  // Urutkan berdasarkan rasio

    totalValue = 0
    for each item in sorted items:
        if capacity >= item.weight:
            totalValue += item.value  // Ambil seluruh item
            capacity -= item.weight
        else:
            totalValue += item.value * (capacity / item.weight)  // Ambil sebagian item
            break  // Tas sudah penuh

    return totalValue  // Kembalikan nilai total yang diperoleh


## Kompleksitas:
- Waktu: O(n log n) untuk pengurutan dan O(n) untuk memasukkan item.
- Ruang: O(n) untuk menyimpan data barang.

## Aplikasi:
- Penjadwalan tugas dengan sumber daya terbatas
- Investasi dana ke beberapa proyek
- Pengalokasian bandwidth dalam jaringan
- Optimisasi logistik

Fractional Knapsack adalah variasi dari Knapsack Problem yang dapat diselesaikan dengan pendekatan algoritma greedy, di mana kita dapat mengambil sebagian dari barang untuk mencapai solusi optimal. Dengan menghitung rasio nilai/berat dan memilih barang dengan rasio tertinggi, kita dapat memaksimalkan nilai total dalam kapasitas tas terbatas dengan cara yang efisien dan cepat. Algoritma ini efektif dalam banyak aplikasi dunia nyata, meskipun tidak cocok untuk semua jenis masalah yang memerlukan keputusan lebih kompleks atau dengan banyak batasan tambahan.

