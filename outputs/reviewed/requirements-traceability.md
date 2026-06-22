# Requirements Traceability Matrix: Student Task Management System

Dokumen ini memetakan keterkaitan (*traceability*) antara setiap Kebutuhan Fungsional (Functional Requirement) dengan Stakeholder, Sumber Elicitation, User Story, Kriteria Penerimaan (Acceptance Criteria), dan Prioritas MoSCoW.

| Requirement ID | Stakeholder | Source ID | User Story ID | Acceptance Criteria | Priority |
|:---|:---|:---|:---|:---|:---|
| **FR-01** | Lecturer (Dosen) | EL-Lecturer-01 | US-02 / US-05 | AC-02.1, AC-05.1 | Must |
| **FR-02** | Lecturer (Dosen) | EL-Lecturer-02 | US-02 | AC-02.1, AC-02.2 | Should |
| **FR-03** | Student (Mahasiswa) | EL-Student-01 | US-01 | AC-01.1 | Must |
| **FR-04** | Student (Mahasiswa) | EL-Student-02 | US-01 | AC-01.1, AC-01.2, AC-01.3 | Must |
| **FR-05** | Student (Mahasiswa) | EL-Student-03 | US-06 | AC-06.1, AC-06.2, AC-06.3 | Should |
| **FR-06** | Lecturer (Dosen) | EL-Lecturer-03 | US-05 | AC-05.1, AC-05.2 | Must |
| **FR-07** | Administrator | EL-Admin-01 | US-03 | AC-03.1, AC-03.2 | Should |
| **FR-08** | Administrator | EL-Admin-02 | US-03 | AC-03.1, AC-03.2 | Must |
| **FR-09** | Student / Lecturer | EL-Student-03 | US-01 | AC-01.1 | Must |

### Keterangan Kode Sumber (Source ID):
- **EL-Lecturer-01**: Pembuatan tugas perkuliahan oleh dosen (`outputs/reviewed/02-elicitation.md#L12`).
- **EL-Lecturer-02**: Pengunduhan berkas tugas mahasiswa satu kelas sekaligus berbentuk ZIP (`outputs/reviewed/02-elicitation.md#L13`).
- **EL-Lecturer-03**: Penilaian tugas berupa angka 0-100 dan umpan balik tertulis (`outputs/reviewed/02-elicitation.md#L15`).
- **EL-Student-01**: Tampilan daftar tugas aktif diurutkan berdasarkan *deadline* terdekat (`outputs/reviewed/02-elicitation.md#L17`).
- **EL-Student-02**: Unggah berkas tugas dengan tipe dan ukuran file tervalidasi (`outputs/reviewed/02-elicitation.md#L18`).
- **EL-Student-03**: Pembatalan pengumpulan berkas (*unsubmit*) sebelum deadline (`outputs/reviewed/02-elicitation.md#L20`).
- **EL-Admin-01**: Impor akun massal menggunakan berkas Excel/CSV (`outputs/reviewed/02-elicitation.md#L24`).
- **EL-Admin-02**: Penonaktifan akun (*suspend*) alih-alih menghapusnya secara permanen (`outputs/reviewed/02-elicitation.md#L25`).
