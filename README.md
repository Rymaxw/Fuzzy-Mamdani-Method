## Program Sistem Fuzzy Mamdani – Penentuan 5 Bengkel Terbaik

Program ini digunakan untuk menentukan **5 bengkel terbaik** berdasarkan **kualitas servis** dan **harga** menggunakan **metode Fuzzy Mamdani**. Proses yang dilakukan meliputi pembacaan data, fuzzification, inferensi, dan defuzzification.

---

## Cara Menjalankan Program

1. Pastikan Python sudah terinstall.
2. Pastikan library `pandas` sudah terinstall dengan perintah:

   ```
   pip install pandas
   ```
3. Pastikan file berikut berada dalam **folder yang sama**:

   * File utama program (`.ipynb`)
   * `Dataset Bengkel AI.csv`
   * `Readme.txt`
4. Jalankan program dari **cell/baris pertama hingga terakhir secara berurutan**.
5. Program akan memproses data dan menampilkan hasil.
6. Hasil akhir akan disimpan ke file:

   ```
   Output_Top5_Bengkel.csv
   ```

---

## Format Dataset

Dataset berupa file CSV dan kolom sebagai berikut:

```
id_bengkel;Kualitas_Servis;Harga
```

Kualitas_Servis dan Harga menggunakan skala **1–10**.

---

## Penjelasan Kolom Hasil (Output)

Beberapa kolom tambahan dihasilkan selama proses perhitungan fuzzy, yaitu:

### `mu_servis`

Menunjukkan **derajat keanggotaan kualitas servis** terhadap kategori linguistik:

* `buruk`
* `cukup`
* `baik`

Contoh:

```
{'buruk': 0, 'cukup': 0, 'baik': 0.4}
```

Artinya kualitas servis **cenderung ke kategori baik** dengan derajat 0.4.

---

### `mu_harga`

Menunjukkan **derajat keanggotaan harga** terhadap kategori:

* `murah`
* `sedang`
* `mahal`

Contoh:

```
{'murah': 0.25, 'sedang': 0.5, 'mahal': 0}
```

Artinya harga berada di antara **murah dan sedang**, namun lebih dominan ke **sedang**.

---

### `out_strength`

Merupakan **hasil inferensi Mamdani**, yaitu derajat keanggotaan output kelayakan bengkel:

* `rendah`
* `sedang`
* `tinggi`

Contoh:

```
{'rendah': 0.6, 'sedang': 0, 'tinggi': 0}
```

Artinya sistem menilai bengkel memiliki **kelayakan rendah** dengan kekuatan 0.6.

---

### `Skor_Kelayakan`

Merupakan hasil **defuzzification** dari `out_strength` dalam bentuk nilai numerik (0–100).
Nilai ini digunakan untuk melakukan **perangkingan bengkel**.

---

## Output Program

Output akhir program berupa:

* Skor kelayakan setiap bengkel
* Daftar **5 bengkel terbaik** berdasarkan skor tertinggi
* File CSV hasil sorting

---
