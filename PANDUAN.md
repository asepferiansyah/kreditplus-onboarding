# Panduan Pasang Aplikasi (PWA) — Kreditplus Onboarding Portal

## Isi paket
- index.html            : cangkang aplikasi (membuka web app Apps Script dalam layar penuh)
- manifest.webmanifest  : nama, ikon, mode standalone
- sw.js                 : service worker (cache cangkang saja; data tetap online)
- icons/                : icon-192, icon-512, icon-maskable-512, apple-touch-icon

## Langkah
1. Apps Script: pasang semua file terbaru (Code.gs, DashboardBackend.gs, Login/Peserta/Penilai/Buddy/Admin/DashboardPortal .html), lalu Deploy > Manage deployments > salin URL web app (berakhiran /exec).
2. Buka index.html, ganti GANTI_DENGAN_URL_EXEC_APPS_SCRIPT (variabel APP_URL) dengan URL /exec tersebut.
3. Upload SELURUH isi folder ini (index.html, manifest.webmanifest, sw.js, folder icons) ke hosting HTTPS, mis. GitHub Pages / Netlify (drag & drop folder). Semua file harus berada di folder yang sama.
4. Buka alamat hosting di HP:
   - Android (Chrome): menu ⋮ > "Instal aplikasi" / "Tambahkan ke layar utama".
   - iPhone (Safari): Bagikan > "Tambah ke Layar Utama".
5. Kamera/foto/lokasi meminta izin saat pertama dipakai.

## Catatan
- Jika memperbarui cangkang (index.html/sw.js), naikkan versi CACHE di sw.js (kp-shell-v2, dst.) agar HP memuat versi baru.
- Perubahan pada portal (Apps Script) otomatis terlihat tanpa memasang ulang PWA.
- Jika layar tidak muncul setelah 15 detik, tersedia tautan "Buka langsung".
