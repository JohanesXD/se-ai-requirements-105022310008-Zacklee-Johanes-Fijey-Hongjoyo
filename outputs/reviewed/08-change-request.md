# Change Request Evaluation: Student Task Management System

## 1. Change Request Information
- **CR-ID**: CR-01
- **Title**: Integrasi Fitur Pendeteksian Plagiarisme Otomatis (*Automated Plagiarism Detection*)
- **Requestor**: Lecturer (Dosen - Dr. Budi Santoso)
- **Description**: 
  Sistem harus dapat mendeteksi tingkat plagiarisme berkas tugas yang diunggah mahasiswa secara otomatis dengan membandingkan teks berkas tersebut terhadap repositori internet dan tugas-tugas mahasiswa lain. Hasil skor kemiripan (persentase plagiarisme) dan link laporan detail harus ditampilkan pada dasbor penilaian dosen.
- **Reason for Change**: 
  Dosen memerlukan alat bantu otomatis untuk meminimalkan kecurangan akademis (tindakan menyalin tugas teman atau internet) secara cepat tanpa harus melakukan pemeriksaan manual satu per satu di luar sistem.

---

## 2. Impact Analysis

### 2.1 Affected Requirements
- **FR-04 (Upload berkas)**: Alur pengunggahan berkas tugas mahasiswa harus memicu *trigger* untuk memanggil layanan pendeteksi plagiarisme sesaat setelah file disimpan di server.
- **FR-06 (Penilaian Dosen)**: Dasbor penilaian dosen perlu dimodifikasi untuk menampilkan skor kemiripan plagiarisme (misal: "Plagiarism Score: 12%") dan menautkan link laporan analisis Turnitin.
- **Penambahan Kebutuhan Baru**: Perlu didefinisikan FR baru (FR-10) untuk menangani proses pemindaian dan penyajian hasil plagiarisme.

### 2.2 Architecture & Database Impact
- **Database Schema Impact**:
  Tabel `submissions` dalam database harus ditambahkan beberapa kolom baru:
  - `plagiarism_percentage` (DECIMAL/INT): Menyimpan skor persentase kemiripan (0-100).
  - `plagiarism_report_url` (VARCHAR): Menyimpan URL tautan laporan detail plagiarisme.
  - `plagiarism_status` (VARCHAR/ENUM): Menyimpan status proses pemindaian (`PENDING`, `IN_PROGRESS`, `SUCCESS`, `FAILED`).
- **Integration & Architecture Impact**:
  - Diperlukan integrasi dengan API pihak ketiga seperti Turnitin, Copyleaks, atau PlagScan.
  - Pemindaian file membutuhkan waktu (beberapa menit). Proses ini **wajib dijalankan secara asinkronus** menggunakan antrean tugas (*message queue* / *background task processor* seperti Celery atau BullMQ) agar tidak memblokir respon server web utama saat mahasiswa menekan tombol "Submit".

### 2.3 Schedule & Storage Impact
- **Schedule Impact**: Menambah waktu pengerjaan (estimasi 2-3 minggu tambahan) untuk integrasi API, pengujian *background queue*, penanganan error API eksternal, dan penyesuaian UI.
- **Cost & Budget Impact**: Memerlukan anggaran tambahan untuk membayar lisensi penggunaan API pendeteksi plagiarisme eksternal per dokumen/tahun yang belum dianggarkan dalam anggaran MVP rilis pertama.

---

## 3. Final Decision
- **Status**: **Deferred (Ditangguhkan / Ditunda ke Fase 2)**
- **Justification**: 
  Meskipun fitur ini memiliki nilai akademik yang tinggi, biaya lisensi API eksternal belum dianggarkan dalam siklus anggaran MVP (Rilis Pertama) ini. Penambahan waktu pengerjaan selama 3 minggu juga akan menunda jadwal peluncuran sistem yang kritis. Sebagai solusi alternatif sementara, dosen tetap dapat mengunduh seluruh tugas mahasiswa dalam satu kelas berupa file ZIP (`FR-02`) lalu mengunggahnya secara manual ke akun Turnitin institusi resmi kampus yang sudah tersedia. Fitur integrasi otomatis ini ditunda dan akan ditinjau kembali pada pengembangan Fase 2.
