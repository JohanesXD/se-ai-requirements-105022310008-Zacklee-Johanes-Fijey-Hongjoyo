# AI Output Review

## Skill
Project Inception and Stakeholder Discovery

## AI Output File
outputs/raw/inception-ai-output.md

## Problems Found
1. **Pencampuran Masalah dan Solusi**: AI langsung mengusulkan solusi sistem ("pembuatan Student Task Management System dengan antarmuka yang sangat cepat dan modern") di dalam deskripsi *Business Problem*. Ini melanggar aturan untuk memisahkan masalah dari solusi.
2. **Kriteria Tidak Terukur (Ambigu)**: AI menggunakan kalimat "dapat diakses dengan sangat cepat" pada bagian *Project Goals*. Istilah "sangat cepat" bersifat subjektif dan tidak dapat diuji (*untestable*).
3. **Halusinasi Fitur (Scope Creep)**: AI menambahkan "Fitur Chatting/Forum Diskusi antar dosen dan mahasiswa" ke dalam *In-Scope*. Fitur ini tidak diminta oleh dosen, mahasiswa, maupun administrator dalam berkas `CASE.md` maupun `inputs/stakeholder-notes.md`.

## Student Corrections
1. **Perbaikan Masalah Bisnis**: Memformulasikan ulang deskripsi *Business Problem* agar murni menjelaskan masalah operasional pengumpulan tugas tanpa mendikte solusi sistem.
2. **Kuanifikasi Kriteria**: Mengubah tujuan "sangat cepat" menjadi metrik terukur, yaitu: "Mencapai waktu respons sistem (page load time) maksimal 3 detik pada kondisi jaringan standar."
3. **Koreksi Scope**: Menghapus "Fitur Chatting/Forum Diskusi" dari *In-Scope* dan memindahkannya ke *Out-of-Scope* untuk mencegah *scope creep* (pelebaran ruang lingkup yang tidak berdasar).

## Final Output
[01-inception.md](../../outputs/reviewed/01-inception.md)

---

## Skill
Requirements Elicitation

## AI Output File
outputs/raw/elicitation-ai-output.md

## Problems Found
1. **Teknik Elicitation Tidak Relevan**: AI merekomendasikan "Alumni Survey" untuk mengumpulkan kebutuhan sistem tugas kuliah aktif, yang tidak relevan dengan kebutuhan pengguna sistem saat ini.
2. **Spesifikasi Database Khusus**: AI memaksakan penggunaan "Oracle Database 19c" sebagai kebutuhan implisit dosen dan batasan sistem, padahal tidak pernah disebutkan dalam berkas masukan.
3. **Fitur Di Luar Scope & Anggaran**: AI menyarankan pengiriman "SMS berbayar" sebagai kebutuhan implisit mahasiswa. Hal ini di luar cakupan kebutuhan dan menambah biaya operasional.

## Student Corrections
1. **Eliminasi Teknik Tidak Relevan**: Menghapus "Alumni Survey" dan memfokuskan dokumentasi pada teknik *Interview* (wawancara) dan *Document Analysis* yang terbukti digunakan.
2. **Generalisasi Basis Data**: Menghapus batasan "Oracle Database 19c" dan memfokuskannya pada integritas data serta otorisasi akses data nilai secara umum.
3. **Penyesuaian Fitur Notifikasi**: Mengganti notifikasi SMS berbayar menjadi notifikasi email otomatis dan notifikasi dalam aplikasi (*in-app notification*) sesuai catatan wawancara mahasiswa.

## Final Output
[02-elicitation.md](../../outputs/reviewed/02-elicitation.md)

---

## Skill
Requirements Elaboration and Specification

## AI Output File
outputs/raw/requirements-ai-output.md

## Problems Found
1. **Requirement Fungsional Duplikat**: FR-06 ("Dosen dapat memberikan nilai angka...") dan FR-08 ("Dosen dapat menginput nilai tugas...") memiliki substansi yang sama, menyebabkan redundancy.
2. **Leakage Scope Out-of-Scope**: FR-09 menyertakan fitur "notifikasi chat instan", padahal chatting sudah diklasifikasikan sebagai *out-of-scope* pada tahap inception.
3. **NFR Tidak Terukur (Ambigu)**: NFR-01 s.d NFR-04 menggunakan kata subjektif ("sangat cepat", "sangat aman", "user-friendly", "selalu online tanpa downtime") yang tidak dapat diuji.
4. **Acceptance Criteria Tidak Memiliki Failure/Alternative Scenario**: US-01 (Upload), US-05 (Grading), dan US-06 (Unsubmit) hanya mendefinisikan skenario sukses (*happy path*) tanpa menangani kasus batas (seperti file > 20MB, nilai di luar 0-100, atau unsubmit setelah dinilai).
5. **Kurang dari Minimum Kriteria**: US-04 hanya memiliki 1 Acceptance Criteria (AC), sedangkan ketentuannya minimal 2 AC per User Story.

## Student Corrections
1. **Konsolidasi FR & Penghapusan Out-of-Scope**: Menggabungkan FR-06 dan FR-08 menjadi satu requirement fungsional terintegrasi, menghapus FR-09 (chat), dan menambahkan FR baru (FR-08: penonaktifan akun secara logis) agar tetap berjumlah minimal 8 FR.
2. **Kuantifikasi Metrik NFR**: Mengubah seluruh NFR menggunakan metrik terukur (misalnya: enkripsi AES-256 untuk security, waktu respons < 3 detik untuk performance, ketersediaan 99.9% untuk reliability, dan SUS score > 75 untuk usability).
3. **Melengkapi Skenario Alternatif/Gagal pada AC**: Menambahkan skenario gagal untuk setiap User Story (seperti penolakan ukuran file > 20MB, penolakan input nilai negatif/di atas 100, dan penolakan unsubmit setelah dinilai).
4. **Menambah AC Baru**: Menambahkan kriteria penerimaan kedua pada US-04 untuk notifikasi email dan notifikasi *in-app*.

## Final Output
- [03-requirements.md](../../outputs/reviewed/03-requirements.md)
- [04-user-stories.md](../../outputs/reviewed/04-user-stories.md)
