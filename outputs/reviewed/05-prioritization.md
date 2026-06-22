# Requirements Prioritization & Negotiation: Student Task Management System

## 1. Stakeholder Conflict Resolutions

### Conflict 1: Batasan Ukuran Berkas Tugas vs Kebutuhan Ruang Penyimpanan Server
- **Stakeholders Involved**: Student (Mahasiswa) vs Administrator (Tim IT Kampus)
- **Conflict Description**: 
  Mahasiswa menginginkan batas pengunggahan berkas tugas yang tidak dibatasi (unlimited) atau berukuran sangat besar (misal 100 MB - 500 MB) agar leluasa melampirkan berkas video demonstrasi, program lengkap, atau laporan gambar beresolusi tinggi. Di sisi lain, Administrator dan Tim IT Kampus menginginkan batasan file sekecil mungkin (maksimal 5 MB) untuk menghemat kapasitas harddisk server dan menghindari kemacetan *bandwidth* server ketika ribuan mahasiswa mengunggah berkas bersamaan menjelang *deadline*.
- **Resolution & Trade-off**:
  Setelah dilakukan proses negosiasi, disepakati kompromi sebagai berikut:
  1. Batas ukuran berkas yang diunggah disetujui sebesar **20 MB per file** (`[CONSTRAINT]`). Ini dinilai cukup untuk laporan (.pdf, .docx) dan program yang dikompresi (.zip).
  2. Sistem diwajibkan melakukan validasi sisi klien (*client-side validation*) sebelum file dikirim ke server untuk menghemat *bandwidth*.
  3. Mahasiswa yang membutuhkan pengumpulan tugas berukuran sangat besar (seperti video demonstrasi) diarahkan untuk mengunggah video ke platform pihak ketiga (seperti Google Drive kampus atau YouTube) dan hanya mengumpulkan link tautan teks di dalam sistem.

---

## 2. Requirements Dependencies
- **FR-04 (Upload berkas)** bergantung pada **FR-01 (Pembuatan tugas)**: Mahasiswa tidak dapat mengunggah file tugas jika tugas perkuliahan tersebut belum dibuat dan dikonfigurasi oleh dosen di sistem.
- **FR-05 (Unsubmit berkas)** bergantung pada **FR-04 (Upload berkas)**: Mahasiswa tidak dapat membatalkan pengiriman file jika belum pernah melakukan pengunggahan berkas sebelumnya.
- **FR-06 (Penilaian & Feedback)** bergantung pada **FR-04 (Upload berkas)**: Dosen tidak dapat memberikan penilaian dan umpan balik pada tugas mahasiswa jika mahasiswa belum mengunggah berkas tugasnya.
- **FR-02 (Bulk Download ZIP)** bergantung pada **FR-04 (Upload berkas)**: Fitur pengunduhan ZIP satu kelas tidak dapat mengekstraksi file jika mahasiswa belum mengunggah berkas apa pun.
- **FR-09 (Rename file otomatis)** bergantung pada **FR-04 (Upload berkas)**: Proses penggantian nama file secara standar hanya dipicu saat mahasiswa melakukan pengunggahan file.

---

## 3. MoSCoW Prioritization Matrix

| ID | Requirement Description | Category (M/S/C/W) | Dependency | Priority Justification |
|:---|:---|:---|:---|:---|
| **FR-01** | Dosen dapat membuat tugas baru dengan menentukan judul, instruksi, dan tenggat waktu (*deadline*). | **Must Have (M)** | None | Kebutuhan paling mendasar dari sistem; tanpa pembuatan tugas oleh dosen, alur kerja sistem tidak dapat dimulai. |
| **FR-02** | Dosen dapat mengunduh seluruh file tugas mahasiswa dalam satu kelas sekaligus sebagai satu file ZIP terkompresi. | **Should Have (S)** | FR-04 | Dosen masih bisa mengunduh file satu per satu untuk penilaian awal jika fitur ZIP ditunda, tetapi fitur ZIP sangat penting untuk efisiensi waktu dosen. |
| **FR-03** | Mahasiswa dapat melihat daftar tugas perkuliahan aktif yang otomatis diurutkan berdasarkan tenggat waktu terdekat. | **Must Have (M)** | None | Kritis bagi mahasiswa untuk mengetahui tugas apa saja yang harus diselesaikan guna menghindari keterlambatan. |
| **FR-04** | Mahasiswa dapat mengunggah berkas pengumpulan tugas dengan tipe file yang diizinkan. | **Must Have (M)** | FR-01 | Inti dari sistem pengumpulan tugas perkuliahan; tanpa fitur ini, sistem kehilangan fungsi utamanya. |
| **FR-05** | Mahasiswa dapat membatalkan pengiriman berkas tugas (*unsubmit*) sebelum melewati tenggat waktu. | **Should Have (S)** | FR-04 | Penting untuk *user experience* mahasiswa jika terjadi kesalahan unggah berkas, tetapi secara teknis mahasiswa masih bisa menghubungi dosen secara manual jika fitur ini belum aktif. |
| **FR-06** | Dosen dapat memberikan nilai angka (0-100) dan umpan balik (*feedback*) tertulis langsung pada tugas mahasiswa. | **Must Have (M)** | FR-04 | Siklus akhir pengumpulan tugas yang krusial untuk transparansi nilai akademik di kampus. |
| **FR-07** | Administrator dapat mengimpor data dosen, mahasiswa, dan mata kuliah secara massal menggunakan file Excel/CSV. | **Should Have (S)** | None | Mempercepat *setup* awal pengguna, namun di rilis awal administrator masih dapat mendaftarkan akun secara manual melalui form admin jika diperlukan. |
| **FR-08** | Administrator dapat mengubah status akun pengguna menjadi nonaktif (*suspended*) alih-alih menghapus data secara permanen. | **Must Have (M)** | None | Kritis untuk menjaga integritas data riwayat nilai (*data integrity*); menghapus akun secara permanen akan merusak relasi database transaksional nilai. |
| **FR-09** | Sistem secara otomatis mengubah nama file tugas mahasiswa menjadi format standar (`NIM_Nama_TugasID.ekstensi`). | **Must Have (M)** | FR-04 | Kritis untuk mencegah konflik penamaan file (*file naming collision*) di server penyimpanan cloud kampus dan mempermudah dosen mengidentifikasi file. |
