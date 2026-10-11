# LOG PROMPT MENTAH AWAL–AKHIR (RAW PROMPT LOG)
## Proyek: TobiQuest — Platform Web Edukasi Interaktif Siswa SD
**Kompetisi:** M-ONE Telkomsel Coding Competition 2026  
**Kategori:** Kategori Umum (Individu)  
**Tujuan Dokumen:** Lampiran Verifikasi Keaslian Karya dari Nol (Audit Trail)  
**Periode Pengerjaan:** 5 Oktober 2026 (09.30 WIB) – 11 Oktober 2026  

---

### SIKLUS PENGEMBANGAN KRONOLOGIS (5–11 OKTOBER 2026)

Berikut adalah catatan riwayat interaksi dan arahan prompt secara berurutan sejak pembukaan garis start lomba:

#### Sesi 1: Inisiasi Proyek & Fondasi Arsitektur (5 Oktober 2026)
* **Prompt 1.1:** Setup workspace Next.js App Router dengan TypeScript dan Tailwind CSS untuk platform web edukasi anak SD "KiddoQuest".
* **Prompt 1.2:** Rancang dokumen Product Requirements Document (`PRD.md`) yang memetakan modul Kurikulum Merdeka: Sains, Matematika, dan Literasi Nusantara.
* **Prompt 1.3:** Implementasi sistem penyimpanan state `src/lib/storage.ts` berbasis LocalStorage-First (zero-database dependency) dengan penanganan `try-catch` aman dari data korup.
* **Prompt 1.4:** Rancang komponen header navigasi anak dengan indikator bintang, profil kelas siswa, dan tombol toggle Telkomsel Lite Mode.

#### Sesi 2: Pembangunan Mesin Audio & Maskot Sokratik Tobi (6 Oktober 2026)
* **Prompt 2.1:** Buat `src/lib/sound.ts` menggunakan Web Audio API sintesis nada osilator murni (chime, tada, socratic hint) tanpa file audio MP3 eksternal.
* **Prompt 2.2:** Integrasikan Web Speech API (Text-to-Speech) suara Bahasa Indonesia (`id-ID`) pada komponen `MascotTobi.tsx`.
* **Prompt 2.3:** Buat logika Socratic Mentor (Zero-Scold): respon ramah yang membimbing dan tidak menyalahkan anak saat jawaban kuis belum tepat.

#### Sesi 3: Stasiun Eksperimen Lab Sains Interaktif (7–8 Oktober 2026)
* **Prompt 3.1:** Implementasi Lab Warna (`/lab-sains/warna`): pipet tetes interaktif cairan primer (merah, kuning, biru) dengan reaksi gelembung busa dan formula visual sekunder.
* **Prompt 3.2:** Implementasi Lab Siklus Air (`/lab-sains/siklus-air`): simulasi tahapan evaporasi laut, kondensasi awan, dan presipitasi hujan.
* **Prompt 3.3:** Implementasi Rantai Makanan (`/lab-sains/rantai-makanan`): ekosistem sawah dan laut dengan kuis dampak kepunahan produsen/konsumen.
* **Prompt 3.4:** Implementasi Sirkuit Listrik (`/lab-sains/listrik`): simulator puzzle sirkuit baterai-saklar-lampu dan komparasi nyata rangkaian Seri vs Paralel.
* **Prompt 3.5:** Implementasi Magnet Hunter (`/lab-sains/magnet`): pengelompokan benda magnetis dan non-magnetis di sekitar kelas.

#### Sesi 4: Modul Hitung Ceria & Tata Surya 3D (8–9 Oktober 2026)
* **Prompt 4.1:** Implementasi Kalkulasi Buah (`/hitung-ceria/kalkulasi`): penjumlahan representatif apel dan jeruk.
* **Prompt 4.2:** Implementasi Timbangan Neraca (`/hitung-ceria/neraca`): sistem keseimbangan dua lengan beban kuningan dan balok kayu.
* **Prompt 4.3:** Implementasi Detektif Aljabar (`/hitung-ceria/detektif`): eliminasi dan substitusi cilik dengan generator soal dinamis.
* **Prompt 4.4:** Implementasi Tata Surya Kosmik (`/tata-surya`): navigasi 9 objek langit 3D orbit dengan narasi fakta kosmik suara Tobi.

#### Sesi 5: Literasi 34 Provinsi, Lagu Nasional & Asesmen 10 Mapel (9 Oktober 2026)
* **Prompt 5.1:** Implementasi Literasi Cerita Rakyat 34 Provinsi (`/literasi-nusantara`) dengan filter pulau dan audio pembaca legenda.
* **Prompt 5.2:** Implementasi Panggung Lagu Wajib Nasional (`/lagu-nasional`) dengan sematan resmi YouTube, timestamp jumper otomatis, dan tuts pianika not angka asli.
* **Prompt 5.3:** Implementasi Bank Soal Asesmen Diagnostik (`/evaluasi`): 300+ soal mencakup 10 Mapel Kurikulum Merdeka dan pilihan 6 Agama resmi di Indonesia.

#### Sesi 6: Debugging Layout Cetak Piagam PDF & Audio Mobile (10 Oktober 2026)
* **Prompt 6.1:** Investigasi bug cetak PDF Piagam Penghargaan Siswa: perbaiki flexbox stretch pada badge bintang dan sesuaikan `@media print` agar pas tepat 1 halaman A4 Landscape.
* **Prompt 6.2:** Atasi masalah delay 15 detik suara Tobi di Android Chrome: tambahkan silent first-touch listener untuk warm-up `AudioContext` dan cache voice pre-loading.
* **Prompt 6.3:** Sederhanakan tombol maskot Tobi menjadi "Dengarkan Tobi" dan "Beri Semangat" dengan pembagian simetris 50:50 di layar smartphone.
* **Prompt 6.4:** Hapus animasi serpihan kertas confetti pada perolehan bintang agar tidak mengotori visual gelap Tata Surya dan mencegah lag pada perangkat spesifikasi rendah.

#### Sesi 7: Finishing UI/UX, Logika Matematika & Persiapan Penyerahan (11 Oktober 2026)
* **Prompt 7.1:** Redesain menu Asesmen 10 Mapel dan 6 Agama menjadi tombol bulat grid (3 kolom di HP) agar muat dalam satu layar tanpa scroll panjang.
* **Prompt 7.2:** Perbaiki generator soal Detektif Aljabar: hapus sontekan katalog nilai buah dan perbaiki bug pertanyaan kembar menjadi 4 pola investigasi acak (nilai tunggal, kelipatan, selisih, dan kombinasi baru).
* **Prompt 7.3:** Perbarui Segmented Control Lab Listrik di desktop dan grid 2x2 simetris di smartphone.
* **Prompt 7.4:** Perbarui daftar Inovasi Utama di footer dengan titik merah khas Telkomsel (`bg-red-600`) dan susun dokumen kelayakan resmi kompetisi.

---

### VERIFIKASI KEASLIAN KARYA
Seluruh tahapan kode, commit Git, serta rancangan komponen di atas dapat dicocokkan secara kronologis dengan riwayat *commit log* pada repository publik GitHub:
* Garis start karya: **5 Oktober 2026 (09.30 WIB)**
* Penyelesaian akhir & audit kelayakan: **11 Oktober 2026**
