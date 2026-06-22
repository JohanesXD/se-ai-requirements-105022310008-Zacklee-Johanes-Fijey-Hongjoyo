# Requirements Elicitation: Student Task Management System

## 1. Elicitation Techniques & Justification
- **Interview (Wawancara)**: Digunakan untuk menggali langsung keluhan, harapan, dan kebutuhan dari perwakilan dosen (Dr. Budi Santoso), mahasiswa (Rian & Siska), dan administrator (Ibu Ambar). Teknik ini sangat efektif untuk memahami alur kerja aktual dan *pain points* pengguna.
- **Document Analysis (Analisis Dokumen)**: Menganalisis catatan awal studi kasus (`CASE.md`) serta batasan umum proyek (`inputs/assumptions.md`) untuk memastikan seluruh kebutuhan yang didefinisikan tidak melanggar batasan arsitektur kampus.

## 2. Key Interview Highlights
### 2.1 Lecturer Interviews
- **Topik**: Pengunduhan Berkas Tugas
  - **Temuan**: Dosen membutuhkan fitur pengunggahan instruksi tugas yang fleksibel dan kemampuan untuk mengunduh seluruh tugas mahasiswa dalam satu kelas sekaligus sebagai satu file ZIP terkompresi.
- **Topik**: Penilaian & Penandaan Status
  - **Temuan**: Dosen menghendaki sistem memberikan penanda visual jika ada tugas mahasiswa yang belum dinilai. Nilai yang dimasukkan dibatasi pada angka bulat 0-100.

### 2.2 Student Interviews
- **Topik**: Validasi Berkas & Notifikasi
  - **Temuan**: Mahasiswa ingin sistem memvalidasi file yang diunggah tidak berukuran 0 KB (rusak) dan menunjukkan pratonton file PDF. Mahasiswa juga membutuhkan notifikasi dalam aplikasi (*in-app*) dan notifikasi email setiap ada tugas baru atau nilai yang masuk.
- **Topik**: Pengunggahan Ulang (*Unsubmit*)
  - **Temuan**: Mahasiswa menginginkan opsi membatalkan pengiriman berkas (*unsubmit*) agar bisa mengunggah file revisi sebelum melewati batas waktu pengumpulan.

### 2.3 Administrator Interviews
- **Topik**: Manajemen Akun & Siklus Hidup Pengguna
  - **Temuan**: Administrator membutuhkan impor massal data menggunakan format Excel/CSV. Akun dari mahasiswa yang lulus atau dosen yang pensiun tidak boleh dihapus permanen melainkan dinonaktifkan (*suspended*) demi menjaga riwayat data akademik.

## 3. Explicit vs. Implicit Requirements
### 3.1 Lecturer Requirements
- **[EXPLICIT]** Dosen dapat mengunggah berkas instruksi tugas dan menentukan tenggat waktunya.
- **[EXPLICIT]** Dosen dapat mengunduh seluruh file tugas mahasiswa dalam satu kelas sekaligus sebagai berkas ZIP.
- **[IMPLICIT]** Sistem harus memverifikasi bahwa pengakses kelas (dosen) adalah dosen pengampu resmi kelas tersebut sebelum mengizinkan pembuatan tugas atau penilaian.
- **[IMPLICIT]** Sistem harus menampilkan indikator status "Belum Dinilai" (*Pending Review*) di daftar tugas mahasiswa yang masuk.

### 3.2 Student Requirements
- **[EXPLICIT]** Mahasiswa dapat melihat daftar tugas aktif dan mengunggah berkas tugas (.pdf, .zip, .rar, .docx, .xlsx, .pptx).
- **[EXPLICIT]** Mahasiswa dapat melakukan *unsubmit* berkas tugas untuk melakukan revisi pengumpulan sebelum tenggat waktu berakhir.
- **[IMPLICIT]** Sistem harus memvalidasi ukuran berkas dan integritas file saat pengunggahan untuk mencegah unggahan file kosong (0 KB) atau rusak.
- **[IMPLICIT]** Sistem harus mengubah nama file yang diunggah mahasiswa secara otomatis mengikuti pola standar penamaan (misal: `NIM_Nama_TugasID.ekstensi`) untuk kerapian penyimpanan di server.

### 3.3 Administrator Requirements
- **[EXPLICIT]** Administrator dapat mengimpor data dosen, mahasiswa, dan mata kuliah secara massal menggunakan file Excel/CSV.
- **[EXPLICIT]** Administrator dapat mengubah status akun pengguna menjadi nonaktif (*suspended*) alih-alih menghapusnya dari database.
- **[IMPLICIT]** Sistem harus memvalidasi kolom data pada file impor (seperti format email, kecocokan tipe data role) dan menampilkan pesan kesalahan baris demi baris jika impor gagal.

## 4. Elicitation Constraints & Business Rules
- **[CONSTRAINT]** Ukuran maksimal file tugas mahasiswa yang diunggah dibatasi sebesar 20 MB per file.
- **[CONSTRAINT]** Sistem harus berjalan dengan konfigurasi zona waktu Waktu Indonesia Barat (WIB / UTC+7) untuk validasi tenggat waktu.
- **[BUSINESS RULE]** Dosen hanya dapat memasukkan nilai berupa bilangan bulat (*integer*) dengan rentang minimal 0 dan maksimal 100.
- **[BUSINESS RULE]** Mahasiswa tidak dapat membatalkan pengiriman (*unsubmit*) atau mengunggah berkas baru apabila status tugas sudah dinilai oleh dosen atau apabila waktu pengumpulan telah melewati tenggat waktu yang ditentukan.
