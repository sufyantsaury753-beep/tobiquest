# JURNAL PROMPT TERKURASI (VIBE CODING JOURNAL)
## Proyek: TobiQuest — Platform Web Edukasi Interaktif Siswa SD
**Kompetisi:** M-ONE Telkomsel Coding Competition 2026  
**Kategori:** Kategori Umum (Individu)  
**Tema:** *Innovating Education Through Technology*  
**Subtema:** *WEB EDUCATION FOR KIDS (untuk anak SD)*  
**Bobot Penilaian:** 25 Poin (Kategori *Proses Vibe Coding*)  
**Format Dokumen:** 5 Prompt Terkurasi Wajib (Ide/PRD, Debugging, Audit & Optimasi, Finishing, Bebas)  

---

## PENGANTAR PROSES VIBE CODING

Pengembangan platform edukasi **TobiQuest** dilakukan secara mandiri dari nol sejak garis start kompetisi dibuka pada **5 Oktober 2026 pukul 09.30 WIB**. Dalam proses ini, Artificial Intelligence (AI Agent) diberdayakan secara intensif dan iteratif sebagai mitra pemrograman berpasangan (*AI Pair Programming & Vibe Coding*).

Dokumen ini mendokumentasikan **5 Prompt Terkurasi Terbaik** yang mewakili setiap fase penting siklus pengembangan: dari konsepsi arsitektur, pemecahan masalah kritis (*debugging*), optimasi performa ramah kuota (*Telkomsel Lite Mode*), perapian antarmuka mobile (*finishing*), hingga implementasi inovasi suara sokratik ramah anak (*innovation*).

---

## 1. PROMPT 1: FASE IDE & ARSITEKTUR PRODUK (PRD)

* **Kategori Wajib:** Ide / PRD
* **Fokus:** Perancangan Visi Produk, Analisis Kebutuhan Siswa SD (Kelas 1–6), Arsitektur *LocalStorage-First*, dan Integrasi *Telkomsel Lite Mode*.
* **Waktu Eksekusi:** 5 Oktober 2026

```markdown
Bertindaklah sebagai Senior EdTech Product Manager & Lead Architect. 

Saya akan mengikuti "M-ONE Telkomsel Coding Competition 2026" kategori Web Education for Kids (Siswa SD). 
Bantu saya merancang dokumen spesifikasi produk (PRD) dan arsitektur awal untuk aplikasi web interaktif bernama "TobiQuest".

### Persyaratan Utama:
1. Relevansi Tema & Sponsor (Telkomsel):
   - Rancang fitur khusus "Telkomsel Lite Mode (< 500 KB)" yang ramah kuota data untuk sekolah dan anak-anak di daerah 3T (Terdepan, Terluar, Tertinggal) dengan sinyal minim.
2. Inklusivitas Siswa SD (Kelas 1–6):
   - Hadirkan maskot robot ramah bernama "Tobi" yang dilengkapi Text-to-Speech (Web Speech API Bahasa Indonesia) untuk membantu anak yang belum lancar membaca instruksi teks.
   - Gunakan pendekatan "AI Socratic Mentor (Zero-Scold)": saat anak salah menjawab kuis/eksperimen, berikan kalimat pemantik yang membimbing, bukan memarahi atau memberi tanda silang merah yang menakutkan.
3. Modul Kurikulum Merdeka SD:
   - Lab Sains Interaktif (Campur Warna cairan tabung, Siklus Air, Rantai Makanan, Rangkaian Listrik, dan Magnet Hunter).
   - Petualangan Hitung Ceria (Manipulatif Buah, Detektif Aljabar, dan Timbangan Neraca).
   - Literasi Nusantara 34 Provinsi & Panggung Lagu Nasional dengan tuts pianika.
   - Asesmen Mandiri 10 Mapel lengkap SD + 6 Agama resmi di Indonesia.
4. Arsitektur Teknis:
   - Gunakan Next.js 16 (App Router), TypeScript, dan Tailwind CSS.
   - Zero-Login & LocalStorage-First: tidak butuh server database mahal, instan dimainkan, dan 100% aman bagi privasi anak (bebas iklan & pelacak pihak ketiga).
   - Fitur Piagam Penghargaan PDF otomatis untuk mengapresiasi capaian bintang siswa.

Keluarkan luaran berupa PRD terstruktur lengkap dengan user persona siswa SD dan diagram arsitektur sistem.
```

* **Hasil & Dampak Pengembangan:**
  Tercapainya dokumen fondasi `docs/PRD.md` dan struktur modular proyek. Menghasilkan fondasi *zero-crash* dan identitas unik produk yang memadukan pedagogi Kurikulum Merdeka dengan inovasi hemat kuota Telkomsel.

---

## 2. PROMPT 2: FASE DEBUGGING KRITIS (PEMECAHAN MASALAH)

* **Kategori Wajib:** Debugging
* **Fokus:** Mengatasi Kerusakan Layout Cetak PDF Piagam A4 Landscape (Font Mikroskopis & Badge Bintang Melar Selebar Kertas Akibat Flexbox Stretch).
* **Waktu Eksekusi:** 9–10 Oktober 2026

```markdown
Sebagai Frontend & CSS Paged Media Expert, tolong analisis dan perbaiki bug kritis pada fitur cetak "Piagam Prestasi Siswa" di TobiQuest.

### Masalah yang Ditemukan:
Di tampilan modal web, sertifikat terlihat sangat rapi, proporsional, dan mewah. Namun saat pengguna menekan tombol "Cetak Piagam Prestasi" dan masuk ke mode Print / Save as PDF browser (A4 Landscape):
1. Kotak kuning bintang ("Pencapaian: X Bintang Kehormatan") melar dari ujung kiri ke ujung kanan kertas selebar A4.
2. Seluruh teks (judul, nama siswa, dan tanda tangan) mendadak mengecil drastis (hanya 8px–10px) seperti catatan kaki, menyisakan ruang putih kosong yang sangat luas di tengah kertas.
3. Terkadang sertifikat pecah menjadi 2–3 halaman terpotong.

### Analisis Akar Masalah:
- Di `globals.css` pada `@media print`, `#printable-certificate-inner` menggunakan `display: flex; flex-direction: column; justify-content: space-between;` tanpa `align-items: center`. Secara default CSS Flexbox menerapkan `align-items: stretch`, sehingga badge `inline-flex` dipaksa melebar 100% selebar halaman fisik A4 (297mm).
- Di `CertificateModal.tsx`, terdapat hardcoded modifier `print:text-[8px]` dan `print:my-1` yang merusak hierarki tipografi piagam resmi.

### Instruksi Perbaikan:
1. Perbaiki `globals.css`:
   - Atur `@page { size: A4 landscape; margin: 0; }`.
   - Kunci kontainer `#printable-certificate` tepat berdimensi 297mm x 210mm dengan `box-sizing: border-box`.
   - Di `#printable-certificate-inner`, tambahkan `align-items: center !important;` agar badge tidak melar.
2. Perbaiki `CertificateModal.tsx`:
   - Hapus semua kelas pengecil teks `print:text-[8px]` dan `print:text-[10px]`.
   - Gunakan ukuran font piagam yang megah untuk kertas A4 fisik: Judul text-4xl/5xl, Nama Siswa text-4xl font-extrabold, dan Stempel Medali w-16 h-16.
   - Tambahkan class `w-fit mx-auto self-center` pada badge bintang.
   - Pastikan hasil cetak 100% WYSIWYG (persis seperti preview) dan tepat 1 lembar A4 Landscape.
```

* **Hasil & Dampak Pengembangan:**
  Bug terselesaikan secara tuntas. Piagam penghargaan siswa dapat dicetak langsung ke PDF A4 Landscape dengan layout elegan, stempel resmi proporsional, dan tepat satu halaman tanpa pemborosan kertas.

---

## 3. PROMPT 3: FASE AUDIT & OPTIMASI PERFORMA

* **Kategori Wajib:** Audit & Optimasi
* **Fokus:** Mengatasi Delay 15 Detik Web Speech API di Browser Smartphone (Android Chrome) & Optimasi Bobot Aset untuk Telkomsel Lite Mode.
* **Waktu Eksekusi:** 10 Oktober 2026

```markdown
Bertindaklah sebagai Web Performance & Mobile Audio Specialist. 

Lakukan audit dan optimasi mendalam pada sistem audio Web Speech API di `src/lib/sound.ts` serta pemenuhan standar "Telkomsel Lite Mode (< 500 KB)".

### Gejala Masalah di Peramban Ponsel (Mobile Android):
Saat web TobiQuest pertama kali dibuka di smartphone, fitur suara maskot Tobi tidak langsung bersuara dan mengalami jeda/delay hening sekitar 14–15 detik saat tombol ditekan.

### Analisis Teknis Masalah:
1. Di Android Chromium, pemanggilan pertama `window.speechSynthesis.getVoices()` mengembalikan array kosong `[]` karena sistem OS memuat data suara secara asinkron (*lazy-loading*).
2. Jika sintesis suara dipanggil sebelum engine bangun, Android Chromium memicu antrean macet (*queue stall*) yang tertahan hingga watchdog timer 15 detik internal peramban me-reset antrean.
3. Kebijakan autoplay mobile browser mensyaratkan adanya interaksi fisik pengguna (*user gesture*) untuk membuka kunci `AudioContext` dan `SpeechSynthesis`.

### Instruksi Optimasi:
1. Implementasikan pola "Silent First-Touch Warm-Up":
   - Pasang event listener `{ once: true, passive: true }` untuk `touchstart` dan `click`.
   - Begitu jari pengguna pertama kali menyentuh layar, bangunkan AudioContext (`ctx.resume()`) dan panggil pemanasan senyap `speechSynthesis.resume()` serta `speechSynthesis.cancel()` di latar belakang.
2. Tambahkan Cache Voice Pre-loading:
   - Pantau event `window.speechSynthesis.onvoiceschanged` agar suara Bahasa Indonesia (`id-ID`) sudah tersimpan di memori sebelum tombol ditekan.
3. Cegah Garbage Collection Bug:
   - Simpan referensi objek `SpeechSynthesisUtterance` aktif pada properti kelas agar tidak dihapus memori Android sebelum suara selesai berbicara.
4. Verifikasi Telkomsel Lite Mode:
   - Pastikan seluruh efek audio menggunakan osilator murni (Web Audio API) tanpa bergantung pada file audio eksternal yang membebani kuota data siswa.
```

* **Hasil & Dampak Pengembangan:**
  Delay 15 detik di browser smartphone hilang sepenuhnya. Maskot Tobi mampu berbicara secara instan dalam hitungan milidetik setelah tombol ditekan, dan seluruh beban audio bernilai 0 KB transfer jaringan.

---

## 4. PROMPT 4: FASE FINISHING & POLISH UI/UX

* **Kategori Wajib:** Finishing
* **Fokus:** Redesain Menu Asesmen 10 Mapel & 6 Agama Menjadi Tombol Bulat Grid di Mobile, Perapian Segmented Tab Sirkuit Listrik, dan Pembersihan Footer.
* **Waktu Eksekusi:** 9–10 Oktober 2026

```markdown
Tolong lakukan pemolesan akhir (UI/UX Finishing & Polish) pada tampilan aplikasi KiddoQuest agar antarmuka mobile dan desktop memiliki standar kenyamanan dan estetika maksimal bagi siswa SD:

### 1. Menu Asesmen Mandiri 10 Mapel & 6 Agama (`src/components/zones/EvaluasiModal.tsx`):
- Masalah: 10 mapel dan 6 agama sebelumnya ditampilkan dalam kartu persegi panjang besar memanjang ke bawah, memaksa siswa melakukan scroll panjang di layar HP.
- Solusi: 
  - Ubah kontainer menjadi grid responsif: `grid grid-cols-3 sm:grid-cols-4 md:grid-cols-5 gap-3` (pada HP otomatis 3 kolom kesamping ala app-launcher).
  - Ubah item mapel dan agama menjadi tombol bulat ikonik (`w-14 h-14 rounded-full shadow-md mx-auto`) dengan warna tematik khas dan label teks ringkas di bawah tombol. Seluruh 6 agama pas dalam 2 baris (3 atas, 3 bawah) dalam 1 layar tanpa perlu scroll.

### 2. Tab Mode Sirkuit Listrik (`src/components/zones/science/ElectricCircuitsView.tsx`):
- Masalah: Tombol mode sirkuit (Rakit, Dasar, Seri, Paralel) sebelumnya menggunakan flex-wrap polos yang patah berantakan dan rata kiri di layar HP.
- Solusi:
  - Di Mobile: Kelompokkan tombol ke dalam Grid 2x2 simetris 50:50 (`grid grid-cols-2 gap-2 w-full`), diikuti tombol "Dengar Penjelasan" full-width di bawahnya.
  - Di Desktop: Buat tampilan "Segmented Lab Control" ber-ikon tematik (⚡, 💡, 🔗, 🔀) dengan aksen aktif gradasi emas dan pendaran neon lab.

### 3. Pembersihan Footer & Identitas Brand (`src/components/Footer.tsx`):
- Hapus badge privasi dan kolom redundan untuk memusatkan perhatian siswa pada navigasi utama.
- Buat teks hak cipta Telkomsel rata tengah (`text-center sm:text-right`) di mobile.
- Sesuaikan titik identitas "Telkomsel Lite Mode" menjadi warna merah khas Telkomsel (`bg-red-600`).
```

* **Hasil & Dampak Pengembangan:**
  Tampilan antarmuka di layar smartphone menjadi sangat ringkas, padat, simetris, dan intuitif disentuh oleh jari anak-anak tanpa perlu *scrolling* panjang yang melelahkan.

---

## 5. PROMPT 5: FASE INOVASI & FITUR UNGGULAN (BEBAS)

* **Kategori Wajib:** Bebas (Inovasi & Nilai Guna Nyata)
* **Fokus:** Simulator Pembelajaran Sains Kinestetik (Rakit Rangkaian Listrik Seri vs Paralel Pure SVG & Pipet Campur Warna Cairan).
* **Waktu Eksekusi:** 7–8 Oktober 2026

```markdown
Bertindaklah sebagai Senior Interactive Educational Technologist. 

Rancang modul pembelajaran sains interaktif kinestetik untuk materi Rangkaian Listrik dan Pencampuran Warna tanpa memakai aset gambar raster berat (100% Pure Vector SVG & Canvas):

### Spesifikasi Modul:
1. Laboratorium Sirkuit Listrik Seri & Paralel:
   - Buat simulasi sirkuit interaktif menggunakan SVG dengan visual aliran elektron animasi (CSS keyframe dashoffset).
   - Mode 1 (Assembly Puzzle): Siswa merakit sendiri komponen sirkuit (pasang baterai 1.5V, pasang saklar, dan bohlam). Jika sirkuit tertutup dan saklar ON, lampu menyala terang dengan radial gradient glow.
   - Mode 2 (Komparasi Seri vs Paralel): Tunjukkan perbedaan nyata konsep sains: jika satu lampu pada rangkaian seri diputus, semua lampu padam; sedangkan pada rangkaian paralel, lampu lainnya tetap menyala mandiri.
2. Laboratorium Pipet Campur Warna:
   - Buat alat pipet tetes interaktif yang dapat menyedot warna primer (Merah, Kuning, Biru).
   - Saat cairan diteteskan ke dalam tabung reaksi kimia, terjadi animasi gelembung busa (fizzy chemical reaction sound) dan cairan berubah menjadi warna sekunder (Oranye, Hijau, Ungu) disertai rumus visual HUD sains.
3. Kuis Diagnostik Sokratik Terintegrasi:
   - Setiap akhir eksperimen dilengkapi pertanyaan penalar sains yang langsung memberi reward bintang prestasi.

Pastikan seluruh kode ditulis dalam komponen TypeScript React murni dengan performa 60 FPS dan ukuran bundel seringan mungkin.
```

* **Hasil & Dampak Pengembangan:**
  Terciptanya stasiun eksperimen sains kinestetik yang mengubah teori sains abstrak menjadi pengalaman interaktif visual langsung bagi anak-anak SD, membuktikan potensi inovasi teknologi dalam dunia pendidikan dasar.

---

## KESIMPULAN

Melalui 5 tahapan prompt terkurasi di atas, proses pengembangan **TobiQuest** membuktikan penerapan metodologi *Vibe Coding* yang terencana, iteratif, dan berstandar teknis tinggi. AI Agent diberdayakan bukan sekadar untuk menghasilkan kode mentah, melainkan sebagai akselerator inovasi dalam memecahkan masalah nyata aksesibilitas, performa, dan pedagogi pendidikan anak di Indonesia.
