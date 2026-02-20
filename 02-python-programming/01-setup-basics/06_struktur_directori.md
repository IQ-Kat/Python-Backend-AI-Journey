# 📘 Bab 06: Arsitektur Proyek & Standar Industri

> **Tujuan Belajar:**
> Mengimplementasikan prinsip *Separation of Concerns* (SoC) dan pola *src/ layout* untuk menciptakan proyek yang skalabel, profesional, dan aman dari kebocoran data.

---

## 📖 Teori Singkat

### 🧱 Filosofi Separation of Concerns (SoC)

Prinsip ini menjaga agar setiap bagian kode memiliki "tanggung jawab" yang terisolasi.

* **Logic:** Kode inti (algoritma/fungsi).
* **Data:** File CSV, database, atau aset gambar.
* **Config:** Pengaturan rahasia (API Key/Password).
* **Tests:** Kode penguji agar tidak mengotori produksi.

### 🏗️ Pola src/ Layout vs Flat Layout

| Karakteristik | Flat Layout (Pemula) | src/ Layout (Professional) |
| --- | --- | --- |
| **Struktur** | Semua `.py` di root folder. | Kode inti masuk ke folder `src/`. |
| **Keamanan** | Risiko *Namespace Collision*. | Terhindar dari bentrok nama library. |
| **Deployment** | Sulit memisahkan kode vs tes. | Sangat mudah dipaketkan ke server. |

---

## 💻 Perintah & Kode Latihan

### ⌨️ Terminal (Struktur Manual)

Gunakan perintah ini untuk membangun pondasi proyek `AI_Model` kamu dalam sekali jalan:

```bash
# Membuat struktur folder inti
mkdir src tests data logs

# Membuat file fundamental
touch README.md .gitignore requirements.txt .env src/__init__.py

# Trik .gitkeep agar folder kosong ikut terbawa ke GitHub
touch logs/.gitkeep data/.gitkeep

```

### 🐍 Python Snippet (Contoh .env Loading)

Jangan pernah tulis API Key kamu langsung di kode. Gunakan cara ini:

```python
# Di dalam file src/main.py
import os
from dotenv import load_dotenv

# Memuat variabel dari file .env
load_dotenv()

API_KEY = os.getenv("API_KEY")
print(f"API Key berhasil dimuat: {API_KEY[:5]}***") # Jangan print seluruhnya!

```

---

## 🧪 Contoh Praktek & Output

### 📂 The Architect Blueprint (Struktur Akhir)

Jika kamu menjalankan `tree` atau melihat Sidebar VS Code, beginilah rupa proyek profesional:

```plaintext
my_project/
├── .env                  <-- Rahasia (API Keys)
├── .gitignore            <-- Satpam Git
├── README.md             <-- Brosur Proyek
├── requirements.txt      <-- Daftar Belanja
├── src/                  <-- Jantung Aplikasi
│   └── my_app/
│       ├── __init__.py
│       └── main.py
├── tests/                <-- Lab Pengujian
│   └── test_main.py
├── data/                 <-- Gudang Data
└── logs/                 <-- Catatan Operasi

```

---

## 💡 Tips & Peringatan

> **Tips:** Gunakan **Logger** daripada `print()`. Mencetak jutaan baris ke terminal (stdout) pada i3-1215U akan membuat proses melambat karena beban I/O terminal. Menulis ke file di folder `logs/` jauh lebih cepat.
> **Peringatan:** **Dilarang keras** mengunggah file `.env` ke GitHub. Sekali terunggah, API Key kamu bisa dicuri orang dan kuotamu akan habis dalam sekejap! Pastikan `.env` sudah tertulis di `.gitignore`.

---

[⬅️ Kembali ke Daftar Isi](../README.md)