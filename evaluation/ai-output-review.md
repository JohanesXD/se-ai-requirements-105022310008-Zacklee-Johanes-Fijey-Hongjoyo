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
2. **Kuantifikasi Kriteria**: Mengubah tujuan "sangat cepat" menjadi metrik terukur, yaitu: "Mencapai waktu respons sistem (page load time) maksimal 3 detik pada kondisi jaringan standar."
3. **Koreksi Scope**: Menghapus "Fitur Chatting/Forum Diskusi" dari *In-Scope* dan memindahkannya ke *Out-of-Scope* untuk mencegah *scope creep* (pelebaran ruang lingkup yang tidak berdasar).

## Final Output
[01-inception.md](../../outputs/reviewed/01-inception.md)
