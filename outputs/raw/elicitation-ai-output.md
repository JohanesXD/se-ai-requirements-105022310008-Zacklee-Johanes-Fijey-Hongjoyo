# Requirements Elicitation: Student Task Management System (Raw AI Output)

## 1. Elicitation Techniques & Justification
- **Interview (Wawancara)**: Digunakan untuk menggali kebutuhan personal, keluhan, dan harapan langsung dari Dosen, Mahasiswa, dan Administrator.
- **Document Analysis (Analisis Dokumen)**: Menganalisis catatan rapat dan dokumen asumsi untuk memahami batasan teknis proyek.
- **Alumni Survey (Kuesioner Alumni)**: Mengirim kuesioner ke seluruh alumni untuk menanyakan apakah aplikasi sejenis ini berguna saat mereka masih kuliah dulu.

## 2. Key Interview Highlights
### 2.1 Lecturer Interviews
- **Topik**: Pengunduhan Berkas Tugas
  - **Temuan**: Dosen ingin dapat mengunduh berkas tugas satu per satu atau sekaligus dalam satu file ZIP terkompresi untuk satu kelas.
- **Topik**: Penilaian & Penandaan Status
  - **Temuan**: Penginputan nilai berupa angka bulat 0-100 dan ada status penanda tugas yang belum dinilai.

### 2.2 Student Interviews
- **Topik**: Validasi Berkas & Notifikasi
  - **Temuan**: Mahasiswa ingin melihat pratonton file PDF yang diunggah dan mendapatkan notifikasi dalam aplikasi serta notifikasi email ketika ada tugas atau nilai baru.
- **Topik**: Pengunggahan Ulang (*Unsubmit*)
  - **Temuan**: Fitur membatalkan pengumpulan sebelum *deadline* agar bisa mengunggah berkas yang diperbaiki.

### 2.3 Administrator Interviews
- **Topik**: Manajemen Akun & Siklus Hidup Pengguna
  - **Temuan**: Import massal data pengguna via Excel/CSV dan penonaktifan akun secara dinonaktifkan (*suspended*) alih-alih dihapus permanen.

## 3. Explicit vs. Implicit Requirements
### 3.1 Lecturer Requirements
- **[EXPLICIT]** Dosen dapat membuat deskripsi tugas baru dan tenggat waktunya.
- **[EXPLICIT]** Dosen dapat mengunduh berkas tugas mahasiswa dalam bentuk file ZIP sekaligus satu kelas.
- **[IMPLICIT]** Sistem harus menggunakan DBMS Oracle 19c untuk menyimpan seluruh berkas ZIP pengumpulan agar aman.
- **[IMPLICIT]** Sistem harus memeriksa hak akses dosen agar dosen hanya dapat menilai kelas yang diampunya saja.

### 3.2 Student Requirements
- **[EXPLICIT]** Mahasiswa dapat melihat daftar tugas aktif dan mengunggah berkas tugas (.pdf, .zip, .rar, .docx, .xlsx, .pptx).
- **[EXPLICIT]** Mahasiswa dapat membatalkan pengiriman tugas (*unsubmit*) sebelum tenggat waktu.
- **[IMPLICIT]** Sistem harus mengirimkan SMS berbayar ke nomor handphone mahasiswa setiap kali ada tugas baru.
- **[IMPLICIT]** Sistem harus menghitung kapasitas sisa dari file yang diunggah untuk dicocokkan dengan batas 20MB.

### 3.3 Administrator Requirements
- **[EXPLICIT]** Admin dapat mengimpor data pengguna secara massal menggunakan file Excel/CSV.
- **[EXPLICIT]** Akun mahasiswa yang lulus atau dosen yang pensiun harus dinonaktifkan (*suspended*) bukan dihapus.
- **[IMPLICIT]** Sistem harus memvalidasi data CSV/Excel yang diunggah agar tidak ada email ganda atau format data yang salah masuk ke database.

## 4. Elicitation Constraints & Business Rules
- **[CONSTRAINT]** Ukuran maksimal file tugas adalah 20 MB per file.
- **[CONSTRAINT]** Oracle Database 19c harus digunakan sebagai standard database.
- **[BUSINESS RULE]** Dosen hanya diperkenankan menginput nilai bulat dengan rentang 0-100.
- **[BUSINESS RULE]** Mahasiswa tidak diizinkan melakukan *unsubmit* jika status tugas telah dinilai oleh dosen atau jika tenggat waktu telah terlampaui.
