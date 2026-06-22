# Software Requirements Specification & User Stories (Raw AI Output)

## Part 1: Kebutuhan Sistem

### 1. Functional Requirements (FR)
| ID | Requirement Description | Source ID |
|:---|:---|:---|
| FR-01 | Dosen dapat membuat tugas baru dengan menentukan judul, deskripsi, dan tenggat waktu. | EL-Lecturer-01 |
| FR-02 | Dosen dapat mengunduh seluruh file tugas mahasiswa dalam bentuk ZIP. | EL-Lecturer-02 |
| FR-03 | Mahasiswa dapat melihat daftar tugas perkuliahan yang diurutkan berdasarkan deadline terdekat. | EL-Student-01 |
| FR-04 | Mahasiswa dapat mengunggah berkas pengumpulan tugas mereka. | EL-Student-02 |
| FR-05 | Mahasiswa dapat melakukan unsubmit berkas tugas untuk melakukan revisi pengumpulan. | EL-Student-03 |
| FR-06 | Dosen dapat memberikan nilai angka dan feedback tertulis pada tugas mahasiswa. | EL-Lecturer-03 |
| FR-07 | Administrator dapat mengimpor data dosen, mahasiswa, dan mata kuliah via CSV/Excel secara massal. | EL-Admin-01 |
| FR-08 | Dosen dapat menginput nilai tugas mahasiswa dalam rentang 0-100. | EL-Lecturer-03 |
| FR-09 | Sistem harus mengirimkan notifikasi chat instan ke mahasiswa jika nilai dipublikasikan. | EL-Student-02 |

### 2. Non-Functional Requirements (NFR)
- **NFR-01 (Performance)**: Sistem harus merespons pengaksesan halaman utama dengan sangat cepat.
- **NFR-02 (Security)**: Halaman login sistem harus sangat aman sehingga tidak bisa diretas oleh hacker.
- **NFR-03 (Usability)**: Antarmuka sistem harus user-friendly dan mudah dipahami oleh dosen yang sudah berumur.
- **NFR-04 (Reliability)**: Sistem harus selalu online 24 jam sehari tanpa mengalami error atau downtime.

### 3. Business Rules (BR)
- **BR-01**: Dosen hanya diperkenankan menginput nilai bulat dengan rentang 0-100.
- **BR-02**: Mahasiswa tidak diizinkan melakukan *unsubmit* jika status tugas telah dinilai.

---

## Part 2: User Stories & Acceptance Criteria

### US-01: Upload Tugas
- **Story**: As a Student, I want to upload my assignment file so that my lecturer can grade it.
- **Acceptance Criteria**:
  - **AC-01.1**: Given student is on the assignment detail page, When they click upload and select a file, Then the file is uploaded.
  - **AC-01.2**: Given student has uploaded a file, When they view the status, Then it shows 'Submitted'.

### US-02: Download ZIP Kelas
- **Story**: As a Lecturer, I want to download all student submissions in a class as a ZIP file so that I can grade offline.
- **Acceptance Criteria**:
  - **AC-02.1**: Given lecturer is on the class assignment summary page, When they click 'Download All', Then a ZIP file is generated.
  - **AC-02.2**: Given the ZIP file is generated, When it is downloaded, Then it contains all files renamed with student names.

### US-03: Import Akun massal
- **Story**: As an Admin, I want to upload an Excel file of users so that I can create accounts quickly.
- **Acceptance Criteria**:
  - **AC-03.1**: Given admin is on the user management page, When they upload a valid CSV, Then all users are created.
  - **AC-03.2**: Given users are created, When admin checks the list, Then the new users appear.

### US-04: Notifikasi Nilai
- **Story**: As a Student, I want to get email and push notification when my assignment is graded so that I can see it immediately.
- **Acceptance Criteria**:
  - **AC-04.1**: Given student has submitted work, When lecturer saves the grade, Then a notification is sent.

### US-05: Penilaian Dosen
- **Story**: As a Lecturer, I want to input grades and feedback so that students know their performance.
- **Acceptance Criteria**:
  - **AC-05.1**: Given lecturer is on submission grading page, When they input grade and feedback, Then the grade is saved.

### US-06: Unsubmit Tugas
- **Story**: As a Student, I want to unsubmit my task so that I can fix mistakes.
- **Acceptance Criteria**:
  - **AC-06.1**: Given student has submitted, When they click unsubmit, Then the submission is removed.
