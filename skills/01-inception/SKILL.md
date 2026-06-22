# Skill 1: Project Inception and Stakeholder Discovery

## Purpose
Mengidentifikasi masalah bisnis, tujuan proyek, ruang lingkup awal, stakeholder utama dan sekunder, kebutuhan masing-masing stakeholder, serta asumsi dan batasan awal proyek secara sistematis.

## When to Use
Gunakan skill ini pada awal siklus hidup proyek Requirements Engineering sebelum melangkah ke proses elicitation detail, analisis kebutuhan, atau pembuatan user stories.

## Inputs
- Deskripsi awal studi kasus (`CASE.md`)
- Catatan pertemuan stakeholder (`inputs/stakeholder-notes.md`)
- Dokumen asumsi dan batasan awal (`inputs/assumptions.md`)

## Required Context
AI harus membaca dokumen berikut sebelum menjalankan workflow:
1. [CASE.md](../../CASE.md)
2. [stakeholder-notes.md](../../inputs/stakeholder-notes.md)
3. [assumptions.md](../../inputs/assumptions.md)

## Workflow
1. **Analisis Masalah Bisnis**: Ringkas masalah bisnis yang melatarbelakangi kebutuhan sistem dalam maksimal dua paragraf. Pastikan untuk memisahkan antara masalah (apa yang dirasakan) dan solusi (fitur yang diinginkan).
2. **Definisikan Tujuan Bisnis**: Identifikasi tujuan utama proyek secara spesifik dan dapat dievaluasi di akhir proyek.
3. **Identifikasi Stakeholder**: Klasifikasikan stakeholder menjadi stakeholder primer (pengguna langsung) dan sekunder (pengguna tidak langsung/pendukung).
4. **Analisis Kebutuhan Stakeholder**: Jabarkan kebutuhan spesifik dan masalah utama masing-masing stakeholder berdasarkan input yang tersedia.
5. **Tentukan Scope Proyek**: Bagi ruang lingkup proyek secara tegas menjadi:
   - **In-Scope**: Fitur/proses bisnis yang masuk dalam batasan pengembangan sistem.
   - **Out-of-Scope**: Fitur/proses bisnis yang tidak akan dikembangkan pada fase ini.
6. **Identifikasi Asumsi & Batasan**: Daftarkan asumsi dan batasan proyek. Berikan label `[ASSUMPTION]` untuk setiap asumsi dan `[CONSTRAINT]` untuk batasan.
7. **Identifikasi Open Questions**: Jika ada informasi penting yang belum jelas atau tidak tersedia di dokumen input, tandai secara eksplisit dengan label `[OPEN QUESTION]`.
8. **Jalankan Quality Checks**: Lakukan pemeriksaan mandiri sebelum menghasilkan output final.

## Output Format
Output wajib ditulis dalam format Markdown dengan struktur berikut:

```markdown
# Project Inception and Stakeholder Discovery: Student Task Management System

## 1. Business Problem & Goals
### Business Problem
[Deskripsi masalah bisnis, maks 2 paragraf]

### Project Goals
[Daftar tujuan proyek yang dapat diukur]

## 2. Stakeholders & User Needs
### 2.1 Primary Stakeholders
- **[Nama Peran/Aktor]**:
  - **Needs**: [Kebutuhan stakeholder]
  - **Pain Points**: [Masalah utama stakeholder]

### 2.2 Secondary Stakeholders
- **[Nama Peran/Aktor]**:
  - **Needs**: [Kebutuhan]
  - **Pain Points**: [Masalah]

## 3. Project Scope
### 3.1 In-Scope
- [Fitur/proses yang masuk scope]

### 3.2 Out-of-Scope
- [Fitur/proses yang berada di luar scope]

## 4. Assumptions & Constraints
- **[ASSUMPTION]** [Deskripsi asumsi]
- **[CONSTRAINT]** [Deskripsi batasan]

## 5. Open Questions
- **[OPEN QUESTION]** [Pertanyaan terbuka yang butuh klarifikasi lebih lanjut]
```

## Rules
- **Dilarang keras mengarang fakta** yang tidak ada di dalam dokumen `CASE.md` atau `inputs/stakeholder-notes.md`.
- Semua asumsi di luar berkas input wajib ditandai secara eksplisit dengan label `[ASSUMPTION]`.
- Informasi penting yang tidak ada atau kurang jelas wajib ditandai dengan label `[OPEN QUESTION]`.
- Hindari menyarankan solusi teknologi spesifik di bagian masalah bisnis (misal: "Membuat database MySQL" -> gantilah dengan "Menyimpan data secara terintegrasi dan aman").

## Quality Checks
- Apakah masalah bisnis dijelaskan tanpa mencampuradukkannya dengan deskripsi fitur solusi?
- Apakah batasan scope (In-Scope dan Out-of-Scope) sudah jelas dan tegas?
- Apakah setiap stakeholder memiliki daftar kebutuhan yang relevan dengan perannya?
- Apakah asumsi telah dipisahkan dari fakta dan ditandai secara benar dengan label `[ASSUMPTION]`?
- Apakah tujuan proyek dapat diverifikasi/diuji keberhasilannya?

## Failure Conditions
Hentikan eksekusi dan minta klarifikasi dari Requirements Engineer jika:
- Berkas `CASE.md` tidak tersedia atau kosong.
- Stakeholder utama tidak didefinisikan sama sekali di dalam berkas masukan.
- Terdapat kontradiksi dasar antara catatan stakeholder yang tidak bisa diselesaikan secara logis.

## Example Invocation
```text
Read CASE.md, inputs/stakeholder-notes.md, inputs/assumptions.md, and skills/01-inception/SKILL.md.
Execute the skill exactly as written.
Save the result using the output structure defined in the skill.
Do not invent missing facts. Mark assumptions and open questions explicitly.
```

## Expected Output Example
```markdown
# Project Inception and Stakeholder Discovery: Student Task Management System

## 1. Business Problem & Goals
### Business Problem
Proses pengelolaan tugas perkuliahan saat ini masih dilakukan secara manual dan terdistribusi melalui email atau aplikasi pesan instan. Hal ini menyebabkan kesulitan pelacakan tugas bagi dosen dan potensi terlewatnya tenggat waktu bagi mahasiswa karena tidak adanya sistem pengingat terpusat.

### Project Goals
- Menyediakan platform tunggal untuk mendistribusikan, mengumpulkan, dan menilai tugas perkuliahan.
- Menurunkan tingkat keterlambatan pengumpulan tugas mahasiswa sebesar 50%.
- Memudahkan dosen dalam melacak status pengumpulan tugas secara *real-time*.

[... dan seterusnya sesuai struktur Output Format ...]
```
