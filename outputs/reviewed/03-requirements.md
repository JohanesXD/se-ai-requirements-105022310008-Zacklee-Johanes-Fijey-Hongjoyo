# Software Requirements Specification: Student Task Management System

## 1. Functional Requirements (FR)
| ID | Requirement Description | Source ID |
|:---|:---|:---|
| FR-01 | Dosen dapat membuat tugas baru dengan menentukan judul, instruksi/deskripsi, dan tenggat waktu (*deadline*). | outputs/reviewed/02-elicitation.md#L12 |
| FR-02 | Dosen dapat mengunduh seluruh file tugas mahasiswa dalam satu kelas sekaligus sebagai satu file ZIP terkompresi. | outputs/reviewed/02-elicitation.md#L13 |
| FR-03 | Mahasiswa dapat melihat daftar tugas perkuliahan aktif yang otomatis diurutkan berdasarkan tenggat waktu terdekat. | outputs/reviewed/02-elicitation.md#L17 |
| FR-04 | Mahasiswa dapat mengunggah berkas pengumpulan tugas dengan tipe file yang diizinkan (.pdf, .zip, .rar, .docx, .xlsx, .pptx). | outputs/reviewed/02-elicitation.md#L18 |
| FR-05 | Mahasiswa dapat membatalkan pengiriman berkas tugas (*unsubmit*) sebelum melewati tenggat waktu yang ditentukan. | outputs/reviewed/02-elicitation.md#L20 |
| FR-06 | Dosen dapat memberikan nilai angka (0-100) dan umpan balik (*feedback*) tertulis langsung pada tugas yang dikumpulkan mahasiswa. | outputs/reviewed/02-elicitation.md#L15 |
| FR-07 | Administrator dapat mengimpor data dosen, mahasiswa, dan mata kuliah secara massal menggunakan file format Excel/CSV. | outputs/reviewed/02-elicitation.md#L24 |
| FR-08 | Administrator dapat mengubah status akun pengguna menjadi nonaktif (*suspended*) alih-alih menghapus data secara permanen. | outputs/reviewed/02-elicitation.md#L25 |
| FR-09 | Sistem secara otomatis mengubah nama file tugas yang diunggah mahasiswa menjadi format standar (`NIM_Nama_TugasID.ekstensi`). | outputs/reviewed/02-elicitation.md#L36 |

## 2. Non-Functional Requirements (NFR)
| ID | Category | Metric-based Requirement | Testability / Verification Method |
|:---|:---|:---|:---|
| NFR-01 | Performance | Waktu respons sistem (*page load time*) maksimal 3 detik pada kondisi jaringan standar (bandwidth minimal 5 Mbps). | Diuji menggunakan Google Lighthouse audit dan JMeter load testing dengan 500 pengguna konkuren. |
| NFR-02 | Security | Semua kata sandi pengguna wajib dienkripsi menggunakan algoritma bcrypt sebelum disimpan, dan transmisi data nilai menggunakan protokol HTTPS (TLS 1.3). | Audit keamanan kode sumber (Static Analysis) dan pengujian penetrasi (*penetration testing*) menggunakan OWASP ZAP. |
| NFR-03 | Usability | Sistem harus mendapatkan skor System Usability Scale (SUS) minimal 75 dari hasil kuesioner pengujian oleh 20 responden pengguna. | Melakukan usability testing dengan metode kuesioner SUS setelah masa uji coba sistem selesai. |
| NFR-04 | Reliability | Tingkat ketersediaan sistem (*availability*) minimal mencapai 99.9% selama masa jam akademik aktif (07:00 s.d. 22:00 WIB). | Memantau uptime server menggunakan tool monitoring eksternal (seperti UptimeRobot) selama 30 hari berturut-turut. |
| NFR-05 | Data Integrity | Sistem harus memvalidasi integritas berkas tugas yang diunggah untuk mendeteksi file rusak atau berukuran 0 KB. | Pengujian fungsional otomatis dengan mencoba mengunggah file kosong (0 KB) dan memastikan sistem menolaknya. |

## 3. Business Rules (BR)
- **BR-01 (Grade Range Rule)**: Input nilai tugas mahasiswa oleh dosen wajib berupa bilangan bulat (*integer*) dengan nilai minimum 0 dan nilai maksimum 100.
- **BR-02 (Submission Lifecycle Rule)**: Mahasiswa hanya diperbolehkan melakukan pembatalan (*unsubmit*) atau pengunggahan berkas tugas baru apabila status tugas saat ini belum diberikan nilai oleh dosen DAN waktu pengiriman belum melewati tenggat waktu yang ditentukan (*deadline*).
