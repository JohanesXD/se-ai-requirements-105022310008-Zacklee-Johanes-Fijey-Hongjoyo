# Skill 3: Requirements Elaboration and Specification

## Purpose
Mengelaborasikan hasil temuan elicitation menjadi spesifikasi kebutuhan perangkat lunak yang formal, terukur, dan teruji. Skill ini menghasilkan daftar Functional Requirements (FR), Non-Functional Requirements (NFR), Business Rules (BR), serta User Stories lengkap dengan Acceptance Criteria (AC).

## When to Use
Gunakan skill ini setelah tahap Requirements Elicitation selesai untuk menyusun dokumen spesifikasi kebutuhan sistem formal.

## Inputs
- Berkas hasil elicitation yang telah direview (`outputs/reviewed/02-elicitation.md`)

## Required Context
AI harus membaca dokumen berikut sebelum menjalankan workflow:
1. [CASE.md](../../CASE.md)
2. [01-inception.md](../../outputs/reviewed/01-inception.md)
3. [02-elicitation.md](../../outputs/reviewed/02-elicitation.md)

## Workflow
1. **Definisikan Functional Requirements (FR)**: Susun minimal 8 kebutuhan fungsional sistem. Setiap kebutuhan wajib memiliki ID unik terurut (`FR-01`, `FR-02`, dst.) dan tautan ke sumber kebutuhan elicitation.
2. **Definisikan Non-Functional Requirements (NFR)**: Susun minimal 4 kebutuhan non-fungsional sistem yang dikategorikan berdasarkan aspek kualitas (Usability, Security, Performance, Reliability, Data Integrity). Setiap NFR wajib menggunakan parameter yang **terukur dan dapat diuji** (hindari kata sifat seperti "cepat", "aman", "mudah").
3. **Definisikan Business Rules (BR)**: Susun minimal 2 aturan bisnis yang membatasi operasi sistem atau perilaku pengguna.
4. **Susun User Stories (US)**: Buat minimal 6 cerita pengguna yang mencakup perwakilan ketiga aktor utama (Lecturer, Student, Administrator). Gunakan format:
   `As a [user role], I want to [action] so that [benefit/value].`
5. **Rancang Acceptance Criteria (AC)**: Untuk setiap User Story, buat minimal 2 kriteria penerimaan yang jelas menggunakan format skenario (*Given-When-Then*) atau daftar checklist yang teruji secara logis (mencakup skenario sukses dan skenario gagal/kondisi alternatif).
6. **Jalankan Quality Checks**: Pastikan semua dokumen konsisten dan tidak tumpang tindih.

## Output Format
Hasil keluaran harus dipisah menjadi dua output utama (atau disatukan dalam satu template jika dijalankan secara bertahap):

### Format Dokumen 1: Kebutuhan Sistem (03-requirements.md)
```markdown
# Software Requirements Specification: Student Task Management System

## 1. Functional Requirements (FR)
| ID | Requirement Description | Source ID |
|:---|:---|:---|
| FR-01 | [Deskripsi fungsionalitas] | [Source ID, misal: EL-01] |
| ... | ... | ... |

## 2. Non-Functional Requirements (NFR)
| ID | Category | Metric-based Requirement | Testability / Verification Method |
|:---|:---|:---|:---|
| NFR-01 | [Kategori, misal: Performance] | [Deskripsi metrik terukur] | [Cara menguji] |
| ... | ... | ... | ... |

## 3. Business Rules (BR)
- **BR-01**: [Penjelasan aturan bisnis]
- **BR-02**: [Penjelasan aturan bisnis]
```

### Format Dokumen 2: User Stories (04-user-stories.md)
```markdown
# User Stories and Acceptance Criteria: Student Task Management System

## User Stories & Acceptance Criteria List

### US-01: [Judul User Story]
- **Story**: As a [role], I want to [action] so that [value].
- **Acceptance Criteria**:
  - **AC-01.1 (Scenario: Success)**: Given... When... Then...
  - **AC-01.2 (Scenario: Alternative/Failure)**: Given... When... Then...

[Ulangi minimal untuk US-02 s.d US-06]
```

## Rules
- **Metrik NFR Wajib Terukur**: Jangan gunakan kata sifat ambigu tanpa angka ukuran (misalnya "Sistem harus aman" -> ganti dengan "Semua data nilai harus dienkripsi menggunakan AES-256").
- **Acceptance Criteria Wajib Memiliki Kasus Kegagalan/Alternatif**: Jangan hanya membuat skenario sukses. Harus ada minimal satu skenario penolakan (misal: "Jika ukuran file > 20MB, tampilkan pesan error").
- Setiap Functional Requirement harus dapat ditelusuri kembali ke sumber elicitation di `outputs/reviewed/02-elicitation.md`.

## Quality Checks
- Apakah jumlah FR minimal 8, NFR minimal 4, BR minimal 2, US minimal 6, dan AC minimal 2 per story?
- Apakah ada NFR yang menggunakan kata sifat subjektif tanpa metrik?
- Apakah setiap User Story memiliki minimal satu Acceptance Criteria yang menguji kondisi batas atau kegagalan?

## Failure Conditions
Hentikan eksekusi jika:
- Dokumen `outputs/reviewed/02-elicitation.md` tidak dapat diakses atau kosong.
- Total kebutuhan fungsional yang diturunkan dari berkas masukan kurang dari 8 kebutuhan unik.

## Example Invocation
```text
Read CASE.md, outputs/reviewed/02-elicitation.md, and skills/03-specification/SKILL.md.
Execute the skill exactly as written.
Generate outputs/raw/requirements-ai-output.md containing both documents according to the defined Output Format.
```
