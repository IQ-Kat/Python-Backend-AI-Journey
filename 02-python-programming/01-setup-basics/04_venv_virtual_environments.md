# 📘 Bab 04: Virtual Environments (Venv) - Ruang Isolasi

> **Tujuan Belajar:**
> Menciptakan ekosistem mandiri untuk setiap proyek agar tidak terjadi konflik antar *library* dan menjaga sistem utama tetap bersih.

---

## 🏗️ 1. Kenapa Wajib Pakai Venv?

Bayangkan Global Python adalah **Ruang Tamu** rumahmu. Kamu tidak ingin menaruh tumpukan material bangunan (library proyek) di sana, kan?

* **Isolasi:** Setiap proyek punya "gudang" sendiri. Proyek A bisa pakai Pandas versi lama, Proyek B pakai versi terbaru tanpa saling merusak.
* **Kebersihan:** Menjaga Global Python tetap "suci" adalah standar profesional. Global hanya boleh berisi alat dasar seperti `pip`, `setuptools`, dan `virtualenv`.

---

## 🔍 2. Anatomi Venv (Isi Perut si Gudang)

Saat kamu membuat venv, akan muncul 4 komponen utama:

| Komponen | Fungsi |
| --- | --- |
| **`Lib/`** | **Jantung Venv.** Di sinilah 90% library yang kamu instal (lewat `pip`) akan disimpan. |
| **`Scripts/`** | Berisi salinan `python.exe` dan skrip untuk mengaktifkan/mematikan venv. |
| **`Include/`** | Folder untuk library yang membutuhkan kompilasi bahasa C (jarang disentuh manual). |
| **`pyvenv.cfg`** | File konfigurasi yang memberitahu sistem: *"Gunakan alat di sini, jangan lihat ke Global!"* |

---

## ⌨️ 3. Perintah Eksekusi (Standard Bash)

Sebagai pengguna Git, kita akan fokus menggunakan **Git Bash** agar konsisten:

1. **Membuat Venv:**
```bash
python -m venv .venv

```


*Tips: Gunakan awalan titik (`.venv`) agar folder tersembunyi dan mudah dikenali oleh VS Code.*
2. **Mengaktifkan (Activation):**
```bash
source .venv/Scripts/activate

```


*(Akan muncul tanda `(.venv)` di depan baris terminalmu).*
3. **Mematikan (Deactivation):**
```bash
deactivate

```



---

## ⚠️ Aturan Emas: Larangan Pindah Folder

Venv sangat sensitif soal **Absolute Path** (Alamat Lengkap). Saat dibuat, venv mencatat lokasi folder saat itu (misal: `C:\Project\AI_Model`).

* **Masalah:** Jika kamu memindahkan folder `AI_Model` ke `D:\Backup`, venv akan rusak karena dia masih mencari "jalan pulang" ke folder C.
* **Solusi:** Jika terpaksa pindah folder:
1. Hapus folder `.venv` yang lama.
2. Pindahkan folder proyeknya.
3. Buat ulang venv baru dan instal ulang library via `requirements.txt`.
*Tenang, proses ini cepat karena Pip punya sistem **Cache** (dia tidak download ulang dari internet, tapi ambil dari simpanan lokal).*



---

## 🛠️ Tips & Troubleshooting

### A. Masalah Izin di PowerShell

Jika kamu terpaksa pakai PowerShell dan dilarang menjalankan skrip, jalankan ini sekali saja sebagai Administrator:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

```

### B. Kapan Harus Pindah ke Conda?

Jika `pip` gagal menginstal library berat (biasanya karena masalah kompilasi C++ yang rumit), itulah saatnya kamu menggunakan **Conda Environment**. Conda jauh lebih berat, tapi "sakti" karena ia mengunduh paket yang sudah jadi (binary).

---

## 💡 Arsitek Note:

Dengan RAM 16GB dan CPU i3, strategi kamu menggunakan `venv` adalah yang paling efisien. Satu venv hanya memakan sekitar **15MB - 100MB** di SSD, jauh lebih hemat daripada membuat kontainer Docker atau lingkungan Conda yang bisa memakan Gigabyte.

---

