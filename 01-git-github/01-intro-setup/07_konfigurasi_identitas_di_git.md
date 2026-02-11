# 📘 Bab 07: Konfigurasi Identitas (user.name & user.email)

> **Tujuan Belajar:**
> Mengatur identitas diri di Git agar setiap perubahan kode memiliki "tanda tangan" yang jelas.

---

## 📖 Pengetahuan Dasar

- **Pentingnya Identitas:** Git menggunakan identitas ini untuk mencatat siapa yang melakukan perubahan (akuntabilitas). Jika bekerja dalam tim, ini membantu kita tahu siapa yang harus dihubungi jika ada kode yang bermasalah.
- **Global vs Local:**

  | Cakupan | Perintah | Kegunaan |
  | :--- | :--- | :--- |
  | **Global** | `--global` | Berlaku untuk semua proyek di laptopmu. (Paling sering digunakan). |
  | **Local** | (Tanpa flag) | Hanya berlaku untuk satu folder proyek tertentu saja. |

---

## 💻 Perintah & Kode Latihan

### 1. Mengatur Identitas Global (Wajib dilakukan sekali)
Gunakan perintah ini agar semua proyekmu menggunakan identitas yang sama:
```bash
git config --global user.name "Nama Lengkap Kamu"
git config --global user.email "emailkamu@example.com"
```

### 2. Verifikasi Konfigurasi

Untuk memastikan nama dan emailmu sudah terdaftar, gunakan:

```bash
git config --list
```

---

## 💡 Tips & Peringatan

> **Tips:**
> Pastikan email yang kamu daftarkan **sama persis** dengan email akun GitHub-mu. Ini penting agar setiap *commit* yang kamu kirim terbaca sebagai kontribusi resmi dan memunculkan **"Green Dots"** (grafik hijau) di profil GitHub-mu.
> **Peringatan:**
> * Jika namamu mengandung spasi, **wajib** gunakan tanda kutip dua `" "`.
> * Periksa kembali typo sebelum menekan Enter. Identitas ini akan menempel secara permanen pada sejarah *commit* yang kamu buat.
> 
> 

---

[⬅️ Kembali ke Daftar Isi](../README.md)