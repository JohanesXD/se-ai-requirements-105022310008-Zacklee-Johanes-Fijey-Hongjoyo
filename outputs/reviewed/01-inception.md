# Project Inception and Stakeholder Discovery: Student Task Management System

## 1. Business Problem & Goals
### Business Problem
Proses pengelolaan tugas perkuliahan di lingkungan kampus saat ini masih dilakukan secara manual dan terfragmentasi menggunakan email, aplikasi pesan instan (WhatsApp), dan Google Drive. Akibatnya, dosen kesulitan memantau status pengumpulan tugas mahasiswa, berkas tugas sering hilang atau tertumpuk di inbox email, dan mahasiswa kerap kali melupakan tenggat waktu pengumpulan karena tidak adanya media pengingat yang terpusat. Hal ini menurunkan efisiensi akademik dan akurasi pencatatan nilai.

### Project Goals
- Menyediakan platform tunggal yang terintegrasi untuk mendistribusikan deskripsi tugas, mengumpulkan berkas tugas, dan memberikan penilaian secara terpusat.
- Memastikan waktu respons sistem (*page load time*) maksimal 3 detik pada kondisi jaringan standar kampus.
- Meminimalisasi keterlambatan pengumpulan tugas mahasiswa dengan menyediakan daftar tugas aktif yang diurutkan berdasarkan tenggat waktu terdekat.
- Meningkatkan transparansi penilaian dengan menampilkan nilai dan umpan balik secara langsung kepada mahasiswa yang bersangkutan segera setelah dinilai oleh dosen.

## 2. Stakeholders & User Needs
### 2.1 Primary Stakeholders
- **Lecturer (Dosen)**:
  - **Needs**: Mengunggah instruksi tugas perkuliahan, menetapkan tenggat waktu (*deadline*), melihat daftar mahasiswa yang sudah/belum mengumpulkan, serta memberikan nilai (0-100) dan umpan balik langsung di sistem.
  - **Pain Points**: Sulit mencari berkas tugas mahasiswa di email karena tertimbun, dan tidak memiliki rekapitulasi status pengumpulan secara langsung.
- **Student (Mahasiswa)**:
  - **Needs**: Melihat daftar tugas aktif yang diurutkan dari *deadline* terdekat, mengunggah berkas tugas (.pdf, .zip, .rar, .docx, .xlsx, .pptx), membatalkan pengiriman (*unsubmit*) untuk perbaikan berkas sebelum tenggat waktu berakhir, serta melihat nilai dan umpan balik dari dosen.
  - **Pain Points**: Sering melewatkan tenggat waktu karena informasi tugas tersebar di banyak grup obrolan.
- **Administrator**:
  - **Needs**: Mengelola akun pengguna (dosen, mahasiswa, administrator), mengelola kelas dan mata kuliah, serta melakukan impor data massal pengguna via file Excel/CSV.
  - **Pain Points**: Pendaftaran akun dan mata kuliah secara manual membutuhkan waktu yang sangat lama dan rentan kesalahan input data.

### 2.2 Secondary Stakeholders
- **Biro Teknologi Informasi Kampus**:
  - **Needs**: Menjamin keamanan data nilai mahasiswa, kelancaran integrasi Single Sign-On (SSO), dan stabilitas sistem saat beban puncak (mendekati *deadline*).
  - **Pain Points**: Potensi lonjakan beban server (*server load spikes*) di menit-menit terakhir sebelum tenggat waktu pengumpulan tugas.

## 3. Project Scope
### 3.1 In-Scope
- Sistem autentikasi pengguna terintegrasi dengan Single Sign-On (SSO) kampus.
- Manajemen tugas perkuliahan (pembuatan deskripsi tugas dan tenggat waktu oleh dosen).
- Pengunggahan berkas tugas mahasiswa dengan pembatasan tipe file (.pdf, .zip, .rar, .docx, .xlsx, .pptx) dan pembatasan ukuran berkas.
- Fitur pembatalan pengunggahan berkas (*unsubmit*) sebelum melewati tenggat waktu.
- Penilaian tugas dan umpan balik tertulis dari dosen untuk setiap mahasiswa.
- Impor data dosen, mahasiswa, dan mata kuliah secara massal menggunakan file Excel/CSV oleh Administrator.
- Integrasi pengambilan data kelas dan mata kuliah yang aktif lewat API akademik kampus.

### 3.2 Out-of-Scope
- Fitur ruang kelas virtual atau tatap muka online (integrasi Zoom/Teams).
- Pembayaran biaya kuliah atau administrasi keuangan akademik lainnya.
- Fitur komunikasi real-time seperti chat internal atau forum diskusi antar pengguna.

## 4. Assumptions & Constraints
- **[ASSUMPTION]** Kampus memiliki sistem Single Sign-On (SSO) aktif dengan API autentikasi yang dapat diakses oleh sistem.
- **[ASSUMPTION]** Biro TI kampus menyediakan API akademik yang stabil untuk pengambilan data mahasiswa, dosen, dan mata kuliah.
- **[CONSTRAINT]** Ukuran berkas tugas yang diunggah dibatasi maksimal 20 MB per file.
- **[CONSTRAINT]** Sistem harus berjalan menggunakan zona waktu Waktu Indonesia Barat (WIB / UTC+7).
- **[CONSTRAINT]** Keamanan data harus diatur sedemikian rupa sehingga mahasiswa tidak dapat melihat berkas tugas atau nilai milik mahasiswa lainnya.

## 5. Open Questions
- **[OPEN QUESTION]** Apakah sistem perlu mengirimkan notifikasi pengingat secara otomatis melalui email atau WhatsApp saat tenggat waktu tugas tersisa 24 jam?
- **[OPEN QUESTION]** Apakah sistem harus mendukung fitur pendeteksian plagiarisme otomatis (seperti Turnitin) pada berkas tugas yang dikumpulkan?
