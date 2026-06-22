# Project Assumptions and Constraints - Student Task Management System

Berikut adalah beberapa batasan dan asumsi awal terkait pengembangan dan operasional sistem:

## 1. Asumsi (Assumptions)
* **[ASSUMPTION] Single Sign-On (SSO)**: Sistem akan diintegrasikan dengan sistem Single Sign-On (SSO) milik kampus yang sudah ada untuk autentikasi login mahasiswa, dosen, dan administrator.
* **[ASSUMPTION] Penyimpanan Cloud**: Server penyimpanan berkas tugas menggunakan layanan penyimpanan cloud kampus dengan estimasi kapasitas awal yang cukup untuk satu tahun akademik.
* **[ASSUMPTION] Format Waktu**: Semua tenggat waktu pengumpulan tugas akan mengikuti Zona Waktu Indonesia Barat (WIB / UTC+7).

## 2. Batasan (Constraints)
* **[CONSTRAINT] Ukuran Berkas**: Setiap berkas tugas yang diunggah oleh mahasiswa dibatasi maksimal 20 MB per file untuk menghindari kepenuhan ruang penyimpanan.
* **[CONSTRAINT] Format File**: Format file yang diizinkan untuk diunggah dibatasi hanya pada format `.pdf`, `.zip`, `.rar`, `.docx`, `.xlsx`, dan `.pptx`.
* **[CONSTRAINT] Integrasi API**: Sistem harus mengambil data kelas dan mata kuliah yang aktif melalui API akademik yang disediakan oleh Biro Teknologi Informasi kampus.
