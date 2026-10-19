HANDTRACKINGAI AR STUDIO — SINGLE FILE
=====================================

Isi proyek: index.html (seluruh UI + JavaScript + CSS dalam satu file).

GESTUR:
- Dua telapak terbuka di sisi kiri dan kanan wajah: face mesh putih + AR face frame.
- Pinch: ujung ibu jari dan telunjuk berdekatan; memunculkan magic frame.
- Peace sign: telunjuk dan jari tengah terbuka; memunculkan neon arcs/trail.
- Kepalan tangan: jari tertekuk; memunculkan pulse scanner.
- Jempol naik: jempol ke atas dengan jari lain tertekuk; memunculkan partikel.
- Satu telapak terbuka: radar HUD di sekitar tangan.

CARA UPLOAD KE VERCEL:
1. Ekstrak ZIP.
2. Upload index.html langsung di root repository GitHub.
3. Di Vercel, import repository itu.
4. Framework Preset: Other.
5. Build Command kosong; Output Directory `.` jika diminta.
6. Deploy.

PENTING:
- Internet diperlukan untuk memuat MediaPipe Hands dan Face Mesh dari CDN.
- Kamera membutuhkan HTTPS (domain Vercel sudah HTTPS) atau localhost, dan izin Camera.
- Proses kamera berjalan di browser; aplikasi tidak mengunggah video ke server sendiri.
- Ini adalah versi browser single-file, bukan aplikasi PHP server-side.
- Model face mesh dan hand tracking memakai MediaPipe CDN; performa tergantung perangkat/pencahayaan.
