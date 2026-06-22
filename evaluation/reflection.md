# Reflection: AI-Assisted Requirements Engineering

Dokumen ini berisi refleksi mengenai peran, kelebihan, keterbatasan, dan pelajaran yang didapat dari penggunaan kecerdasan buatan (AI) dalam mendukung aktivitas Requirements Engineering (RE) pada proyek **Student Task Management System**.

---

## 1. Bagian apa yang paling baik dikerjakan oleh AI dalam proses Requirements Engineering?
AI sangat unggul dalam melakukan **generasi draf awal secara cepat dan menyusun struktur dokumen** secara rapi sesuai format standar. Kemampuannya mencakup:
*   Menerjemahkan ide-ide abstrak stakeholder menjadi format terstruktur seperti *User Stories* (`As a... I want... so that...`) dan *Acceptance Criteria* secara konsisten.
*   Mengidentifikasi potensi kebutuhan implisit (seperti keamanan data, enkripsi, dan integritas file) yang sering terlewat oleh analis manusia pemula.
*   Membuat pemetaan ketergantungan (*dependency*) antar-requirements dengan logika sebab-akibat yang runtut.

---

## 2. Kesalahan atau asumsi apa yang paling sering dibuat oleh AI?
Selama pengerjaan tugas, AI menunjukkan beberapa kesalahan berulang (*patterns of error*) sebagai berikut:
*   **Scope Creep (Halusinasi Fitur)**: AI cenderung menambahkan fitur-fitur baru yang canggih (seperti ruang obrolan/chatting atau notifikasi SMS berbayar) padahal fitur tersebut sama sekali tidak diminta oleh stakeholder di berkas masukan.
*   **Kriteria Kualitas Ambigu**: AI sering menggunakan kata sifat subjektif yang tidak dapat diuji (*untestable*) pada kebutuhan non-fungsional, seperti "sangat cepat", "sangat aman", atau "user-friendly".
*   **Redundansi / Duplikasi**: Mendefinisikan kebutuhan fungsional yang sama berulang kali dengan susunan kalimat yang sedikit berbeda (seperti pada FR-06 dan FR-08 di draf awal spesifikasi).
*   **Skenario Sukses Saja (Happy Path Bias)**: Saat membuat kriteria penerimaan (*Acceptance Criteria*), AI cenderung mengabaikan skenario gagal atau batas (*failure/boundary cases*), seperti kasus ukuran file melebihi limit atau input nilai di luar rentang.

---

## 3. Bagaimana perubahan pada SKILL.md memperbaiki kualitas output?
Modifikasi terstruktur pada `SKILL.md` (seperti menambahkan aturan `Rules` dan kriteria `Quality Checks` yang ketat) secara signifikan membatasi kelemahan AI:
*   Aturan *"Jangan membuat fakta yang tidak diberikan"* menekan tingkat halusinasi AI secara drastis.
*   Penambahan kriteria *"Wajib menggunakan metrik angka terukur pada NFR"* memaksa AI mencari standar industri (seperti batasan 3 detik untuk loading web atau standar enkripsi AES-256) daripada memakai kata sifat subjektif.
*   Instruksi *"Wajib menyertakan minimal 1 skenario kegagalan pada AC"* memaksa AI berpikir tentang *error handling* dan batasan sistem.

---

## 4. Mengapa human review tetap diperlukan walaupun AI telah menggunakan workflow dan quality checks?
Meskipun AI dibekali dengan workflow dan pemeriksaan kualitas mandiri, tinjauan manusia (*human review*) tetap mutlak diperlukan karena:
*   **Tanggung Jawab Baseline**: AI tidak memiliki pemahaman tentang tanggung jawab moral, hukum, atau komitmen proyek. Manusia harus menandatangani *baseline requirements* karena manusialah yang akan membangun dan menanggung risiko kegagalan sistem tersebut.
*   **Verifikasi Konteks Nyata**: AI tidak tahu apakah batas ukuran file 20 MB masuk akal untuk infrastruktur server kampus saat ini. Hanya analis manusia yang memahami kendala dunia nyata (seperti anggaran server dan kebijakan internal kampus).
*   **Penyaringan Halusinasi**: AI tidak selalu menyadari kapan ia sedang berhalusinasi. Pengawas manusia bertindak sebagai gerbang terakhir untuk menyaring kebutuhan-kebutuhan liar yang tidak realistis.

---

## 5. Bagaimana traceability membantu menjaga konsistensi antarartefak requirements?
Matriks Ketersusuran (*Traceability Matrix*) di `requirements-traceability.md` sangat penting untuk menjaga integritas proyek RE karena:
*   **Mencegah Yatim Piatu (*Orphan Requirements*)**: Menjamin setiap kebutuhan fungsional (`FR`) benar-benar lahir dari suara stakeholder (`EL-Source`) dan bukan buatan sepihak dari tim pengembang.
*   **Memudahkan Analisis Dampak (*Impact Analysis*)**: Jika ada permintaan perubahan (*Change Request*) pada suatu fitur, analis dapat langsung menelusuri requirement mana saja yang terdampak, user story mana yang harus diubah, dan kriteria pengujian apa yang harus ditulis ulang.
*   **Menjamin Keterujian (*Testability*)**: Menghubungkan setiap *User Story* dengan *Acceptance Criteria* untuk memastikan semua fitur yang dijanjikan memiliki skenario uji yang siap dijalankan saat fase QA/Testing.
