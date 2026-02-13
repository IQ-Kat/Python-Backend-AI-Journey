# 📘 Bab 08: Konfigurasi Editor Default Git

> **Tujuan Belajar:**
> Menghindari "perangkap" VIM dan memastikan Git terintegrasi sempurna dengan VS Code untuk tugas-tugas kompleks.

---

## 📖 Kenapa Harus VS Code?

Secara bawaan (*default*), Git menggunakan **VIM**. VIM adalah editor teks berbasis terminal yang sangat powerful tapi sangat tidak ramah pemula (bahkan untuk keluar dari aplikasinya saja banyak orang bingung). Sebagai pengguna Windows dan VS Code, memindahkan tugas editing Git ke VS Code akan membuat hidupmu jauh lebih mudah.

### Perintah Konfigurasi:

Ketik ini di terminal untuk menjadikan VS Code sebagai editor utama Git:

```bash
git config --global core.editor "code --wait"

```

---

## 💻 Mengapa Harus Pakai Flag `--wait`?

Ini adalah poin yang bikin kamu penasaran tadi. Berikut alasan teknisnya:

* **Tanpa `--wait`:** Jika kamu hanya pakai `"code"`, Git akan membuka VS Code dan langsung menganggap tugasnya selesai. Akibatnya, Git akan mencoba memproses commit **sebelum** kamu sempat mengetik pesan apa pun. Akhirnya? Commit gagal atau pesannya kosong.
* **Dengan `--wait`:** Git akan "menahan diri" dan menunggu. Git baru akan melanjutkan prosesnya setelah kamu **menutup tab** file tersebut di VS Code. Ini memberi kamu waktu untuk mengetik, mengedit, dan menyimpan pesan dengan tenang.

---

## 🛠️ Kapan Git Membutuhkan Editor?

Mungkin kamu bertanya, *"Kan bisa pakai `git commit -m`?"*. Betul, tapi ada 3 kondisi di mana terminal saja tidak cukup:

### 1. Pesan Commit yang Panjang (Standard Professional)

Di perusahaan besar, commit tidak boleh cuma "update file". Biasanya ada format: **Judul, Penjelasan (Body), dan Footer (ID Task)**. Mengetik ini di Git Bash sangat tidak nyaman. Dengan VS Code, kamu bisa membuat dokumentasi commit yang rapi.

### 2. Resolusi Konflik (Merge Conflict)

Saat kodenya bentrok dengan milik teman, Git akan menandai file tersebut. Membuka file "berantakan" ini di VS Code jauh lebih mudah karena ada fitur **Highlighting** yang memberitahu bagian mana yang harus dihapus dan mana yang harus diambil.

### 3. Interactive Rebase

Ini adalah fitur "Cuci Gudang" Git. Digunakan untuk menggabungkan banyak commit kecil menjadi satu agar riwayat proyek terlihat rapi sebelum di-*push* ke GitHub. Proses ini butuh editor teks untuk memilih commit mana yang mau disimpan atau dihapus.

---

## 💡 Tips & Peringatan

> **Tips:** 
> Jika kamu terlanjur terjebak di dalam **VIM** (layar hitam dengan tanda `~`), jangan panik. Cara keluarnya: Tekan tombol `Esc`, lalu ketik `:q!` dan tekan `Enter`. Kamu akan keluar tanpa menyimpan perubahan.
>
> **Peringatan:** 
> Pastikan VS Code sudah terdaftar di **Path Windows** kamu (biasanya otomatis saat instalasi). Cara ceknya: ketik `code` di terminal. Jika VS Code terbuka, berarti aman!
>

---

[⬅️ Kembali ke Daftar Isi](../README.md)