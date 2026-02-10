# 📘 Bab 03: Sejarah Singkat Git

> **Tujuan Belajar:**
> Untuk memahami mengapa git bisa seperti sekarang, kita akan mundur ke tahun 2005

---

## 📖 Teori Singkat
* **Kelahiran Git:** Pada Tahun 2005 BitMover mencabut lisensi BitKeeper untuk para komunitas pengembang kernel linux karena salah satu dari mereka mencoba membongkar protokol BitKeeper, sehingga Linus Torvalds pencipta linux harus mencari alternatif, alih alih membayar lisensi, Linus memilih membuat Git yang mirip dengan BitKeeper sebuah Vcs berbasis Distributed.
* **Keunggulan Git:** Meski mengikuti BitKeeper, Git punya keunggulan di anataranya
1. Kecepatan adalah kewajiban di Git, dimana dia menyempurnakan sistem snapshot sehingga lebih cepat, dan indexing yang lebih agresif
2. Keamanan menggunakan hashing berbasis SHA-1 yang melacak setiap perubahan id pada kode walau hanya 1 kode
3. Selain terdisribusi atau berbasis DVCS, Git juga open source sehingga para pengembang tak perlu khawatir soal lisensi, bahkan pengaruh yang dapat mengganggu proyek mereka.

---

## 💡 Tips & Peringatan

> **Tips:** Sistem SHA-1 saat ini bisa di tembus meski kemungkinannya sangat rendah, namun pihak Git mulai mempersiapkan migrasi ke sistem keamanan berbasis SHA-256

---

[⬅️ Kembali ke Daftar Isi](https://www.google.com/search?q=../README.md)