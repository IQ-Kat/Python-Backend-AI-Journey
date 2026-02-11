# 📘 Bab 06: Terminal/Command Line Dasar

> **Tujuan Belajar:**
> Menguasai navigasi dan perintah dasar terminal untuk efisiensi kerja.

---

## 📖 Pengetahuan & Filosofi Dasar

- **Filosofi CLI (Command Line Interface):** Digunakan karena sangat hemat RAM (hanya beberapa KB) dibandingkan GUI (Windows Explorer) yang butuh alokasi RAM besar untuk rendering visual.
- **`pwd` (Print Working Directory):** Mengetahui posisi kita saat ini (alamat lengkap/Absolute Path).
- **`ls` (List):** Melihat daftar file dan folder di lokasi saat ini.
- **`cd` (Change Directory):** Berpindah antar folder.
- **`mkdir` (Make Directory):** Membuat folder baru.

---

## 💻 Daftar Perintah (Bash)

| Perintah | Fungsi | Contoh/Keterangan |
| :--- | :--- | :--- |
| `pwd` | Cek posisi | Output: `/c/Users/Ikbal/Project/AI` |
| `ls` | List standar | Menampilkan nama file/folder saja. |
| `ls -l` | List detail | Menampilkan ukuran, hak akses, dan tanggal. |
| `ls -a` | List tersembunyi | Menampilkan file `.git` atau `.env` yang disembunyikan. |
| `ls -lh` | List manusiawi | Ukuran file muncul dalam KB/MB (bukan byte). |
| `ls -h` | **AWAS!** | (PowerShell) Hanya menampilkan file Hidden. |
| `cd nama_folder` | Masuk folder | `cd documents` |
| `cd ..` | Naik satu tingkat | Kembali ke folder induk (parent). |
| `cd ~` | Pulang ke Home | Langsung kembali ke folder User utama. |
| `cd -` | Back | Kembali ke folder yang diakses sebelumnya. |
| `mkdir nama` | Buat folder | `mkdir catatan` |
| `mkdir -p a/b` | Buat bertingkat | Membuat folder `a` sekaligus folder `b` di dalamnya. |



---

## 💡 Tips & Peringatan

> **Tips:** 
> * **Arrow Up/Down:** Tekan panah atas/bawah untuk memanggil kembali perintah yang sudah pernah diketik.
> * **Tab Completion:** Ketik 2-3 huruf awal folder lalu tekan **TAB** untuk melengkapi nama otomatis. Ini cara paling ampuh menghindari typo!
> * **Brace Expansion:** Gunakan `mkdir -p projek/{folder1,folder2/isifolder2}` gunakan untuk membuat 1 folder dengan 2 jalur folder sekaligus, tentu bisa juga menggunakan `mkdir -p projek/folder1 projek/folder2/isifolder2`, cara pertama lebih bersih.
>
> **Peringatan:** 
> * **Case Sensitivity:** Di Git Bash, `Projek` dan `projek` itu berbeda. Biasakan gunakan **huruf kecil semua**.
> * **Windows Trap:** Meskipun Bash sensitif, ia tetap tunduk pada OS Windows. Kamu tidak bisa membuat folder `projek` dan `Projek` di lokasi yang sama karena Windows akan menganggapnya duplikat.
> * **Hindari Spasi:** Jangan gunakan spasi pada nama file/folder (contoh: `catatan hari ini.md`). Gunakan tanda hubung atau garis bawah (`catatan-hari-ini.md`).

---

[⬅️ Kembali ke Daftar Isi](../README.md)