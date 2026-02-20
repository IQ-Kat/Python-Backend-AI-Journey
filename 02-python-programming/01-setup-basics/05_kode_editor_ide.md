# 📘 Bab 05: Ekosistem Pengembangan & Persiapan Senjata

> **Tujuan Belajar:**
> Memahami perbedaan arsitektur antara Text Editor, IDE, dan Notebook agar bisa memilih alat yang paling optimal untuk hardware i3-1215U dan menjaga performa laptop tetap stabil.

---

## 📖 Teori Singkat

### 🏎️ Perbandingan Arsitektur Alat

* **Text Editor (Notepad):** Hanya kanvas kosong. Tidak punya intelijen untuk mendeteksi kesalahan sintaks.
* **Enhanced Editor (VS Code):** Ringan, berbasis *Asynchronous*. Fitur berat berjalan di proses terpisah, sehingga tidak membuat macet proses mengetik. Sangat efisien untuk CPU Hybrid (E-cores menangani ekstensi, P-cores menangani UI).
* **IDE (PyCharm):** Pabrik lengkap. Melakukan **Indexing** (pemetaan kode) secara mendalam. Sangat kuat untuk *refactoring* (mengubah struktur kode besar) tapi memakan banyak *resource*.
* **Jupyter Notebook:** Laboratorium interaktif. Menggunakan sistem **Kernel** dan **Cells** untuk eksekusi kode per bagian.

---

## 💻 Perintah & Kode Latihan

### ⌨️ Terminal (Monitoring & Cleanup)

Gunakan perintah ini untuk memantau "kesehatan" laptopmu saat proses koding berlangsung:

```bash
# Mengecek proses Python yang berjalan (mencari 'zombie process' dari Jupyter)
tasklist | findstr python

# Membuka Process Explorer internal VS Code (Shortcut: Shift + Esc di dalam VS Code)
# Gunakan ini untuk mematikan ekstensi yang memakan CPU berlebihan

```

### 🐍 Python Snippet (Memory Test di Jupyter)

Gunakan kode ini di Jupyter untuk memahami bagaimana RAM 16GB-mu "terkunci" oleh Kernel:

```python
# Simulasi penggunaan RAM besar
data_sampah = [i for i in range(10000000)] 
print("Data berhasil dimuat ke RAM")

# Meskipun cell ini dihapus, RAM tidak akan bebas 
# sebelum kamu klik 'Restart Kernel'

```

---

## 🧪 Contoh Praktek & Output

1. **Skenario:** Menjalankan PyCharm untuk pertama kali.
2. **Proses:** Muncul progress bar di pojok kanan bawah bertuliskan "Indexing...".
3. **Hasil di layar:**
`CPU Usage: 90-100% (P-Cores Active)`
`Status: Laptop mungkin terasa hangat dan fan berputar kencang.`
*(Setelah 1-2 menit, penggunaan CPU akan turun kembali ke normal).*

---

## 💡 Tips & Peringatan

> **Tips:** Gunakan **VS Code Profiles** untuk memisahkan ekstensi Python AI dengan ekstensi lainnya agar VS Code tetap ringan saat dijalankan.
>
> **Peringatan:** Jangan pernah menyimpan **Secret Key** (API Key, Password DB) di dalam file `.ipynb` (Jupyter). File ini adalah JSON transparan; datamu akan sangat mudah bocor saat di-*upload* ke GitHub!

---

[⬅️ Kembali ke Daftar Isi](../README.md)
