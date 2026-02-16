# 📘 Bab 03: Mengenal Package Manager (Pip vs Conda)

> **Tujuan Belajar:**
> Memahami cara mengelola *library* pihak ketiga secara profesional dan menghindari konflik ketergantungan (*dependency*) antar proyek.

---

## 📖 1. Kenapa Butuh Package Manager?

Mungkin kamu terpikir untuk menyalin kode *library* secara manual. **Jangan.** Kamu akan terjebak dalam **Dependency Hell** (Neraka Dependensi).

* **Contoh:** Kamu ingin pakai *Library A*. Tapi *Library A* butuh *Library B* versi 2.0. Ternyata *Library B* butuh *Library C*.
* **Solusi:** Package manager secara otomatis mencarikan, mengunduh, dan merangkai semua "rantai" kebutuhan tersebut untukmu.

---

## ⚖️ 2. Duel Maut: Pip vs Conda

Sebagai arsitek, kamu harus tahu kapan memakai obeng (Pip) dan kapan memakai mesin bor (Conda).

| Fitur | Pip (Python Installs Packages) | Conda (Miniconda/Anaconda) |
| --- | --- | --- |
| **Sumber** | **PyPI** (Python Package Index). | Repo Conda & Cloud. |
| **Cakupan** | Hanya paket berbasis Python. | Paket Python + *System Tools* (C++, CUDA, dll). |
| **Bentuk Paket** | Seringkali berupa kode mentah (butuh CPU untuk *compile*). | Berupa **Binary** (sudah jadi, tinggal pasang, hemat CPU). |
| **Kecocokan** | Ringan, standar untuk Web/Backend. | Berat, standar untuk Data Science/AI berat. |

> **Architect Tips:** Jika RAM terbatas dan butuh Conda, gunakan **Miniconda**. Hindari **Anaconda Navigator** karena ia memakan RAM sangat besar hanya untuk tampilan visualnya saja.

---

## 🛠️ 3. Perintah "Sakti" `-m` (Module Mode)

Jangan langsung ketik `pip install`. Gunakanlah:

```bash
python -m pip install <nama_library>

```

**Kenapa?**
Jika di laptopmu ada lebih dari satu Python, perintah `pip` saja bisa salah sasaran. Menggunakan `python -m pip` memastikan *library* terpasang tepat pada "mesin" Python yang sedang kamu panggil saat itu.

---

## 🔍 4. Audit Library (Cek Daftar Bahan)

Sebelum mulai memasak kode, kamu harus tahu apa saja bahan yang sudah tersedia di gudangmu.

* **List (Tampilan Tabel):** Cocok untuk dibaca manusia.
```bash
python -m pip list

```


* **Freeze (Tampilan Versi):** Digunakan untuk membuat daftar `requirements.txt`.
```bash
python -m pip freeze

```


* **Show (Detail Spesifik):** Jika ingin tahu lokasi folder atau siapa pembuat library-nya.
```bash
python -m pip show <nama_library>

```



> **Catatan:** Jika terminalmu aktif di **Virtual Environment (venv)**, perintah di atas hanya akan menampilkan library di dalam env tersebut. Jika tidak aktif, yang muncul adalah library **Global**.

---

## 🤝 5. Kolaborasi & `requirements.txt`

Jangan pernah mengirim folder `site-packages` (folder tempat library disimpan) ke teman setim. Itu berat dan tidak profesional.

* **Cara Membuat Daftar Belanja:**
Catat semua *library* dan versinya ke sebuah file.

```bash
python -m pip freeze > requirements.txt

```

* **Cara Teman Menginstal:**
Temanmu cukup menjalankan satu perintah untuk meniru persis ekosistemmu:

```bash
python -m pip install -r requirements.txt

```

> **Pentingnya Versi (`pandas==1.1.1`):** Tanpa versi yang dikunci, Pip akan mengambil versi terbaru. Jika ada fungsi yang dihapus di versi terbaru, kodemu akan *crash*. Mengunci versi mencegah alasan klasik: *"Di laptopku jalan kok!"*

---

## ⚠️ Peringatan: Nama File "Terlarang"

Ini adalah kesalahan pemula yang bisa bikin sistem *error* total.
**JANGAN memberi nama file kamu sama dengan nama library.**

* **Contoh:** Kamu buat file `pandas.py` untuk latihan, padahal kamu sudah instal library `pandas`.
* **Hasilnya:** Saat kamu ketik `import pandas`, Python akan bingung dan mencoba mengimpor file buatanmu sendiri, bukan library aslinya. Programmu akan *error* seketika.

---

### 💡 Catatan Tambahan:

Di dunia AI akan sering bertemu library seperti **PyTorch** atau **TensorFlow**. Library ini butuh akses ke kartu grafis (GPU). Nah, di sinilah **Conda** biasanya menang karena ia bisa menginstal *driver* pendukung GPU secara otomatis, sedangkan **Pip** seringkali gagal di bagian ini.

---

[⬅️ Kembali ke Daftar Isi](../README.md)