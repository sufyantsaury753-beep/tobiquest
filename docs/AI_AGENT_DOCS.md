# DOKUMEN ACUAN PENGEMBANGAN AI AGENT (SYSTEM SPECIFICATION)
## Proyek: TobiQuest — Platform Web Edukasi Interaktif Siswa SD
**Kompetisi:** M-ONE Telkomsel Coding Competition 2026  
**Tema Utama:** *Innovating Education Through Technology*  
**Subtema:** *WEB EDUCATION FOR KIDS · SD (Sekolah Dasar Kelas 1–6)*  
**Dokumen:** Panduan & Aturan Kerja AI Agent (Engineering Reference)  
**Versi:** 1.0.0 — Final Production Release  
**Garis Start Pengembangan:** 5 Oktober 2026, 09.30 WIB  

---

## 1. TUJUAN PRODUK & FILOSOFI PENGEMBANGAN

### 1.1 Visi Produk
**TobiQuest** adalah platform web pembelajaran interaktif masa depan yang dirancang khusus untuk siswa Sekolah Dasar (SD Kelas 1–6) di seluruh Indonesia. Mengusung semangat inovasi Telkomsel untuk pemerataan pendidikan digital berkualitas (*Inclusive & Accessible EdTech*), TobiQuest berfokus pada:
1. **Pengalaman Belajar Menyenangkan (Joyful & Kinesthetic Learning):** Mengubah materi sains, matematika, dan literasi yang kaku menjadi laboratorium eksperimen dan simulasi manipulatif visual.
2. **Aksesibilitas & Inklusivitas Suara (Web Speech API TTS):** Membantu siswa kelas awal (SD Kelas 1–2) yang belum lancar membaca melalui pendampingan narator suara robot ceria bernama **Tobi**.
3. **AI Socratic Kids Mentor (Zero-Scold Culture):** Menghilangkan rasa takut salah (*fear of failure*) dengan respon sokratik pemantik daya nalar ketika siswa menjawab keliru.
4. **Telkomsel Lite Mode (< 500 KB):** Arsitektur hemat kuota yang dapat berjalan mulus di jaringan minim sinyal (daerah 3T: Terdepan, Terluar, Tertinggal).
5. **Zero-Login & Privasi Anak Penuh:** Arsitektur *LocalStorage-First* tanpa registrasi akun, tanpa pelacak, tanpa iklan pihak ketiga, dan sepenuhnya aman bagi privasi anak.

---

## 2. TECH STACK & ARSITEKTUR SISTEM

AI Agent wajib mematuhi batasan arsitektur teknologi berikut:

| Lapisan Teknologi | Pilihan Teknologi | Alasan Pemilihan & Nilai Guna |
| :--- | :--- | :--- |
| **Framework Utama** | **Next.js 16.3.8 (App Router & Turbopack)** | Performa rendering kilat, rute statis (*Static Site Generation* 18 rute) yang instan dimuat. |
| **Bahasa Pemrograman** | **TypeScript 5 (Strict Mode)** | Menjamin keamanan tipe data (*type-safety*) dan zero runtime errors pada data evaluasi dan skor. |
| **Styling & Desain** | **Tailwind CSS 4 + Chunky Kids UI** | Desain ramah anak dengan sudut membulat lebar (*rounded-3xl*), bayangan timbul (*chunky buttons*), dan palet warna Kurikulum Merdeka. |
| **Iconography** | **Lucide React** | Ikon vektor ringan, tajam, dan universal tanpa beban aset gambar eksternal. |
| **Audio Engine** | **Web Audio API + Web Speech API (TTS)** | Sintesis audio murni berbasis osilator peramban dan Text-to-Speech lokal `id-ID` tanpa file MP3 berat. |
| **State & Penyimpanan** | **LocalStorage-First Engine** | Penyimpanan lokal tanpa ketergantungan server database, menjaga privasi data anak 100%. |
| **Media Cetak** | **CSS Paged Media (`@media print`)** | Mesin cetak Piagam Prestasi Siswa otomatis berukuran tepat 1 lembar A4 Landscape standar resmi. |
| **Deployment** | **Vercel Edge Platform** | Hosting global berkecepatan tinggi dengan integrasi Git CI/CD otomatis dan SSL HTTPS bawaan. |

---

## 3. MODUL FITUR UTAMA & SPESIFIKASI KERJA AI AGENT

AI Agent mengimplementasikan dan mengelola 6 modul inti pembelajaran:

### 3.1 Maskot Interaktif "Tobi si Robot"
* **Komponen:** `src/components/MascotTobi.tsx`, `src/lib/sound.ts`
* **Spesifikasi:**
  - Sintesis suara Bahasa Indonesia (`id-ID`) dengan nada ramah anak (pitch: 1.15, rate: 0.95).
  - Mekanisme *First-Touch Audio Unlock* untuk mencegah *queue stall* 15 detik di browser mobile Android/iOS.
  - Dialog interaktif pemantik rasa ingin tahu dan tombol "Beri Semangat".

### 3.2 Stasiun Lab Sains Interaktif (5 Laboratorium Eksperimen)
* **Rute:** `/lab-sains/*`
* **Stasiun:**
  1. **Campur Warna Cairan (`/warna`):** Simulasi pipet tetes warna primer (merah, kuning, biru) untuk menemukan warna sekunder dengan visual tabung reaksi dinamis.
  2. **Siklus Air Bumi (`/siklus-air`):** Tahapan interaktif evaporasi, kondensasi, presipitasi, dan infiltrasi.
  3. **Rantai Makanan & Ekosistem (`/rantai-makanan`):** Simulasi jaring makanan sawit dan laut serta krisis kepunahan produsen/konsumen.
  4. **Laboratorium Sirkuit Listrik (`/listrik`):** Perakitan puzzle baterai, saklar, dan lampu, serta demonstrasi komparasi rangkaian Seri vs Paralel.
  5. **Magnet Hunter (`/magnet`):** Identifikasi sifat feromagnetik benda sehari-hari (logam vs non-logam).

### 3.3 Modul Hitung Ceria & Logika Aljabar
* **Rute:** `/hitung-ceria/*`
* **Stasiun:**
  1. **Kalkulasi Buah (`/kalkulasi`):** Penjumlahan dan pengurangan berbasis representasi buah tanpa sontekan langsung, menuntut penalaran deduktif.
  2. **Timbangan Neraca Misteri (`/neraca`):** Simulasi neraca dua lengan berbeban kuningan dan kristal misteri untuk memahami konsep kesetaraan aljabar.
  3. **Detektif Aljabar Buah (`/detektif`):** Generator soal teka-teki logika 2 variabel bertingkat (*eliminasi dan substitusi cilik*) dengan 4 pola soal acak: tebak buah tunggal, kelipatan, selisih, dan kombinasi baru.

### 3.4 Tata Surya Kosmik 3D Interaktif
* **Rute:** `/tata-surya`
* **Spesifikasi:**
  - Navigasi orbit 9 objek langit (Matahari, Merkurius, Venus, Bumi, Mars, Jupiter, Saturnus, Uranus, Neptunus).
  - Lembar fakta sains kosmik (suhu permukaan, waktu revolusi, jumlah satelit) dinarasikan suara Tobi.
  - Docking selector ramah jempol anak di bagian bawah layar.

### 3.5 Literasi Budaya Nusantara & Panggung Lagu Nasional
* **Rute:** `/literasi-nusantara`, `/lagu-nasional`
* **Spesifikasi:**
  - Literasi cerita rakyat 34 provinsi Indonesia lengkap dengan audio pembaca cerita.
  - Panggung Lagu Wajib Nasional dengan YouTube Embed resmi, timestamp jumper akurat tiap lagu, lirik resmi, makna filosofis, dan companion tuts pianika not angka asli.

### 3.6 Asesmen Diagnostik & Ujian Mandiri (10 Mapel + 6 Agama)
* **Rute:** `/evaluasi`
* **Spesifikasi:**
  - Bank soal 300+ soal pilihan ganda kurikulum merdeka SD.
  - Mendukung 10 Mata Pelajaran lengkap SD (Bahasa Indonesia, Matematika, IPAS, Pancasila, Seni Budaya, PJOK, Bahasa Inggris, dll.).
  - Pilihan 6 Agama Resmi di Indonesia (Islam, Kristen Protestan, Katolik, Hindu, Buddha, Khonghucu).
  - Antarmuka *app-launcher* berupa tombol bulat grid (3 kolom di HP) yang kompak dan nyaman disentuh.

### 3.7 Piagam Penghargaan Prestasi Siswa (Cetak PDF A4)
* **Komponen:** `src/components/CertificateModal.tsx`, `src/app/globals.css`
* **Spesifikasi:**
  - Desain sertifikat resmi Telkomsel & TobiQuest dengan ornamen sudut emas, nama siswa, bintang prestasi yang dikumpulkan, dan stempel komite juri.
  - Skala cetak 100% presisi untuk 1 lembar A4 Landscape (297mm x 210mm) tanpa melar dan tanpa halaman sisa.

---

## 4. ATURAN KERJA & STANDAR KUALITAS AI AGENT

AI Agent dalam mengembangkan dan merawat kode wajib mematuhi SOP berikut:

1. **Aturan Responsivitas Mobile-First:**
   - Semua antarmuka wajib diuji dan rapi pada resolusi smartphone (360px–412px lebar) serta laptop/desktop (1024px–1920px).
   - Hindari layout rata kiri compang-camping; gunakan pembagian grid simetris (misal `grid-cols-2` atau `grid-cols-3` pada mobile).
2. **Aturan Kebersihan Kode & Zero-Error:**
   - Perintah `npm run build` wajib menghasilkan exit code 0 tanpa kompromi.
   - Tidak boleh ada deklarasi tipe `any` tanpa alasan jelas.
3. **Aturan Integritas Orisinalitas Karya:**
   - Seluruh riwayat kode, berkas, dan struktur direktori dibuat secara mandiri dari nol sejak lomba dibuka (5 Oktober 2026, 09.30 WIB).
   - Pesan commit di GitHub disusun secara bertahap dan mencerminkan progres nyata fitur.
4. **Aturan Privasi & Kenyamanan Anak:**
   - Dilarang menambahkan analitik pelacak, iklan pihak ketiga, atau form pengumpulan data sensitif.
   - Gunakan pendekatan *Zero-Scold*: jika siswa salah menjawab, berikan respon yang menyemangati dan mendidik.
