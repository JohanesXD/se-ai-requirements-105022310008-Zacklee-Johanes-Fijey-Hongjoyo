# AI-Assisted Requirements Engineering Assignment

## Student Information
- Name: Zacklee Johanes Fijey Hongjoyo
- Student ID: 105022310008
- Class: Informatika Semester 6
- Course: Software Engineering
- Lecturer: Andrew Tanny Liem

## Project
Student Task Management System

## Assignment Objective
This repository demonstrates reusable AI skills for conducting requirements engineering activities.

## Skills
1. [Inception Skill](skills/01-inception/SKILL.md)
2. [Elicitation Skill](skills/02-elicitation/SKILL.md)
3. [Specification Skill](skills/03-specification/SKILL.md)
4. [Prioritization Skill](skills/04-prioritization/SKILL.md)
5. [Validation and Change Skill](skills/05-validation-change/SKILL.md)

## Final Outputs
Semua berkas keluaran akhir (*reviewed outputs*) dapat diakses di tautan berikut:
- [01-Inception](outputs/reviewed/01-inception.md) - Project Inception and Stakeholder Discovery
- [02-Elicitation](outputs/reviewed/02-elicitation.md) - Requirements Elicitation Findings
- [03-Requirements](outputs/reviewed/03-requirements.md) - Software Requirements Specification (FR, NFR, BR)
- [04-User Stories](outputs/reviewed/04-user-stories.md) - User Stories & Acceptance Criteria
- [05-Prioritization](outputs/reviewed/05-prioritization.md) - MoSCoW Prioritization & Negotiation
- [06-Use Case](outputs/reviewed/06-use-case.md) - Use Case Specifications
- [07-Validation](outputs/reviewed/07-validation.md) - Requirements Validation Audit
- [08-Change Request](outputs/reviewed/08-change-request.md) - Change Request Impact Analysis (CR-01)
- [Requirements Traceability Matrix](outputs/reviewed/requirements-traceability.md) - Traceability Matrix Table

## AI Usage
- **AI Tool Used**: Antigravity IDE
- **Model**: Gemini 3.5 Flash
- **Date**: 2026-06-22
- **Skills Tested**:
  - `Skill 1: Project Inception and Stakeholder Discovery` (diuji pada kasus *Library Reservation System*).
  - `Skill 3: Requirements Elaboration and Specification` (diuji pada kasus *Library Reservation System*).
- **Major Corrections Made**:
  1. **Inception**: Menghapus fitur chat/diskusi (*scope creep*) dan mengkuantifikasi kriteria "sangat cepat" menjadi metrik respons 3 detik.
  2. **Elicitation**: Mengeliminasi teknik *Alumni Survey* yang tidak relevan, membatalkan ketergantungan pada DBMS Oracle 19c spesifik, dan mengubah notifikasi SMS berbayar menjadi email/in-app.
  3. **Specification**: Menggabungkan fungsionalitas duplikat, menghapus requirement chat instan, melengkapi kriteria kegagalan (*failure scenarios*) pada berkas tugas (> 20MB) dan penilaian (di luar rentang 0-100).
  4. **Prioritization**: Menyelesaikan logika dependensi antara pengunggahan berkas (FR-04) dengan penilaian (FR-06), serta menambahkan FR-08 & FR-09 yang terlewat oleh AI.
  5. **Validation & Change**: Mengoreksi keputusan fitur plagiarisme Turnitin dari *Approved* menjadi *Deferred* demi menjaga jadwal MVP dan anggaran proyek rilis pertama.

## Reflection
AI terbukti sangat efisien untuk menyusun draf awal yang terstruktur dan menerjemahkan keluhan stakeholder menjadi tulisan kebutuhan formal. Namun, AI sering kali mengalami halusinasi fitur di luar ruang lingkup (*scope creep*), bias terhadap skenario sukses (*happy path*), dan memunculkan kriteria yang subjektif/ambigu. Oleh karena itu, tinjauan analis manusia (*human review*) tetap mutlak diperlukan untuk menyaring halusinasi tersebut, membatasi fungsionalitas berdasarkan kendala dunia nyata, dan bertanggung jawab secara profesional atas *requirements baseline* akhir.

Catatan refleksi lengkap dapat diakses di: [Reflection Report](evaluation/reflection.md).
