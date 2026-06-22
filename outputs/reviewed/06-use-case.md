# Use Case Specification: Student Task Management System

## 1. Use Case Diagram Overview
Sistem ini memfasilitasi hubungan antara 3 aktor utama (Lecturer, Student, Administrator) dengan minimal 8 use cases sebagai berikut:
- **Lecturer**: UC-01 (Create Assignment), UC-03 (View Assignments), UC-04 (Grade Submission & Feedback), UC-07 (Download Bulk Submissions ZIP).
- **Student**: UC-02 (Submit Assignment), UC-03 (View Assignments), UC-08 (Cancel Submission / Unsubmit).
- **Administrator**: UC-05 (Import Users Massally), UC-06 (Suspend Account).

---

## 2. Use Case Descriptions

### UC-01: Create Assignment (Dosen)
- **Actor**: Lecturer (Dosen)
- **Pre-condition**: Dosen sudah masuk (*logged in*) ke sistem dan berada pada halaman kelas yang diampunya.
- **Post-condition**: Tugas baru berhasil dibuat dan dapat dilihat oleh mahasiswa yang terdaftar di kelas tersebut.
- **Main Flow**:
  1. Dosen mengklik tombol "Create Assignment".
  2. Sistem menampilkan form pembuatan tugas (Judul, Instruksi, Tenggat Waktu).
  3. Dosen mengisi data tugas secara lengkap dan menentukan *deadline*.
  4. Dosen mengklik "Publish Assignment".
  5. Sistem memvalidasi data input, menyimpan data tugas ke database, dan menampilkan pesan sukses.

---

### UC-02: Submit Assignment (Mahasiswa)
- **Actor**: Student (Mahasiswa)
- **Pre-condition**: Mahasiswa sudah masuk (*logged in*) ke sistem dan tugas yang bersangkutan berstatus aktif (belum melewati *deadline*).
- **Post-condition**: File tugas berhasil diunggah dan disimpan ke server, serta status berubah menjadi "Submitted".
- **Main Flow**:
  1. Mahasiswa membuka halaman detail tugas yang aktif.
  2. Mahasiswa menekan tombol "Upload File" dan memilih file (.pdf, .zip, .rar, dll. maks 20 MB).
  3. Sistem memvalidasi tipe dan ukuran berkas secara otomatis.
  4. Mahasiswa menekan tombol "Submit".
  5. Sistem menyimpan berkas tugas ke server, melakukan *renaming* berkas secara standar (`NIM_Nama_TugasID.ekstensi`), menyimpan data ke database, dan menampilkan status "Submitted".

---

### UC-04: Grade Submission & Feedback (Dosen)
- **Actor**: Lecturer (Dosen)
- **Pre-condition**: Dosen sudah masuk (*logged in*) dan terdapat file tugas mahasiswa yang berstatus "Submitted" atau "Pending Review".
- **Post-condition**: Nilai dan umpan balik tersimpan, serta status tugas mahasiswa berubah menjadi "Graded".
- **Main Flow**:
  1. Dosen memilih salah satu tugas mahasiswa dari daftar pengumpulan.
  2. Dosen mengunduh atau melihat pratonton berkas mahasiswa.
  3. Dosen menginput nilai angka bulat (0-100) dan umpan balik tertulis di form penilaian.
  4. Dosen mengklik tombol "Save Grade".
  5. Sistem memvalidasi input nilai, menyimpan nilai ke database, mengubah status tugas menjadi "Graded", dan mengirimkan notifikasi ke mahasiswa.

---

### UC-05: Import Users Massally (Admin)
- **Actor**: Administrator
- **Pre-condition**: Administrator sudah masuk (*logged in*) dan berada di halaman User Management.
- **Post-condition**: Akun-akun baru berhasil dibuat secara massal di database.
- **Main Flow**:
  1. Administrator mengunduh template CSV/Excel.
  2. Administrator mengunggah berkas data pengguna yang sudah terisi.
  3. Sistem melakukan validasi format kolom dan kelayakan data baris demi baris.
  4. Sistem memproses data valid, membuat akun baru, dan menampilkan hasil statistik impor.

---

### UC-06: Suspend Account (Admin)
- **Actor**: Administrator
- **Pre-condition**: Akun pengguna (mahasiswa/dosen) yang akan disuspend berada dalam status aktif di database.
- **Post-condition**: Akun pengguna dinonaktifkan, sehingga tidak dapat masuk ke sistem, tetapi riwayat nilainya tetap aman.
- **Main Flow**:
  1. Administrator mencari akun pengguna di daftar pencarian pengguna.
  2. Administrator mengklik aksi "Suspend Account".
  3. Sistem menampilkan konfirmasi penonaktifan akun.
  4. Administrator mengonfirmasi konstatus penonaktifan.
  5. Sistem mengubah kolom `is_active` menjadi `false` di database dan menampilkan pesan sukses.

---

### UC-08: Cancel Submission / Unsubmit (Mahasiswa)
- **Actor**: Student (Mahasiswa)
- **Pre-condition**: Mahasiswa telah mengumpulkan tugas (status: "Submitted"), tugas belum dinilai dosen, dan waktu saat ini belum melewati tenggat waktu (*deadline*).
- **Post-condition**: Berkas pengumpulan dihapus dari server dan status dikembalikan menjadi "Not Submitted".
- **Main Flow**:
  1. Mahasiswa membuka halaman detail tugas yang sudah dikumpulkannya.
  2. Mahasiswa mengklik tombol "Unsubmit".
  3. Sistem menampilkan konfirmasi tindakan.
  4. Mahasiswa mengonfirmasi pembatalan.
  5. Sistem menghapus file lama dari server, mengupdate database, dan mengaktifkan kembali tombol pengunggahan.
