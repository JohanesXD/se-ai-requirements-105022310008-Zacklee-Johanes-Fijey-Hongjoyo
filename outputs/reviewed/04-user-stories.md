# User Stories and Acceptance Criteria: Student Task Management System

## User Stories & Acceptance Criteria List

### US-01: Mengunggah Berkas Tugas (Upload Submission)
- **Story**: As a Student, I want to upload my assignment file so that my lecturer can review and grade it.
- **Acceptance Criteria**:
  - **AC-01.1 (Scenario: Success Upload)**: 
    - **Given** mahasiswa berada di halaman rincian tugas dan waktu saat ini belum melewati tenggat waktu (*deadline*).
    - **When** mahasiswa memilih berkas tugas yang valid (ukuran < 20 MB, format file: `.pdf`, `.zip`, `.rar`, `.docx`, `.xlsx`, `.pptx`) dan menekan tombol "Submit".
    - **Then** berkas berhasil diunggah, nama berkas otomatis diubah mengikuti format `NIM_Nama_TugasID.ekstensi`, dan status tugas berubah menjadi "Submitted".
  - **AC-01.2 (Scenario: Failure - File Too Large)**: 
    - **Given** mahasiswa berada di halaman rincian tugas.
    - **When** mahasiswa mencoba mengunggah berkas yang berukuran lebih dari 20 MB.
    - **Then** sistem menolak pengunggahan, menampilkan pesan kesalahan "File size exceeds the 20 MB limit", dan status tugas tidak berubah.
  - **AC-01.3 (Scenario: Failure - Invalid Format)**:
    - **Given** mahasiswa berada di halaman rincian tugas.
    - **When** mahasiswa mencoba mengunggah berkas dengan ekstensi selain yang diizinkan (misalnya: `.exe`, `.png`, `.jpg`).
    - **Then** sistem menolak pengunggahan, menampilkan pesan kesalahan "Invalid file format. Allowed formats: PDF, ZIP, RAR, DOCX, XLSX, PPTX", dan status tugas tidak berubah.

---

### US-02: Mengunduh Berkas Tugas Satu Kelas (Bulk Download)
- **Story**: As a Lecturer, I want to download all student submissions for a specific class as a single ZIP file so that I can grade them offline.
- **Acceptance Criteria**:
  - **AC-02.1 (Scenario: Success Download ZIP)**:
    - **Given** dosen telah masuk (*logged in*) dan terdaftar sebagai pengampu resmi dari kelas tersebut.
    - **When** dosen membuka dasbor tugas kelas tersebut dan menekan tombol "Download All Submissions".
    - **Then** sistem membuat satu berkas ZIP terkompresi yang berisi seluruh file tugas mahasiswa yang telah dikumpulkan, dan mengunduh berkas tersebut ke komputer dosen.
  - **AC-02.2 (Scenario: Failure - Unauthorized Class Access)**:
    - **Given** dosen mencoba mengakses halaman pengunduhan dasbor tugas kelas yang bukan diampunya secara langsung melalui perubahan URL.
    - **Then** sistem menolak akses, menampilkan pesan kesalahan "403 Forbidden - You are not authorized to access this class", dan proses unduh dibatalkan.

---

### US-03: Impor Akun Pengguna Massal (Bulk User Import)
- **Story**: As an Administrator, I want to upload a CSV/Excel file of users so that I can create multiple accounts quickly.
- **Acceptance Criteria**:
  - **AC-03.1 (Scenario: Success Import)**:
    - **Given** administrator berada di halaman manajemen pengguna.
    - **When** administrator mengunggah berkas CSV/Excel dengan format kolom yang benar (NIM/NIDN, Nama Lengkap, Email, Peran, Kelas) dan berisi data valid.
    - **Then** sistem membuat akun pengguna baru untuk semua baris data dan menampilkan pesan sukses "Successfully imported X users".
  - **AC-03.2 (Scenario: Failure - Invalid Data/Format)**:
    - **Given** administrator berada di halaman manajemen pengguna.
    - **When** administrator mengunggah berkas CSV/Excel di mana beberapa baris memiliki kolom kosong atau format email tidak valid.
    - **Then** sistem menolak baris data yang salah, memproses baris data yang valid, dan menampilkan laporan kesalahan rinci yang menunjukkan nomor baris dan deskripsi kesalahan (misal: "Baris 5: Format email tidak valid").

---

### US-04: Menerima Notifikasi Nilai (Grading Notification)
- **Story**: As a Student, I want to receive a notification when my assignment is graded so that I can immediately view my results.
- **Acceptance Criteria**:
  - **AC-04.1 (Scenario: In-App Notification)**:
    - **Given** mahasiswa sedang aktif masuk ke dalam aplikasi.
    - **When** dosen menyimpan nilai dan umpan balik pada tugas mahasiswa tersebut.
    - **Then** lencana notifikasi (*notification badge*) di aplikasi berubah warna/angka secara waktu nyata (*real-time*), dan ketika diklik menampilkan teks "Tugas [TugasID] Anda telah dinilai".
  - **AC-04.2 (Scenario: Email Notification)**:
    - **Given** mahasiswa tidak sedang membuka aplikasi tetapi email mereka terdaftar secara valid.
    - **When** dosen menyimpan nilai dan umpan balik pada tugas mahasiswa tersebut.
    - **Then** sistem mengirimkan email pemberitahuan otomatis ke email mahasiswa yang berisi informasi nilai, potongan umpan balik dosen, dan tautan langsung ke halaman rincian tugas.

---

### US-05: Penilaian dan Umpan Balik Tugas (Grading & Feedback)
- **Story**: As a Lecturer, I want to input grades and feedback for each student submission so that they understand their academic evaluation.
- **Acceptance Criteria**:
  - **AC-05.1 (Scenario: Success Grading)**:
    - **Given** dosen sedang memeriksa berkas pengumpulan tugas milik mahasiswa di halaman penilaian.
    - **When** dosen memasukkan nilai angka bulat valid (0-100), mengisi umpan balik tertulis, dan mengklik tombol "Save Grade".
    - **Then** sistem menyimpan nilai tersebut ke database, mengubah status tugas menjadi "Graded", dan memperbarui tampilan nilai di akun mahasiswa yang bersangkutan.
  - **AC-05.2 (Scenario: Failure - Out of Range Grade)**:
    - **Given** dosen berada di halaman penilaian mahasiswa.
    - **When** dosen memasukkan nilai di luar rentang 0-100 (misalnya: -5 atau 105) lalu menekan tombol "Save Grade".
    - **Then** sistem menolak penyimpanan, menampilkan pesan kesalahan "Grade must be an integer between 0 and 100", dan nilai lama tetap tidak berubah.

---

### US-06: Pembatalan Pengumpulan Tugas (Unsubmit Submission)
- **Story**: As a Student, I want to unsubmit my task so that I can correct errors and re-upload the file before the deadline.
- **Acceptance Criteria**:
  - **AC-06.1 (Scenario: Success Unsubmit)**:
    - **Given** mahasiswa telah mengumpulkan tugas, status tugas masih "Submitted" (belum dinilai), dan waktu saat ini belum melewati *deadline*.
    - **When** mahasiswa menekan tombol "Unsubmit".
    - **Then** berkas tugas sebelumnya dihapus dari server, status tugas diubah menjadi "Not Submitted", dan tombol unggah berkas diaktifkan kembali agar mahasiswa dapat mengunggah file baru.
  - **AC-06.2 (Scenario: Failure - Already Graded)**:
    - **Given** tugas mahasiswa telah dinilai oleh dosen (status: "Graded").
    - **When** mahasiswa melihat halaman rincian tugas.
    - **Then** tombol "Unsubmit" dinonaktifkan secara permanen oleh sistem, dan sistem menampilkan pesan "Cannot unsubmit. Assignment has already been graded."
  - **AC-06.3 (Scenario: Failure - Past Deadline)**:
    - **Given** waktu saat ini telah melewati tenggat waktu tugas (*deadline*).
    - **When** mahasiswa melihat halaman rincian tugas yang sudah dikumpulkan.
    - **Then** tombol "Unsubmit" dinonaktifkan secara otomatis oleh sistem, dan sistem menampilkan catatan "Deadline has passed. Submission is locked."
