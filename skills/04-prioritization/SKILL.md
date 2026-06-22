# Skill 4: Negotiation and Prioritization

## Purpose
Menyelesaikan konflik antar-kebutuhan stakeholder, menganalisis ketergantungan (*dependency*) antar-requirements, serta memprioritaskan seluruh kebutuhan fungsional sistem menggunakan metode MoSCoW (Must, Should, Could, Won't) dengan alasan/justifikasi bisnis yang rasional.

## When to Use
Gunakan skill ini setelah dokumen spesifikasi kebutuhan perangkat lunak (Functional & Non-Functional Requirements) selesai disusun, untuk menyepakati lingkup kerja rilis awal (MVP - *Minimum Viable Product*).

## Inputs
- Berkas kebutuhan sistem yang telah direview (`outputs/reviewed/03-requirements.md`)

## Required Context
AI harus membaca dokumen berikut sebelum menjalankan workflow:
1. [CASE.md](../../CASE.md)
2. [01-inception.md](../../outputs/reviewed/01-inception.md)
3. [03-requirements.md](../../outputs/reviewed/03-requirements.md)

## Workflow
1. **Analisis Konflik & Negosiasi**: Identifikasi minimal 1 konflik kebutuhan antar-stakeholder (misalnya: keinginan mahasiswa mengunggah file tanpa batas ukuran vs. kekhawatiran tim IT terkait kapasitas penyimpanan server). Jabarkan usulan resolusi/negosiasi konflik tersebut beserta *trade-off*-nya.
2. **Pemetaan Ketergantungan (Dependency Analysis)**: Menganalisis ketergantungan antar-requirements fungsional. Jelaskan requirement mana yang harus diimplementasikan terlebih dahulu sebelum requirement lainnya dapat berjalan (misalnya: penilaian tugas bergantung pada adanya tugas yang dikumpulkan).
3. **MoSCoW Prioritization**: Klasifikasikan **seluruh** kebutuhan fungsional (`FR-01` s.d. `FR-09`) ke dalam kategori berikut:
   - **Must Have (M)**: Kebutuhan mutlak yang jika tidak ada, sistem tidak dapat diluncurkan/tidak berfungsi.
   - **Should Have (S)**: Kebutuhan penting tetapi tidak kritis untuk rilis awal, dapat ditunda dengan solusi alternatif sementara.
   - **Could Have (C)**: Kebutuhan "bagus untuk dimiliki" yang meningkatkan pengalaman pengguna tetapi dapat diabaikan jika waktu/anggaran terbatas.
   - **Won't Have (W)**: Kebutuhan yang tidak akan diimplementasikan pada fase rilis saat ini (akan ditinjau kembali di rilis mendatang).
4. **Berikan Justifikasi**: Berikan alasan bisnis atau teknis yang logis dan kuat untuk setiap penetapan prioritas tersebut.
5. **Jalankan Quality Checks**: Pastikan semua FR terklasifikasi tanpa ada yang terlewat.

## Output Format
Output wajib ditulis dalam format Markdown dengan struktur berikut:

```markdown
# Requirements Prioritization & Negotiation: Student Task Management System

## 1. Stakeholder Conflict Resolutions
### Conflict 1: [Nama Konflik]
- **Stakeholders Involved**: [Stakeholder A] vs [Stakeholder B]
- **Conflict Description**: [Deskripsi perdebatan kebutuhan]
- **Resolution & Trade-off**: [Keputusan negosiasi dan kompromi yang diambil]

## 2. Requirements Dependencies
- **[ID Requirement]** bergantung pada **[ID Requirement]**: [Penjelasan logis ketergantungan]

## 3. MoSCoW Prioritization Matrix
| ID | Requirement Description | Category (M/S/C/W) | Dependency | Priority Justification |
|:---|:---|:---|:---|:---|
| FR-01 | [Deskripsi] | [M/S/C/W] | [ID/None] | [Alasan logis] |
| ... | ... | ... | ... | ... |
```

## Rules
- **Dilarang melewatkan satupun Functional Requirement** yang telah dispesifikasikan di `03-requirements.md` (semua harus masuk dalam tabel prioritas).
- Alasan prioritas harus dikaitkan dengan nilai bisnis (*business value*), kemudahan teknis (*technical feasibility*), atau kebutuhan operasional kritis (*critical operation*).
- Status prioritas harus logis (misalnya: tidak boleh meletakkan requirement *penilaian* sebagai "Must Have" jika *pengunggahan tugas* diletakkan sebagai "Could Have" karena ada ketergantungan teknis).

## Quality Checks
- Apakah semua FR dari berkas spesifikasi sudah terdaftar dalam tabel prioritas?
- Apakah ada konflik stakeholder yang diidentifikasi secara nyata?
- Apakah analisis ketergantungan (*dependency*) logis dan konsisten dengan kategori prioritas?

## Failure Conditions
Hentikan eksekusi jika:
- Dokumen `outputs/reviewed/03-requirements.md` tidak dapat diakses atau kosong.
- Terdapat requirement "Must Have" yang bergantung pada requirement berkategori "Could Have" atau "Won't Have".
