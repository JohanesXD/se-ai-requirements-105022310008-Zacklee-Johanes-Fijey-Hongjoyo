# Skill 5: Requirements Validation and Change Management

## Purpose
Memvalidasi kualitas spesifikasi kebutuhan (*requirements baseline*) berdasarkan aspek kelayakan, kejelasan, kelengkapan, konsistensi, dan keterujian, serta mengelola usulan perubahan kebutuhan (*Change Request*) melalui proses analisis dampak (*Impact Analysis*) dan pengambilan keputusan secara formal.

## When to Use
Gunakan skill ini pada fase akhir siklus Requirements Engineering untuk memvalidasi *baseline* sebelum disetujui, atau ketika terdapat usulan fitur/kebutuhan baru dari stakeholder di tengah jalannya siklus hidup proyek.

## Inputs
- Berkas kebutuhan sistem yang telah direview (`outputs/reviewed/03-requirements.md`)

## Required Context
AI harus membaca dokumen berikut sebelum menjalankan workflow:
1. [CASE.md](../../CASE.md)
2. [03-requirements.md](../../outputs/reviewed/03-requirements.md)

## Workflow
1. **Pemeriksaan Mutu Kebutuhan (Validation)**: Pilih minimal 5 requirements (baik fungsional maupun non-fungsional) dari `03-requirements.md`. Lakukan evaluasi mendalam terhadap 5 kriteria berikut:
   - **Clarity** (Apakah requirement ditulis dengan jelas dan bebas dari keambiguan?)
   - **Completeness** (Apakah detail kebutuhan sudah lengkap dan tidak menggantung?)
   - **Consistency** (Apakah requirement tidak bertentangan dengan requirement lainnya?)
   - **Feasibility** (Apakah requirement dapat diimplementasikan dengan teknologi dan batasan yang ada?)
   - **Testability** (Apakah ada metode yang jelas untuk menguji kebenaran requirement ini?)
2. **Dokumentasikan Hasil Validasi**: Catat hasil temuan audit tersebut. Jika ada kekurangan, tuliskan rekomendasi perbaikan/revisinya.
3. **Simulasi Permintaan Perubahan (Change Request)**: Buat simulasi 1 permintaan perubahan kebutuhan baru (misalnya: penambahan fitur *Plagiarism Detection* otomatis pada berkas tugas mahasiswa).
4. **Analisis Dampak (Impact Analysis)**: Lakukan analisis dampak terhadap usulan perubahan tersebut, yang mencakup:
   - Identifikasi berkas spesifikasi/requirement lama yang terpengaruh.
   - Dampak terhadap desain database dan arsitektur sistem.
   - Dampak terhadap jadwal pengerjaan dan kapasitas server.
5. **Formulasikan Keputusan**: Buat keputusan formal (Disetujui/Ditolak/Ditangguhkan) beserta justifikasi teknis dan bisnisnya.

## Output Format
Hasil keluaran wajib dipisah menjadi dua output utama (atau digabung jika dieksekusi bertahap):

### Format Dokumen 1: Validasi Kebutuhan (07-validation.md)
```markdown
# Requirements Validation Report: Student Task Management System

## 1. Requirements Validation Audit
| Req ID | Requirement Text | Validation Criteria | Evaluation Results (Clarity, Completeness, Consistency, Feasibility, Testability) | Correction / Recommendation |
|:---|:---|:---|:---|:---|
| [ID] | [Teks Req] | [Kriteria] | [Temuan evaluasi] | [Koreksi jika ada] |
| ... | ... | ... | ... | ... |
```

### Format Dokumen 2: Permintaan Perubahan (08-change-request.md)
```markdown
# Change Request Evaluation: Student Task Management System

## 1. Change Request Information
- **CR-ID**: CR-01
- **Title**: [Judul Perubahan]
- **Requestor**: [Aktor yang meminta]
- **Description**: [Deskripsi detail fitur/perubahan yang diminta]
- **Reason for Change**: [Alasan bisnis/akademik perubahan]

## 2. Impact Analysis
- **Affected Requirements**: [Daftar ID Requirement lama yang terpengaruh]
- **Architecture & Database Impact**: [Dampak pada skema DB/integrasi API]
- **Schedule & Storage Impact**: [Dampak pada waktu pengerjaan dan memori server]

## 3. Final Decision
- **Status**: [Approved / Rejected / Deferred]
- **Justification**: [Alasan pengambilan keputusan]
```

## Rules
- **Proses Validasi Harus Menguji Minimal 5 Requirements**.
- **Analisis Dampak Harus Konkret**: Jangan hanya menulis "berdampak pada database", jelaskan secara detail tabel mana yang terpengaruh (misal: "tabel Submissions perlu kolom tambahan hash plagiarism").
- Keputusan akhir atas Change Request harus didukung oleh argumen kelayakan teknis (*technical feasibility*) dan batasan kapasitas (*constraints*).

## Quality Checks
- Apakah tabel audit validasi mencakup minimal 5 requirement unik?
- Apakah analisis dampak change request mencakup aspek arsitektur, database, dan jadwal secara detail?
- Apakah keputusan akhir logis dan berdasar?

## Failure Conditions
Hentikan eksekusi jika:
- Dokumen `outputs/reviewed/03-requirements.md` tidak dapat diakses atau kosong.
- Change request yang disimulasikan melanggar batasan kritis sistem (misalnya: meminta file upload dinaikkan menjadi 5GB tanpa analisis dampak server storage).
