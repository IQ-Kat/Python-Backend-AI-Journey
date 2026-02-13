# 📘 Bab 01: Python 2 vs Python 3

> **Tujuan Belajar:**
> Memahami alasan evolusi Python dan mengapa Python 3 adalah pilihan mutlak untuk era AI dan Big Data.

---

## 📖 Perbandingan Utama

| Fitur | Python 2 (Old Gen) | Python 3 (Modern) |
| --- | --- | --- |
| **Teks/Karakter** | Berbasis **ASCII** (Terbatas). | Berbasis **Unicode** (Mendukung emoji, aksara asing, dll). |
| **Pembagian ( / )** | **Integer Division**: `5/2 = 2`. | **Float Division**: `5/2 = 2.5`. |
| **Fungsi Print** | Adalah **Statement**: `print "Halo"`. | Adalah **Fungsi**: `print("Halo")`. |
| **Manajemen RAM** | Kurang efisien (memuat semua ke RAM). | Sangat efisien (**Lazy Evaluation** via `range`). |
| **Status** | *End of Life* (Tidak diupdate lagi). | Aktif dikembangkan (3.10+ sangat canggih). |

---

## 🧠 Analisis Mendalam (Sudut Pandang AI)

### 1. Masalah Presisi Angka (Division)

Di Python 3, pembagian default selalu menghasilkan desimal (`float`). Jika ingin meniru gaya Python 2 yang membulatkan ke bawah, kita menggunakan operator **`//`** (Floor Division).

* **Contoh:** `5 // 2` hasilnya `2`.
* *Kenapa penting?* Di dunia AI, nilai desimal di belakang koma adalah segalanya. Python 3 menjaga nilai tersebut agar tidak hilang secara tidak sengaja.

### 2. Efisiensi Memori (`range` vs `xrange`)

Di Python 2, perintah `range(1000000)` akan langsung membuat list berisi 1 juta angka di RAM. Di Python 3, `range` hanya akan membuat angka **saat dibutuhkan saja**.

* *Kenapa penting?* Saat mengolah dataset jutaan baris, Python 3 tidak akan membuat laptopmu *hang* karena kehabisan RAM.

### 3. Structural Pattern Matching (Python 3.10+)

Ini adalah fitur "sakti" yang kamu maksud. Di versi 3.10 ke atas, kita punya perintah `match` dan `case`.

* Fungsinya mirip `switch-case` di bahasa lain, tapi jauh lebih hebat karena bisa langsung membedah (unpack) data di dalam `list` atau `dict` secara instan.

---

## 💡 Tips & Peringatan

> **Tips:**
> Jika kamu menemukan kode tutorial lama yang masih menggunakan `print` tanpa kurung, itu tandanya tutorial tersebut sudah kadaluwarsa. Sebaiknya cari tutorial yang menggunakan Python 3.10 ke atas.
> **Peringatan:**
> Jangan pernah menginstal Python 2 di laptopmu kecuali kamu benar-benar dipaksa oleh sistem lama. Python 2 sudah tidak mendapatkan pembaruan keamanan sejak tahun 2020.

---

### 📝 Catatan Tambahan (Pro Tips)

Poin kamu soal `print` sebagai fungsi juga memungkinkan kita melakukan trik keren seperti ini:

```python
print("Data", "AI", sep=" -> ", end=" DONE\n")
# Output: Data -> AI DONE

```

Ini sangat membantu saat kita ingin merapikan tampilan log proses training model AI nantinya.

---

[⬅️ Kembali ke Daftar Isi](../README.md)