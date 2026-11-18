# Administrasi Guru — Portal Mandiri

Aplikasi administrasi guru berbasis **HTML, CSS, dan JavaScript** yang dapat digunakan langsung di browser tanpa server dan tanpa dependensi.

## Cara menjalankan
Buka `index.html` menggunakan browser modern. Untuk menjadikannya situs web, aktifkan GitHub Pages dari branch `main` (root). URL situs GitHub Pages baru tersedia setelah fitur tersebut diaktifkan dan deployment selesai.

## Fitur
- Rencana Pembelajaran: CP, TP, ATP, Prota, Promes, Modul Ajar
- Jurnal Guru: jurnal pembelajaran, bahan ajar, LKPD, refleksi, portofolio
- Administrasi Asesmen: KKTP, kisi-kisi, soal, rubrik, remedial dan pengayaan
- Editor draf, penyimpanan lokal pada browser, ekspor Word `.doc`, cetak/PDF, serta impor/ekspor cadangan JSON

## Keterbatasan
Generator memakai templat lokal, **bukan model AI**. Draf harus diverifikasi guru berdasarkan dokumen kurikulum, kebutuhan sekolah, dan materi faktual. Data disimpan dalam `localStorage` perangkat masing-masing, tidak tersinkron antar perangkat. Belum tersedia login guru, database cloud, dan Ollama Cloud.

## Privasi
Jangan memasukkan data pribadi sensitif siswa ke dalam situs yang belum memiliki sistem autentikasi dan penyimpanan aman.
