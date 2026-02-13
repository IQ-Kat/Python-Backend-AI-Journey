# 📘 Bab 09: Audit & Manajemen Konfigurasi Git

> **Tujuan Belajar:**
> Memahami hirarki pengaturan Git dan cara melakukan audit jika terjadi konflik konfigurasi.

---

## 📖 1. Tiga Level Konfigurasi

Git memiliki tingkatan otoritas dalam menyimpan pengaturan. Level yang lebih spesifik akan selalu mengalahkan level yang lebih umum.

| Level | Cakupan | Lokasi Umum di Windows |
| --- | --- | --- |
| **System** | Semua user di satu PC. | `C:\Program Files\Git\etc\gitconfig` |
| **Global** | Semua proyek milik user kamu. | `C:\Users\Ikbal\.gitconfig` |
| **Local** | Hanya berlaku di 1 proyek aktif. | `.git/config` (di dalam folder proyek) |

---

## 💻 2. Cara Melakukan Audit (Cek Isi)

Jangan hanya menebak, gunakan perintah ini untuk melihat apa yang sedang terjadi di balik layar:

* **Cek Semua List:**
`git config --list`
* **Cek Lokasi Fisik (GPS Git):**
`git config --list --show-origin`
*Gunakan ini jika kamu bingung: "Ini email kok masih email lama ya, padahal sudah saya ganti?" Perintah ini akan menunjukkan di file mana settingan lama itu bersembunyi.*

---

## 🛠️ 3. Mengedit Manual dengan VS Code

Berkat settingan `code --wait` di bab sebelumnya, kamu bisa mengedit file konfigurasi seperti mengetik di Notepad:

```bash
git config --global --edit

```

* **Aturan Main:** Kamu akan melihat teks di dalam kurung siku seperti `[user]` atau `[core]`. Ini disebut **Section**. Jangan hapus tanda kurung ini agar formatnya tidak rusak.
* **Prinsip "Data Terakhir Menang":** Jika di dalam satu file ada dua `user.name`, Git akan menggunakan baris yang paling bawah (paling terakhir dibaca).

---

## 🔐 4. Credential Manager

Jika saat `git config --list` kamu melihat tulisan:
`credential.helper=manager`

Itu artinya kamu aman! Windows akan menyimpan *token/password* GitHub kamu di **Windows Credential Manager**. Kamu tidak perlu mengetik password berulang kali setiap melakukan `push`.

---

## 💡 Tips & Peringatan

> **Tips:**
> Jika kamu sedang mengerjakan proyek kantor dan ingin menggunakan email kantor (khusus di folder itu saja), jangan gunakan `--global`. Cukup ketik `git config user.email "email@kantor.com"` di dalam folder proyek tersebut. Ini akan masuk ke level **Local**.
>
> **Peringatan:**
> Hati-hati saat mengedit secara manual (`--edit`). Salah menghapus satu karakter atau tanda kutip bisa menyebabkan Git memunculkan error saat kamu menjalankan perintah apapun.

---

### Sedikit Penjelasan Tambahan (Biar Makin Jago):

Kenapa ada aturan **Local menimpa Global**?
Bayangkan Global itu adalah "Peraturan Rumah" (semua orang harus mandi), tapi Local itu adalah "Peraturan Kamar" (di kamar ini boleh tidak pakai handuk). Selama kamu ada di dalam kamar (folder proyek), maka peraturan kamarlah yang berlaku, bukan peraturan rumah.

---

[⬅️ Kembali ke Daftar Isi](../README.md)