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

## Integrasi Ollama Cloud (14 model)
Aplikasi menyediakan pemilih 14 model sesuai daftar pengguna. **GitHub Pages tidak dapat menjalankan backend** dan tidak boleh menyimpan `OLLAMA_API_KEY` dalam HTML.

### Deployment backend di Vercel (dari repository ini)
1. Impor `elsyarif2021/administrasi-guru` ke Vercel sebagai proyek baru dengan Framework Preset **Other** dan root repository.
2. Masukkan Environment Variables berikut di Vercel (jangan commit nilainya ke GitHub):
   - `OLLAMA_API_KEY` = API key dari akun Ollama Cloud
   - `APP_ACCESS_TOKEN` = kode akses panjang dan acak yang Anda buat sendiri
   - `ALLOWED_ORIGINS` = `https://elsyarif2021.github.io,https://nama-proyek.vercel.app` (ubah domain Vercel mengikuti URL produksi sesungguhnya).
3. Deploy. Situs Vercel akan menyediakan frontend dan `/api/generate` di domain yang sama.
4. Jika tetap membuka frontend melalui GitHub Pages, masukkan URL dasar Vercel pada kolom **URL Backend AI** serta kode akses yang sama dengan `APP_ACCESS_TOKEN`; klik **Uji Koneksi AI** lalu **Generate dengan Ollama AI**.
5. Untuk penggunaan bersama banyak guru, gunakan autentikasi per pengguna dan rate limiting sebelum membagikan akses luas. Kode akses bersama adalah kontrol dasar, bukan pengganti autentikasi multi-pengguna.

Backend melakukan permintaan ke API resmi `https://ollama.com/api/chat` dengan header Bearer. Hasil AI hanya dapat dicoba setelah server dikonfigurasi dan key sah.

**Model**: kimi-k3.1-pro:cloud, deepseek-v4.1-flash:cloud, deepseek-v4.1-flash:1017-cloud, glm-5.3-flash:cloud, inkling-2-small:cloud, beam:cloud, minimax-m3.1-flash:cloud, muse-spark-open:cloud, clef:cloud, clef:27b-cloud, kimi-k3:cloud, nemotron-3-ultra:cloud, mimo-v2.6-flash:cloud, mimo-v2.6-pro:cloud.

Nama model adalah daftar pilihan; ketersediaan dan hak akses aktual ditentukan Ollama, dan belum diuji tanpa API key.

Catatan: tombol **Templat Offline** tetap dapat digunakan tanpa backend. Dokumen tersimpan dalam browser lokal; fitur AI mengirim identitas dokumen dan topik ke Ollama Cloud melalui backend. Jangan memasukkan data pribadi siswa tanpa kebijakan perlindungan data yang sesuai.
