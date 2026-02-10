```markdown
# 📘 Bab 02: Perbedaan Centralized vs Distributed VCS

> **Tujuan Belajar:**
> Memahami 2 era besar vcs, antara Centralized atau Terpusat dengan Distributed atau Tersebar

---

## 📖 Teori Singkat
* **Konsep CVCS:** Sistem ini menggunakan server pusat sebagai penyimpanan riwayat dimana pengguna hanya punya 1 salinan file yang sedang dikerjakan, sehingga harus selalu online untuk melakukan `commit`, atau pun melakukan perbandingan perubahan, dan jika server pusat rusak maka semua data juga rusak jika tanpa backup.
* **Konsep DVCS:** Secara sederhana sistem ini(salah satunya Git) melakukan sistem tersebesar dimana baik server dan laptopmu punya file dengan kelengkapan yang sama, sehingga bisa melakukan `commit` dll secara offline, dan bisa melakukan push(update) ke server saat online nanti, ini juga jauh lebih aman karena jika server rusak, maka sebagian besar data aman karena tersimpan lokal di laptopmu.

---

## 💡 Tips & Peringatan

> **Tips:** Dengan sistem DVCS kamu bebas membuat branch untuk eksperimen secara offline sehingga tidak akan mengganggu sistem utama
> **Peringatan:** Jika bekerja dengan Tim selalu pastikan untuk melakukan `git fetch` atau `git pull` agar data server dan laptopmu selalu sinkron

---

[⬅️ Kembali ke Daftar Isi](../README.md)