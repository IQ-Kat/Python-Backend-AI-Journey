# 📘 Bab 04: Mengapa Data Scientist/AI Engineer butuh Git?

> **Tujuan Belajar:**
> Alasan harus menggunakan Git

---

## 📖 Catatan Singkat

- **Reproduksibilitas:** Standar emas sains data, karena hasil yang hebat tapi tidak bisa diulang tidak ada gunanya, Git membantu untuk mengulang ke bagian paling unggul dari hasil perubahanmu tanpa merusak kode yang ada.
- **Eksperimentasi Non-Linear (Branching):** AI Engineering selalu mencoba berbagai eksperimen, dengan git yang punya sistem branching atau sederhananya ruang isolasi, kita bisa selalu melakukan eksperimen tanpa merusak atau mencampuri kode utama, bahkan tidak membebani penyimpanan tidak seperti sistem copy paste projek, dan kita bisa menyatukan eksperimen yang unggul ke projek utama.
- **Collaboration & Code Review dalam AI Pipeline:** Dalam kerja Tim, setiap perubahan logika sebelum di terapkan selalu dilakukan pemeriksaan, dengan git pemeriksan pada perubahan logika bisa dilakukan dengan fleksibel tanpa harus kamu membawa laptopmu ke rekan tim
- **Melacak Environment (Dependency Tracking):** Model AI sangat sensistif dengan versi library, sehingga git membantu dalam menyimpan requirements.txt atau environment.yml sehingga rekan setim ataupun dirimu di masa depan selalu menggunakan versi library yang tepat

---

## 💡 Tips & Peringatan

> **Tips:** Selalu commit perubahan pada file dependensi setiap kali kamu melakukan `pip install` baru. Ini memastikan laptop i3 rekanmu atau server di Cloud nantinya akan menjalankan kode dengan kondisi yang identik dengan laptopmu.
> **Peringatan:**
> * **Jupyter Notebook (.ipynb):** File ini sebenarnya adalah JSON raksasa. Jika kamu mengubah satu cell, Git akan mendeteksi banyak sekali perubahan teknis (metadata) yang sulit dibaca manusia.Jangan Commit file Jupyter Notebook (.ipynb) jika tidak ada perubahan kode atau logika di dalamnya.
> * **Binary Data:** Git tidak dirancang untuk menyimpan dataset 10GB atau model .pth yang sangat berat. Git hanya menyimpan pointernya saja(bayangkan saja dia hanya menyimpan alamat atau resep) jika menggunakan Git LFS atau DVC namun secara default dia akan memaksa menyimpan full jadi bisa bisa .git membengkak hingga bergiga-giga

---

[⬅️ Kembali ke Daftar Isi](../README.md)
