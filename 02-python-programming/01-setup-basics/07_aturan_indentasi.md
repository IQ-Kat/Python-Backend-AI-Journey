# 📘 Bab 07: Hukum Spasi (Indentasi) & Estetika Kode

> **Tujuan Belajar:**
> Memahami filosofi *Whitespace as Syntax*, menerapkan standar PEP 8 (4 spasi), dan mengonfigurasi VS Code agar otomatis menangani masalah indentasi untuk menghindari *runtime error* yang konyol.

---

## 📖 Teori Singkat

### 🏛️ Filosofi Whitespace as Syntax

Python menganut prinsip bahwa **kode lebih sering dibaca daripada ditulis**. Tanpa kurung kurawal `{ }`, Python memaksa programmer menulis kode yang rapi secara visual agar bisa dijalankan.

* **Tanda Titik Dua (`:`):** Adalah gerbang masuk ke sebuah blok kode (anak).
* **Indentasi:** Adalah pembatas ruang lingkup (*scope*). Kode yang menjorok ke kanan adalah "anak" dari baris di atasnya.

### ⚔️ Perang Suci: Spaces vs Tabs (PEP 8)

Standar industri **PEP 8** menetapkan aturan mutlak: **Gunakan 4 Spasi**, jangan gunakan tombol Tab murni.

* **Masalah Tab:** Karakter `\t` (Tab) bersifat relatif. Di VS Code terlihat rapi (4 spasi), tapi di server Linux atau GitHub bisa terlihat lebar (8 spasi), merusak estetika dan keterbacaan.
* **Spasi bersifat Absolut:** 1 spasi akan selalu berjarak 1 karakter di layar mana pun di seluruh dunia.

---

## 💻 Perintah & Kode Latihan

### ⌨️ Terminal (Check & Fix)

Meskipun kita mengedit di VS Code, kadang kita perlu memeriksa apakah ada "karakter siluman" (Tab) yang menyelinap di file kita via terminal:

```bash
# Mencari apakah ada karakter Tab di dalam file main.py (Linux/Git Bash)
grep -P "\t" src/main.py

```

### 🐍 Python Snippet (Hirarki Blok)

Salin kode ini ke `src/main.py` untuk melihat bagaimana Python memproses "keluarga" blok kode:

```python
# Level 0: Baris Utama
if True:
    # Level 1: Anak dari IF (4 spasi)
    print("Saya adalah anak pertama") 
    
    if 5 > 2:
        # Level 2: Cucu dari IF utama (8 spasi)
        print("Saya adalah cucu, sangat menjorok ke kanan")

# Kembali ke Level 0
print("Saya sudah di luar semua blok")

```

---

## 🧪 Contoh Praktek & Output

### 📑 Tabel Diagnosa Error Indentasi

| Nama Error | Penyebab | Analogi Arsitek |
| --- | --- | --- |
| `expected an indented block` | Ada `:` tapi baris bawahnya sejajar (tidak menjorok). | Ada pintu, tapi tidak ada ruang di baliknya. |
| `unexpected indent` | Baris tiba-tiba menjorok tanpa ada perintah `:` sebelumnya. | Ada ruangan melayang tanpa pintu masuk. |
| `unindent does not match...` | Spasi penutup tidak sejajar dengan pembukanya. | Pintunya miring, tidak bisa ditutup rapat. |
| `TabError` | Mencampur Tab dan Spasi dalam satu file. | Menggunakan baut inci dan baut metrik di satu mesin. |

---

## 💡 Tips & Peringatan

> **Tips: Aktifkan Radar VS Code!** > Buka Settings (`Ctrl + ,`), cari **"Render Whitespace"**, dan ubah ke **"all"**. Kamu akan melihat titik-titik kecil sebagai penanda spasi. Pastikan juga **"Insert Spaces"** tercentang agar tombol Tab-mu otomatis menjadi 4 spasi (*Soft Tabs*).
>
> **Peringatan: Deep Nesting Danger!**
> Jika kodemu menjorok sampai lebih dari 4 level ke kanan, itu tanda arsitektur logikamu terlalu rumit. Segera pecah menjadi fungsi-fungsi kecil agar tidak terjadi "kelelahan visual" saat membaca kode.

---

[⬅️ Kembali ke Daftar Isi](../README.md)