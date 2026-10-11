# 🤖 TobiQuest — Platform Edukasi Interaktif Siswa SD

> **Karya untuk M-ONE Telkomsel Coding Competition 2026**  
> **Kategori:** Kategori Umum (Individu)  
> **Tema Utama:** *Innovating Education Through Technology*  
> **Subtema:** *WEB EDUCATION FOR KIDS (untuk anak SD Kelas 1–6)*  
> **Tautan Live Demo:** [https://tobiquest.vercel.app](https://tobiquest.vercel.app)  

---

[![Next.js 16](https://img.shields.io/badge/Next.js-16.3.8-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4-38bdf8?style=for-the-badge&logo=tailwindcss)](https://tailwindcss.com/)
[![Telkomsel Lite Mode](https://img.shields.io/badge/Telkomsel_Lite_Mode-%3C500_KB-red?style=for-the-badge)](https://tobiquest.vercel.app)
[![Vercel Deployment](https://img.shields.io/badge/Deploy-Vercel_Edge-000000?style=for-the-badge&logo=vercel)](https://tobiquest.vercel.app)

---

## 🌟 1. Tentang TobiQuest

**TobiQuest** adalah platform web pembelajaran interaktif masa depan yang dirancang khusus untuk siswa Sekolah Dasar (SD Kelas 1–6) di seluruh Indonesia. Mengusung semangat inovasi Telkomsel untuk pemerataan pendidikan digital berkualitas (*Inclusive & Accessible EdTech*), TobiQuest memadukan kurikulum pendidikan dasar nasional dengan teknologi web interaktif mutakhir.

Aplikasi ini menghadirkan maskot robot sahabat belajar bernama **Tobi**, yang membimbing siswa melalui dialog ramah bersuara asli bahasa Indonesia (Web Speech API) dan pendekatan pedagogi **AI Socratic Mentor (Zero-Scold)**—tidak pernah memarahi anak saat salah, melainkan memantik proses berpikir logis hingga anak berhasil.

---

## 🚀 2. Inovasi Unggulan & Fitur Utama

### 🔴 1. Telkomsel Lite Mode (< 500 KB) — Solusi Pendidikan Daerah 3T
* Dirancang khusus untuk siswa di wilayah **3T (Terdepan, Terluar, Tertinggal)** yang memiliki keterbatasan sinyal atau kuota internet.
* Mengompresi aset, menonaktifkan animasi berat, dan menjalankan efek audio murni melalui sintesis osilator peramban (Web Audio API) tanpa mengunduh file MP3/video berat dari server.

### 🤖 2. Maskot Tobi (Voice AI Web Speech API & Socratic Zero-Scold)
* **Bantuan Suara Inklusif:** Membacakan teks narasi materi bagi siswa kelas awal (SD Kelas 1–2) yang belum lancar membaca.
* **Teknologi Anti-Delay:** Menggunakan arsitektur *First-Touch Audio Unlock* dan *Voice Pre-loading* sehingga suara Tobi langsung merespons instan di browser ponsel Android dan iOS tanpa delay.
* **Bimbingan Positif:** Setiap kesalahan siswa dijawab dengan apresiasi dan petunjuk sokratik yang membangun rasa percaya diri.

### 🧪 3. Laboratorium Sains Interaktif (5 Stasiun Eksperimen)
1. **Campur Warna Cairan:** Pipet tetes warna primer (merah, kuning, biru) dengan visual tabung reaksi dan reaksi busa kimiawi.
2. **Siklus Air Bumi:** Eksperimen 4 tahapan hidrologi (evaporasi, kondensasi, presipitasi, dan infiltrasi).
3. **Rantai Makanan & Ekosistem:** Simulasi interaktif jaring makanan sawah dan laut serta krisis kepunahan spesies.
4. **Laboratorium Sirkuit Listrik:** Puzzle perakitan baterai, saklar, dan lampu, serta demonstrasi komparasi rangkaian Seri vs Paralel dengan animasi aliran elektron.
5. **Magnet Hunter:** Identifikasi sifat feromagnetik benda-benda di sekitar kelas.

### 🍎 4. Petualangan Hitung Ceria & Logika Aljabar
1. **Kalkulasi Buah:** Latihan berhitung representatif tanpa sontekan langsung, melatih kemampuan penalaran deduktif.
2. **Timbangan Neraca Misteri:** Neraca dua lengan dengan beban kuningan dan kristal untuk memahami konsep kesetaraan aljabar.
3. **Detektif Aljabar Buah:** Generator teka-teki logika 2 variabel bertingkat (*eliminasi & substitusi cilik*) dengan 4 pola misi acak: tebak nilai tunggal, kelipatan, selisih, dan kombinasi baru.

### 🪐 5. Tata Surya Kosmik 3D Interaktif
* Navigasi orbit 9 objek langit (Matahari hingga Neptunus) dengan fakta sains kosmik (suhu, revolusi, satelit) yang dinarasikan suara Tobi.

### 🇮🇩 6. Literasi Budaya Nusantara & Panggung Lagu Nasional
* **Literasi Nusantara:** Koleksi cerita rakyat dari 34 Provinsi di Indonesia lengkap dengan filter pulau dan audio narasi cerita.
* **Lagu Nasional:** Panggung video edukasi lagu wajib nasional dengan pemutar resmi YouTube embed, timestamp jumper akurat tiap lagu, lirik resmi, makna lagu, dan tuts pianika not angka asli.

### 📝 7. Asesmen Diagnostik & Ujian Mandiri (10 Mapel + 6 Agama)
* Bank soal 300+ soal pilihan ganda kurikulum merdeka SD.
* Mendukung 10 Mata Pelajaran lengkap SD (Bahasa Indonesia, Matematika, IPAS, Pancasila, Seni Budaya, PJOK, Bahasa Inggris, dll.).
* Pilihan 6 Agama Resmi di Indonesia (Islam, Kristen Protestan, Katolik, Hindu, Buddha, Khonghucu).
* Tampilan modern *app-launcher* tombol bulat grid (3 kolom di HP) yang pas 1 layar tanpa perlu *scroll*.

### 🏆 8. Piagam Penghargaan Prestasi Siswa (Cetak PDF A4 Resmi)
* Sistem penghargaan gamifikasi berbasis bintang prestasi yang dikumpulkan siswa.
* Dapat langsung dicetak menjadi **file PDF resmi berukuran tepat 1 lembar A4 Landscape** dengan desain berornamen emas, medali Telkomsel, dan tanda tangan resmi komite juri.

---

## 🛠️ 3. Tech Stack & Arsitektur

* **Framework:** Next.js 16.3.8 (App Router & Turbopack)
* **Language:** TypeScript 5 (Strict Mode)
* **Styling:** Tailwind CSS 4, Responsive Breakpoints (Mobile 9:16 & Desktop 16:9), Chunky Kids UI
* **Audio Engine:** Native Web Audio API + Web Speech API (Indonesian TTS `id-ID`)
* **State Management:** LocalStorage-First (Zero Database Dependency, Zero Crash, 100% Child Privacy)
* **Deployment:** Vercel Edge Global Network

```
+-------------------------------------------------------------------------+
|                              TobiQuest UI                               |
|   (Next.js App Router, Tailwind CSS 4, Lucide Icons, Chunky Kids UI)    |
+-------------------------------------------------------------------------+
                                    |
     +------------------------------+-------------------------------+
     |                              |                               |
     v                              v                               v
+------------------+     +--------------------+          +------------------+
|   Audio Engine   |     | Socratic AI Mentor |          |  Storage & State |
|  Web Audio + TTS |     |  Feedback Logic    |          | LocalStorage     |
| (Bahasa ID Voice)|     | (Zero-Scold Prompts|          | (Zero-Crash sync)|
+------------------+     +--------------------+          +------------------+
     |                              |                               |
     +------------------------------+-------------------------------+
                                    |
                                    v
+-------------------------------------------------------------------------+
|                     18 Static Routes (Prerendered)                      |
|       (Lab Sains, Hitung Ceria, Tata Surya, Literasi, Asesmen, Piagam)  |
+-------------------------------------------------------------------------+
```

---

## 📂 4. Indeks Berkas Resmi Kompetisi

Sesuai ketentuan **Guidebook M-ONE Telkomsel Coding Competition 2026 (Halaman 5, 8, & 12)**, seluruh dokumen kelayakan dan proses vibe coding telah disusun secara transparan di dalam direktori `docs/`:

1. 📄 **[Dokumen Acuan AI Agent (AI_AGENT_DOCS.md)](./docs/AI_AGENT_DOCS.md):**  
   *Panduan spesifikasi teknis, batasan arsitektur, dan aturan kerja pengembangan untuk AI Agent.*
2. 📄 **[Jurnal Prompt Terkurasi (JURNAL_PROMPT.md)](./docs/JURNAL_PROMPT.md):**  
   *Dokumentasi 5 Prompt Terkurasi Wajib (Ide/PRD, Debugging, Audit & Optimasi, Finishing, dan Bebas/Inovasi) untuk penilaian kategori Proses Vibe Coding (Bobot 25 Poin).*
3. 📄 **[Log Prompt Mentah Awal–Akhir (PROMPT_LOG_RAW.md)](./docs/PROMPT_LOG_RAW.md):**  
   *Rekam jejak kronologis proses pengembangan mandiri sejak garis start 5 Oktober 2026 sebagai bukti otentisitas karya.*
4. 📄 **[Product Requirements Document (PRD.md)](./docs/PRD.md):**  
   *Rancangan awal persona siswa SD dan spesifikasi fitur modul Kurikulum Merdeka.*

---

## 💻 5. Cara Menjalankan Proyek Secara Lokal

### Prasyarat
* Node.js versi 18.18.0 atau lebih baru
* npm atau yarn atau pnpm

### Langkah Instalasi
1. Kloning repository ini:
   ```bash
   git clone https://github.com/sufyantsaury753-beep/tobiquest.git
   cd tobiquest
   ```
2. Pasang seluruh dependensi:
   ```bash
   npm install
   ```
3. Jalankan server pengembangan lokal:
   ```bash
   npm run dev
   ```
   Buka peramban Anda di [http://localhost:3000](http://localhost:3000).

4. Uji build produksi:
   ```bash
   npm run build
   ```

---

## 🔒 6. Komitmen Keamanan & Privasi Anak

TobiQuest mematuhi prinsip privasi data anak (*Child Online Privacy Protection*):
* **Zero PII Leakage:** Tidak meminta data pribadi sensitif anak seperti NIK, nomor telepon, atau alamat rumah.
* **Tanpa Iklan & Pelacak:** Bebas dari pelacak pihak ketiga (*third-party advertising cookies*).
* **LocalStorage-First:** Semua progres bintang dan piagam disimpan secara lokal di peramban pengguna.

---

## 👥 Tim Pengembang

* **Peserta:** Sufyan (Kategori Umum)
* **Kompetisi:** M-ONE Telkomsel Coding Competition 2026
* **Penyelenggara:** M-One Solution — Business Center SMK Muhammadiyah 1 Sukoharjo
* **Tahun:** 2026