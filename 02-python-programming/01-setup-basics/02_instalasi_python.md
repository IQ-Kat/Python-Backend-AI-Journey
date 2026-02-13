# 📘 Bab 02: Instalasi & Anatomi Python (Architect Perspective)

> **Tujuan Belajar:**
> Memahami cara kerja mesin Python dan memastikan fondasi instalasi yang kokoh untuk pengembangan sistem Backend dan AI.

---

## 📖 1. Apa itu Interpreter? (The Engine)

Berbeda dengan C++ yang di-*compile* langsung menjadi file `.exe` (bahasa mesin), Python adalah bahasa **Interpreted**. Artinya, kode kamu diterjemahkan secara bertahap saat dijalankan.

### Alur Kerja Internal:

1. **Source Code (`.py`)**: Cetak biru (*Blueprint*) yang kamu tulis.
2. **Bytecode (`.pyc`)**: Hasil terjemahan mandor (Interpreter) ke bahasa tingkat rendah yang efisien.
3. **PVM (Python Virtual Machine)**: "Kuli" yang mengeksekusi *bytecode* tersebut agar bisa dipahami oleh Hardware (CPU).

---

## ⚖️ 2. Memilih Jalur Instalasi

Sebagai calon *Backend Architect*, pemilihan sumber instalasi akan menentukan seberapa fleksibel sistem yang kamu bangun.

| Jalur | Kelebihan | Kekurangan |
| --- | --- | --- |
| **Python.org (Official)** | **Harga Mati.** Akses sistem penuh, stabil, dan standar industri. | Harus diatur manual (PATH). |
| **Microsoft Store** | Instalasi satu klik. | **Sandboxed.** Terkunci di folder sistem, sulit untuk otomatisasi dan *virtual environment*. |
| **Anaconda/Miniconda** | Kaya *library* data science. | **Sangat Berat.** Memakan RAM besar; kurang efisien untuk laptop dengan spesifikasi terbatas. |

---

## 🏗️ 3. Jantung Instalasi: PATH

PATH adalah "Daftar Alamat" Windows. Tanpa mendaftarkan Python ke dalam PATH, Windows akan menjadi "buta" dan tidak tahu di mana harus mencari mesin Python saat kamu mengetik perintah di terminal.

> **Peringatan:** Selalu centang **"Add Python to PATH"** saat awal instalasi. Jika terlewat, kamu harus menambahkannya secara manual lewat *Environment Variables*.

---

## 🔍 4. Verifikasi & Command 'where'

Jangan hanya percaya pada versi, cek juga lokasi fisiknya untuk memastikan tidak ada "Python Hantu" (seperti versi 3.11 yang kita bahas tadi) yang ikut campur.

* **`python --version`**: Cek versi mesin.
* **`where python`**: Mencari alamat rumah tempat mesin Python tinggal.

---

## 💡 Expert Tips: Breaking the Limits

Saat proses instalasi selesai, Windows akan menawarkan opsi **"Disable Path Length Limit"**.

**Kenapa ini wajib diaktifkan?**
Windows memiliki batasan panjang alamat folder sebesar **260 karakter**. Dalam proyek AI atau Backend yang kompleks, folder sering kali bertingkat-tingkat (misal: `Project/data/raw/images/training/subset/category_a/...`). Jika limit ini aktif, Python akan gagal membaca file tersebut dan memicu *error* yang sangat sulit dilacak.

---

[⬅️ Kembali ke Daftar Isi](../README.md)