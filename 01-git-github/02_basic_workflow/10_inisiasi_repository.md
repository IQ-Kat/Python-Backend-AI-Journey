# 📘 Bab 10: Inisialisasi Repositori (`git init`)

> **Tujuan Belajar:**
> Menghidupkan fungsi pelacakan Git pada folder proyek agar setiap perubahan kode mulai tercatat dalam sejarah.

---

## 📖 1. Apa itu `git init`?

`git init` adalah perintah untuk membuat repositori baru. Saat kamu menjalankan perintah ini, Git akan menyiapkan infrastruktur pencatatan di dalam folder tersebut.

### Langkah-langkah Sebelum Inisialisasi:

1. **Cek Lokasi (`pwd`):** Pastikan kamu berada di folder utama proyek (Root Folder), bukan di folder Desktop atau folder User.
2. **Masuk ke Folder (`cd`):** Gunakan `cd` untuk masuk ke folder proyek yang sudah kamu siapkan (misal: `Sales_Forecasting`).

---

## 📂 2. Rahasia Folder `.git`

Begitu `git init` dijalankan, Git akan menciptakan folder tersembunyi bernama **`.git`**. Folder inilah yang kita sebut sebagai "Otak" atau database dari proyekmu.

| Karakteristik `.git` | Penjelasan |
| --- | --- |
| **Tersembunyi** | Tidak muncul di Windows Explorer biasa kecuali kamu menyalakan fitur *Show Hidden Items*. |
| **Database Lokal** | Berisi semua riwayat commit, branch, dan konfigurasi spesifik proyek tersebut. |
| **Fatal Jika Hilang** | Jika kamu menghapus folder ini, semua riwayat (versi-versi sebelumnya) akan **musnah**. Proyekmu akan kembali menjadi folder biasa. |

---

## ⚠️ Aturan Penting "Satu Proyek, Satu Git"

Banyak pemula terjebak melakukan `git init` di mana-mana. Ikuti aturan ini agar repositorimu tidak rusak:

1. **Hanya di Root:** Lakukan `git init` cukup **satu kali** di folder paling luar proyekmu.
2. **Hindari Sub-folder:** Jangan menjalankan `git init` di dalam sub-folder (seperti di dalam `src` atau `notebooks`). Jika ada folder `.git` di dalam folder yang sudah ada Git-nya, itu akan menyebabkan konflik (Nested Repo).
3. **Jangan "Otak-atik" Isi `.git`:** Kecuali kamu sudah level *Expert*, jangan pernah mengubah file di dalam folder `.git` secara manual lewat VS Code atau Notepad. Biarkan Git yang mengelolanya lewat terminal.

---

## 💻 Cara Memulai

```bash
# 1. Masuk ke folder proyek
cd ~/Project/AI_Model

# 2. Inisialisasi
git init

# 3. Verifikasi (melihat apakah folder .git sudah ada)
ls -a

```

---

## 💡 Tips & Peringatan

> **Tips:**
> Jika kamu salah melakukan `git init` di folder yang salah (misalnya tidak sengaja `git init` di folder Desktop), cara membatalkannya adalah dengan menghapus folder `.git`-nya menggunakan perintah: `rm -rf .git`.
>
> **Peringatan:**
> Ingat, Git hanya mencatat perubahan yang ada di dalam folder tempat `.git` berada dan sub-folder di bawahnya. File di luar folder tersebut tidak akan ikut terawasi.

---


[⬅️ Kembali ke Daftar Isi](../README.md)