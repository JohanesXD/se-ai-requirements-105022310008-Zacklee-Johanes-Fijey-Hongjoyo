# Stakeholder Interview Q&A - Student Task Management System

Berikut adalah jawaban dari pertanyaan wawancara lanjutan dengan stakeholder untuk menggali kebutuhan lebih mendalam:

## 1. Wawancara dengan Dosen (Dr. Budi Santoso)
* **Pertanyaan**: Bagaimana Bapak ingin mengunduh tugas mahasiswa yang sudah dikumpulkan?
  * **Jawaban**: Saya ingin bisa mengunduh berkas satu per satu untuk diperiksa, tetapi saya juga sangat butuh fitur untuk mengunduh semua berkas mahasiswa dalam satu kelas sekaligus sebagai satu file ZIP agar hemat waktu.
* **Pertanyaan**: Apakah ada batas waktu penambahan nilai dan umpan balik setelah tugas dikumpulkan?
  * **Jawaban**: Tidak ada batasan sistem yang kaku, tetapi saya ingin sistem memberikan tanda status jika ada tugas mahasiswa yang belum dinilai agar saya tidak terlewat. Nilai yang diinput harus berupa angka bulat dari 0 hingga 100.
* **Pertanyaan**: Apakah dosen lain boleh melihat kelas yang Bapak ajar?
  * **Jawaban**: Tidak. Dosen hanya boleh melihat, membuat tugas, dan menilai kelas di mana dia terdaftar sebagai dosen pengampu kelas tersebut.

## 2. Wawancara dengan Mahasiswa (Rian & Siska)
* **Pertanyaan**: Apakah Anda perlu mengetahui jika berkas yang diunggah rusak atau tidak terbaca?
  * **Jawaban**: Ya, sistem harus menampilkan pratonton (*preview*) file jika memungkinkan (misal untuk file PDF), atau setidaknya menunjukkan ukuran file yang terunggah untuk memastikan file tidak berukuran 0 KB.
* **Pertanyaan**: Bagaimana Anda ingin mengetahui adanya tugas baru atau nilai yang baru dimasukkan oleh dosen?
  * **Jawaban**: Kami sangat ingin ada notifikasi di dalam aplikasi (lonceng notifikasi) dan juga notifikasi email otomatis agar kami langsung tahu jika ada nilai yang masuk.
* **Pertanyaan**: Apakah ada aturan penamaan file tugas saat dikumpulkan?
  * **Jawaban**: Lebih baik jika sistem secara otomatis merubah nama file yang diunggah mahasiswa menjadi format standar (misal: `NIM_Nama_TugasID.ekstensi`) untuk menghindari kebingungan dosen saat mengunduh banyak file.

## 3. Wawancara dengan Administrator (Ibu Ambar)
* **Pertanyaan**: Bagaimana struktur file impor pengguna (Excel/CSV) yang Anda harapkan?
  * **Jawaban**: Kolomnya harus berisi: NIM/NIDN (sebagai username sekaligus ID), Nama Lengkap, Email, Peran (Dosen/Mahasiswa/Admin), dan Kelas.
* **Pertanyaan**: Apakah ada fitur penonaktifan pengguna?
  * **Jawaban**: Ya, jika mahasiswa lulus atau dosen pensiun, akun mereka tidak boleh dihapus secara permanen dari database karena nilai mereka harus tetap tersimpan secara historis. Akun tersebut cukup dinonaktifkan (*suspended*) sehingga tidak bisa login lagi.
