# 📘 Bab 01: Apa Itu Version Control System (VCS)

> **Tujuan Belajar:**
> Memahami konsep dasar Version Control System sebagai pondasi manajemen proyek software dan AI.

---

## 📖 Teori Singkat
* **Konsep Mesin Waktu:** VCS secara umum diibaratkan sebagai mesin waktu yang merekam setiap perubahan pada file (atau sekumpulan file) dari waktu ke waktu. Hal ini memungkinkan kita untuk memanggil kembali versi spesifik dari proyek kita kapan saja.
* **Konsep Snapshot:** Git adalah salah satu sistem VCS. Yang membedakannya adalah cara Git mengelola riwayat menggunakan sistem **Snapshot**. Git mengambil "foto" seluruh keadaan proyek pada saat itu, bukan sekadar mencatat perubahan baris (delta). Hal ini membuat pemanggilan riwayat menjadi lebih cepat dan utuh.
* **Vcs vs Manual :** Kenapa tidak duplikat folder projek saja? selain karena ukuran projek bisa membengkak, kita juga akan sulit melacak perubahan mana yang mempengaruhi projek, sehingga tidak fleksibel.



---

## 🧪 Contoh Praktek & Output

1. **Pukul 10:00:** Kamu menambah fitur `X` di file A yang awalnya kosong. Status: **Sukses**. (Snapshot 1 dibuat).
2. **Pukul 11:00:** Kamu mengubah fitur `X` menjadi `C` di file A. Status: **Error/Bug**. (Snapshot 2 dibuat).
3. **Solusi:** Kamu melakukan "Teleportasi" kembali ke Snapshot 1 (Pukul 10:00).

**Hasil Akhir:**
`File A kembali ke kondisi Pukul 10:00 dengan fitur X yang berfungsi normal.`

---

## 💡 Tips & Peringatan

> **Tips:** Jika perubahan hanya 1 atau 2 baris yang baru saja diketik, `Ctrl+Z` sudah cukup. Namun, untuk eksperimen fitur atau perubahan besar, VCS adalah kewajiban agar kode tidak berantakan.
> **Peringatan:** Disiplin dalam melakukan *commit* (simpan snapshot) adalah kunci. Semakin sering kamu menyimpan snapshot yang bermakna, semakin aman pekerjaanmu dari risiko kehilangan data.

---

[⬅️ Kembali ke Daftar Isi](../README.md)