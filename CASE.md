# Case Study: Student Task Management System

## 1. Background
Student Task Management System adalah aplikasi kampus yang digunakan oleh dosen, mahasiswa, dan administrator untuk mengelola tugas perkuliahan, pengumpulan tugas, penilaian, tenggat waktu, dan pelaporan.
Sistem ini dirancang untuk menggantikan atau meningkatkan pengelolaan tugas perkuliahan agar lebih terstruktur, transparan, dan efisien.

## 2. Stakeholders and Users
Sistem ini memiliki tiga kategori pengguna utama dengan peran masing-masing:
* **Lecturer (Dosen)**:
  - Membuat tugas perkuliahan baru.
  - Menetapkan tenggat waktu (deadline) pengumpulan.
  - Memberikan nilai dan umpan balik (feedback) terhadap tugas yang dikumpulkan.
* **Student (Mahasiswa)**:
  - Melihat daftar tugas perkuliahan yang aktif dan yang telah selesai.
  - Mengunggah file tugas untuk dikumpulkan.
  - Memantau status pengumpulan dan tenggat waktu.
  - Melihat nilai serta umpan balik dari dosen.
* **Administrator**:
  - Mengelola pengguna (pendaftaran, hak akses, dll.).
  - Mengelola data mata kuliah dan kelas.
  - Mengelola konfigurasi sistem secara umum.

## 3. System Quality Attributes (Non-Functional Requirements)
Sistem harus dirancang dengan memperhatikan aspek kualitas berikut:
* **Usability**: Antarmuka mudah dipahami dan digunakan oleh dosen, mahasiswa, dan administrator.
* **Security**: Keamanan data pengguna dan integritas file tugas dari akses yang tidak sah.
* **Performance**: Kecepatan akses data tugas dan respons sistem saat mengunggah file.
* **Reliability**: Ketersediaan sistem yang tinggi terutama mendekati tenggat waktu pengumpulan tugas.
* **Data Integrity**: Keutuhan data nilai, tugas, dan file pengumpulan yang tidak boleh hilang atau rusak.

## 4. Constraint & Assumptions
* Pengguna sistem wajib masuk (*login*) terlebih dahulu sebelum mengakses fitur-fitur di dalamnya.
* Batas ukuran file yang diunggah harus didefinisikan agar tidak membebani kapasitas server.
* Setiap asumsi tambahan yang tidak tercantum dalam dokumen ini wajib ditandai secara eksplisit dengan label `[ASSUMPTION]` pada dokumentasi requirements selanjutnya.
