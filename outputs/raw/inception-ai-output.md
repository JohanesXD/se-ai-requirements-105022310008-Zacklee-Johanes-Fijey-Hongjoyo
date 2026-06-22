# Project Inception and Stakeholder Discovery: Student Task Management System

## 1. Business Problem & Goals
### Business Problem
Pengelolaan tugas perkuliahan di lingkungan kampus saat ini masih menghadapi banyak kendala karena dilakukan secara manual menggunakan berbagai media komunikasi seperti email, WhatsApp, dan Google Drive. Hal ini memicu ketidakteraturan, di mana dosen kesulitan mengidentifikasi mahasiswa yang mengumpulkan tugas tepat waktu, berkas tugas sering tertimbun di email, dan mahasiswa sering kali melupakan tenggat waktu karena tidak ada sistem notifikasi terpusat. Untuk mengatasi masalah tersebut, diperlukan pembuatan Student Task Management System dengan antarmuka yang sangat cepat dan modern agar semua pihak dapat berinteraksi dengan mudah.

### Project Goals
- Membuat sistem pengelolaan tugas berbasis web yang dapat menyatukan seluruh proses pembuatan, pengumpulan, dan penilaian tugas.
- Memastikan sistem dapat diakses dengan sangat cepat oleh seluruh pengguna kapan saja.
- Mengurangi keterlambatan pengumpulan tugas oleh mahasiswa secara signifikan.
- Memungkinkan dosen untuk memberikan nilai angka dan feedback secara langsung.

## 2. Stakeholders & User Needs
### 2.1 Primary Stakeholders
- **Lecturer (Dosen)**:
  - **Needs**: Ingin mengunggah tugas, memantau siapa saja yang sudah mengumpulkan tugas secara real-time, memberikan penilaian, dan memberikan feedback tertulis.
  - **Pain Points**: Tugas tertimbun di email/grup chat, dan sulit merekap nilai secara terorganisir.
- **Student (Mahasiswa)**:
  - **Needs**: Melihat daftar tugas aktif yang diurutkan dari deadline terdekat, mengunggah berkas pengumpulan (.pdf, .zip, .docx), membatalkan pengiriman (unsubmit) sebelum deadline, dan melihat nilai.
  - **Pain Points**: Sering lupa deadline tugas karena tidak ada notifikasi terpusat.
- **Administrator**:
  - **Needs**: Mengelola akun pengguna (mahasiswa, dosen, admin), mengelola kelas, mengelola mata kuliah, serta mengimpor data lewat CSV/Excel secara masal.
  - **Pain Points**: Proses pendaftaran data satu per satu secara manual sangat memakan waktu.

### 2.2 Secondary Stakeholders
- **Biro Teknologi Informasi Kampus**:
  - **Needs**: Memastikan sistem terintegrasi dengan baik ke database akademik pusat dan SSO kampus.
  - **Pain Points**: Beban server yang bisa melonjak tinggi saat menjelang tenggat waktu tugas.

## 3. Project Scope
### 3.1 In-Scope
- Fitur Autentikasi Pengguna menggunakan Single Sign-On (SSO).
- Fitur Manajemen Tugas (pembuatan oleh dosen, melihat daftar tugas oleh mahasiswa).
- Fitur Pengumpulan Berkas Tugas dengan dukungan format PDF, ZIP, RAR, DOCX, XLSX, PPTX.
- Fitur Penilaian dan Feedback tugas oleh dosen.
- Fitur Import Data Pengguna via file Excel/CSV oleh Administrator.
- Fitur Chatting/Forum Diskusi antar dosen dan mahasiswa untuk membahas detail tugas.

### 3.2 Out-of-Scope
- Sistem pembayaran biaya kuliah/akademik.
- Fitur kelas virtual/video conference (seperti Zoom integration).

## 4. Assumptions & Constraints
- **[ASSUMPTION]** Kampus sudah memiliki API akademik aktif yang siap dikonsumsi untuk import data kelas dan mata kuliah.
- **[ASSUMPTION]** Sistem akan di-host pada server cloud internal kampus.
- **[CONSTRAINT]** Berkas pengumpulan tugas dibatasi maksimal 20 MB per file.
- **[CONSTRAINT]** Sistem harus beroperasi dalam zona waktu Waktu Indonesia Barat (WIB).

## 5. Open Questions
- **[OPEN QUESTION]** Apakah ada fitur notifikasi email otomatis jika ada tugas baru yang dibuat oleh dosen?
- **[OPEN QUESTION]** Apakah sistem perlu menyimpan log aktivitas secara detail untuk keperluan audit administrator?
