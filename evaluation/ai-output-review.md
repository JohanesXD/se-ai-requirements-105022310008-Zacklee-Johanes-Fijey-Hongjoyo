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

