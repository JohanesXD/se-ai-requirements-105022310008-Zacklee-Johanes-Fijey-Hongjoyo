# Skill Testing Report: Reusability Verification

Dokumen ini mendokumentasikan pengujian terhadap minimal 2 reusable AI skills yang telah dibuat menggunakan studi kasus yang berbeda, yaitu **Library Reservation System**, untuk membuktikan bahwa instruksi dalam `SKILL.md` bersifat generik dan dapat digunakan kembali (*reusable*).

---

## 1. Studi Kasus Uji: Library Reservation System
Sistem Perpustakaan Kampus yang digunakan oleh:
* **Library Member (Mahasiswa/Dosen)**: Mencari buku, memesan (*reserve*) buku yang sedang dipinjam, dan membatalkan pesanan.
* **Librarian (Pustakawan)**: Mengelola inventaris buku, memantau status peminjaman, dan mengonfirmasi reservasi.
* **Administrator**: Mengelola data anggota dan konfigurasi denda perpustakaan.

---

## 2. Pengujian Skill 1: Project Inception and Stakeholder Discovery

### 2.1 Input Test Run (Library Case)
- Menggunakan deskripsi sistem perpustakaan di atas sebagai input awal.
- Menjalankan perintah (*invocation*) sesuai `skills/01-inception/SKILL.md`.

### 2.2 Hasil Eksekusi AI (Test Run Output)
```markdown
# Project Inception and Stakeholder Discovery: Library Reservation System

## 1. Business Problem & Goals
### Business Problem
Anggota perpustakaan sering kesulitan meminjam buku populer karena tidak adanya sistem reservasi antrean yang adil dan transparan. Buku yang sedang dipinjam sering kali langsung diambil oleh orang lain tanpa mencatat antrean yang sah, menurunkan kepuasan anggota perpustakaan.

### Project Goals
- Menyediakan platform pencarian dan reservasi antrean buku secara real-time.
- Mengurangi waktu tunggu buku populer dengan sistem antrean terkompresi.

## 2. Stakeholders & User Needs
### 2.1 Primary Stakeholders
- **Library Member**:
  - **Needs**: Mencari katalog buku, melakukan reservasi buku yang sedang dipinjam, membatalkan reservasi.
  - **Pain Points**: Tidak tahu kapan buku yang dipinjam akan dikembalikan dan siapa pengantre berikutnya.
- **Librarian**:
  - **Needs**: Mengelola sirkulasi buku, memperbarui status pengembalian, dan memberi notifikasi ke pengantre pertama.

[... Terformat dengan Sempurna Sesuai SKILL.md ...]
```

### 2.3 Evaluasi Hasil Pengujian Skill 1
* **Success**: AI berhasil menyusun dokumen proyek inception untuk sistem perpustakaan dengan struktur yang sama persis seperti pada studi kasus utama.
* **Failure/Issue**: AI sempat mencampuradukkan status "Denda" ke dalam *In-Scope*, padahal denda akademik berada di luar cakupan manajemen peminjaman dasar.
* **Revisi Skill**: Menambahkan aturan di `Rules` `SKILL.md` agar AI lebih ketat membatasi solusi keuangan/denda jika tidak disebutkan dalam deskripsi kasus.

---

## 3. Pengujian Skill 3: Requirements Elaboration and Specification

### 3.1 Input Test Run (Library Case)
- Menggunakan draf hasil elicitation sistem perpustakaan (pencarian buku, booking, denda).
- Menjalankan perintah sesuai `skills/03-specification/SKILL.md`.

### 3.2 Hasil Eksekusi AI (Test Run Output)
```markdown
# Software Requirements Specification: Library Reservation System

## 1. Functional Requirements (FR)
| ID | Requirement Description | Source ID |
|:---|:---|:---|
| FR-01 | Anggota dapat mencari buku berdasarkan Judul, Penulis, atau ISBN. | EL-Member-01 |
| FR-02 | Anggota dapat melakukan reservasi buku yang sedang dipinjam oleh pengguna lain. | EL-Member-02 |
| FR-03 | Pustakawan dapat memperbarui status ketersediaan buku (Tersedia, Dipinjam, Direservasi). | EL-Librarian-01 |
| FR-04 | Sistem mengirim notifikasi email otomatis ke pengantre pertama saat buku dikembalikan. | EL-System-01 |

[... Terformat dengan Sempurna Sesuai SKILL.md ...]
```

### 3.3 Evaluasi Hasil Pengujian Skill 3
* **Success**: AI menghasilkan tabel FR dan NFR dengan parameter metrik terukur secara otomatis. User stories yang dihasilkan juga menggunakan format yang tepat (`As a... I want to... so that...`).
* **Failure/Issue**: Acceptance criteria pada kasus kegagalan pengembalian buku terlambat masih kurang mendefinisikan denda secara matematis.
* **Revisi Skill**: Diperbaiki pada `SKILL.md` dengan menambahkan instruksi agar skenario alternatif/kegagalan pada Acceptance Criteria wajib menyertakan nilai parameter batas (*boundary values*).
