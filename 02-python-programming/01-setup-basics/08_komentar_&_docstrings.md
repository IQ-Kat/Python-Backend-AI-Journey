# 📘 Bab 08: Dokumentasi Kode (Komentar & Docstrings)

> **Tujuan Belajar:**
> Memahami perbedaan fungsional antara komentar dan Docstrings, serta menerapkan filosofi *"Why, Not What"* untuk menciptakan kode yang mudah dipelihara dan dipahami secara arsitektural.

---

## 📖 Teori Singkat

### 🛠️ Jenis Dokumentasi di Python

* **Komentar Satu Baris (`#`):** Digunakan untuk catatan teknis singkat.
* *Own-line:* Di atas kode.
* *Inline:* Di ujung baris (minimal 2 spasi dari kode).


* **Komentar Multi-baris:** Di Python, standar profesional adalah menggunakan tanda `#` berulang di setiap baris, bukan petik tiga.
* **Docstrings (`"""`):** Dokumentasi formal yang menjadi bagian dari objek Python. Disimpan di RAM dan bisa diakses saat *runtime*.

### 🧠 Filosofi "Why, Not What"

Kesalahan fatal pemula adalah menjelaskan **apa** yang dilakukan kode (yang sudah jelas terlihat). Seorang Architect menjelaskan **mengapa** kode tersebut ditulis seperti itu (logika bisnis, batasan hardware, atau alasan teknis).

---

## 💻 Perintah & Kode Latihan

### ⌨️ Terminal (Inspeksi Live)

Kamu bisa melihat dokumentasi fungsi apapun (bawaan atau buatan sendiri) langsung dari terminal Python:

```bash
# Masuk ke mode interaktif
python

# Di dalam python:
import os
help(os.path) # Melihat Docstring library os

```

### 🐍 Python Snippet (Penerapan Standar)

Salin ini ke `src/main.py` untuk melihat perbedaan cara kerja keduanya:

```python
# --- KOMENTAR (#) ---
# Menggunakan offset 0.02 karena deviasi hardware i3 pada suhu tinggi
hasil_sensor = 10.5 + 0.02 

# --- DOCSTRINGS (""") ---
def aktifkan_performa():
    """Mengoptimalkan P-Cores pada i3-1215U untuk pemrosesan AI."""
    pass

# Membuktikan Docstring ada di memori
print(aktifkan_performa.__doc__)

```

---

## 🧪 Contoh Praktek & Output

1. Buat fungsi dengan Docstring lengkap.
2. Panggil atribut `.__doc__` pada fungsi tersebut.
3. **Hasil yang muncul di layar:**
`Mengoptimalkan P-Cores pada i3-1215U untuk pemrosesan AI.`

---

## 💡 Tips & Peringatan

> **Tips: Why, Not What!**
> Jangan tulis `# Tambah satu ke x`. Tulis `# Kompensasi untuk offset sensor`. CPU i3-mu sudah tahu itu penjumlahan; manusia butuh tahu alasan di baliknya.
> **Peringatan: Documentation Debt!**
> Menunda menulis dokumentasi sama dengan menumpuk hutang. Semakin besar proyek `AI_Model`-mu, semakin sulit mengingat logika lama. Tulis Docstring **saat itu juga** ketika fungsi dibuat.

---

[⬅️ Kembali ke Daftar Isi](../README.md)