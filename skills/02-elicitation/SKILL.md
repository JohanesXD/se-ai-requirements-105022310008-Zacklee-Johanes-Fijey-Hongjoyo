# Skill 2: Requirements Elicitation

## Purpose
Menggali kebutuhan fungsional dan non-fungsional secara mendalam menggunakan teknik elicitation terstruktur, serta menganalisis perbedaan antara kebutuhan yang dinyatakan secara eksplisit (tersurat) dan implisit (tersirat).

## When to Use
Gunakan skill ini setelah tahap Project Inception selesai untuk memetakan hasil wawancara, kuesioner, atau observasi awal menjadi kebutuhan yang siap didefinisikan.

## Inputs
- Dokumen Project Inception yang telah direview (`outputs/reviewed/01-inception.md`)
- Catatan pertemuan awal (`inputs/stakeholder-notes.md`)
- Berkas tanya jawab wawancara lanjutan (`inputs/interview-answers.md`)

## Required Context
AI harus membaca dokumen berikut sebelum menjalankan workflow:
1. [CASE.md](../../CASE.md)
2. [01-inception.md](../../outputs/reviewed/01-inception.md)
3. [stakeholder-notes.md](../../inputs/stakeholder-notes.md)
4. [interview-answers.md](../../inputs/interview-answers.md)

## Workflow
1. **Analisis Teknik Elicitation**: Identifikasi teknik elicitation yang telah digunakan (misalnya *Interview*, *Document Analysis*, *Brainstorming*) dan jelaskan justifikasi pemilihannya.
2. **Pemetaan Tanya Jawab (Q&A Mapping)**: Ringkas hasil tanya jawab dari `inputs/interview-answers.md` yang dikelompokkan berdasarkan stakeholder.
3. **Analisis Kebutuhan Eksplisit vs Implisit**:
   - Identifikasi kebutuhan **Eksplisit**: kebutuhan yang dinyatakan secara langsung oleh stakeholder dalam teks masukan. Beri label `[EXPLICIT]`.
   - Identifikasi kebutuhan **Implisit**: kebutuhan yang tidak dinyatakan secara langsung, tetapi secara logis dan teknis sangat krusial agar sistem dapat berjalan dengan baik, aman, dan handal. Beri label `[IMPLICIT]`.
4. **Analisis Kendala/Keterbatasan Sistem**: Identifikasi batasan-batasan teknis baru yang terungkap selama sesi wawancara.
5. **Jalankan Quality Checks**: Periksa apakah pemetaan kebutuhan konsisten dengan ruang lingkup proyek.

## Output Format
Output wajib ditulis dalam format Markdown dengan struktur berikut:

```markdown
# Requirements Elicitation: Student Task Management System

## 1. Elicitation Techniques & Justification
- **[Nama Teknik]**: [Penjelasan mengapa teknik ini digunakan dan bagaimana ia membantu menggali kebutuhan]

## 2. Key Interview Highlights
### 2.1 Lecturer Interviews
- **Topik**: [Topik wawancara]
  - **Temuan**: [Ringkasan jawaban dosen]

### 2.2 Student Interviews
- **Topik**: [Topik wawancara]
  - **Temuan**: [Ringkasan jawaban mahasiswa]

### 2.3 Administrator Interviews
- **Topik**: [Topik wawancara]
  - **Temuan**: [Ringkasan jawaban administrator]

## 3. Explicit vs. Implicit Requirements
### 3.1 Lecturer Requirements
- **[EXPLICIT]** [Deskripsi kebutuhan eksplisit]
- **[IMPLICIT]** [Deskripsi kebutuhan implisit]

### 3.2 Student Requirements
- **[EXPLICIT]** [Deskripsi kebutuhan eksplisit]
- **[IMPLICIT]** [Deskripsi kebutuhan implisit]

### 3.3 Administrator Requirements
- **[EXPLICIT]** [Deskripsi kebutuhan eksplisit]
- **[IMPLICIT]** [Deskripsi kebutuhan implisit]

## 4. Elicitation Constraints & Business Rules
- **[CONSTRAINT]** [Batasan teknis hasil elicitation]
- **[BUSINESS RULE]** [Aturan bisnis hasil elicitation]
```

## Rules
- **Dilarang keras berasumsi atau menambahkan kebutuhan fungsional di luar studi kasus** yang tidak memiliki dasar dari dokumen input (misalnya: tidak boleh menambahkan fitur pembayaran online, fitur share ke media sosial, dll.).
- Klasifikasi `[EXPLICIT]` dan `[IMPLICIT]` harus dipisahkan secara jelas.
- Kebutuhan implisit harus logis, realistis, dan berorientasi pada kualitas sistem (seperti *security*, *data integrity*, *usability*).
- Setiap temuan harus merujuk pada catatan di `inputs/stakeholder-notes.md` atau `inputs/interview-answers.md`.

## Quality Checks
- Apakah semua kebutuhan eksplisit yang dicatat benar-benar memiliki referensi langsung di berkas masukan?
- Apakah kebutuhan implisit benar-benar relevan dan bukan merupakan fitur baru yang diada-adakan oleh AI?
- Apakah batasan (*constraints*) dan aturan bisnis (*business rules*) didefinisikan secara spesifik?

## Failure Conditions
Hentikan eksekusi dan minta klarifikasi jika:
- Dokumen `inputs/interview-answers.md` tidak tersedia atau kosong.
- Terdapat kebutuhan dari stakeholder yang bertentangan langsung dengan batasan yang didefinisikan pada tahap *inception* (misal ukuran file diubah menjadi 2GB secara sepihak).

## Example Invocation
```text
Read CASE.md, outputs/reviewed/01-inception.md, inputs/stakeholder-notes.md, inputs/interview-answers.md, and skills/02-elicitation/SKILL.md.
Execute the skill exactly as written.
Save the result using the output structure defined in the skill.
Do not invent missing facts. Mark assumptions and open questions explicitly.
```

## Expected Output Example
```markdown
# Requirements Elicitation: Student Task Management System

## 1. Elicitation Techniques & Justification
- **Interview (Wawancara)**: Digunakan untuk menggali kebutuhan personal, keluhan, dan harapan langsung dari Dosen, Mahasiswa, dan Administrator.

## 2. Key Interview Highlights
### 2.1 Lecturer Interviews
- **Topik**: Pengunduhan file tugas mahasiswa.
  - **Temuan**: Dosen membutuhkan fitur untuk mengunduh semua tugas mahasiswa dalam satu kelas sekaligus dalam bentuk satu file ZIP terkompresi.

[... dan seterusnya sesuai struktur Output Format ...]
```
