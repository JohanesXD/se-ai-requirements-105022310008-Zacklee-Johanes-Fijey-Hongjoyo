# Requirements Prioritization & Negotiation (Raw AI Output)

## 1. Stakeholder Conflict Resolutions
- Ada konflik antara mahasiswa yang ingin sistem yang sangat canggih dan IT Kampus yang ingin hemat biaya. Kami memutuskan untuk memilih opsi sistem yang murah saja tanpa fitur aneh-aneh.

## 2. Requirements Dependencies
- FR-06 (Penilaian Dosen) bergantung pada FR-04 (Upload tugas mahasiswa).

## 3. MoSCoW Prioritization Matrix
| ID | Requirement Description | Category (M/S/C/W) | Dependency | Priority Justification |
|:---|:---|:---|:---|:---|
| FR-01 | Dosen dapat membuat tugas baru. | Must (M) | None | Dosen harus bisa membuat tugas agar sistem berguna. |
| FR-02 | Dosen dapat mengunduh seluruh file tugas mahasiswa sebagai ZIP. | Should (S) | None | Bagus untuk menghemat waktu dosen, tetapi bisa diunduh manual. |
| FR-03 | Mahasiswa dapat melihat daftar tugas aktif. | Must (M) | None | Kebutuhan dasar mahasiswa untuk melihat tugas mereka. |
| FR-04 | Mahasiswa dapat mengunggah berkas pengumpulan tugas. | Should (S) | None | Penting, namun jika belum siap bisa dikumpulkan manual lewat email dulu. |
| FR-05 | Mahasiswa dapat melakukan unsubmit berkas tugas. | Could (C) | FR-04 | Hanya pelengkap saja jika mahasiswa salah mengunggah file. |
| FR-06 | Dosen dapat memberikan nilai angka dan umpan balik tertulis. | Must (M) | FR-04 | Fitur inti dosen untuk memberikan penilaian akademik. |
| FR-07 | Administrator dapat mengimpor data massal pengguna via CSV/Excel. | Must (M) | None | Admin harus bisa memasukkan data pengguna di awal. |

*Catatan: FR-08 dan FR-09 tidak dimasukkan dalam prioritas karena dianggap otomatis merupakan bagian dari sistem.*
