# HandTrackingAI Web

Versi website dari HandTrackingAI yang berjalan di browser menggunakan HTML, CSS, JavaScript, dan MediaPipe Tasks Vision.

## Fitur
- Deteksi hingga dua tangan secara real-time
- Landmark/skeleton, label handedness, confidence, dan posisi pergelangan
- Dashboard FPS, jumlah tangan, dan estimasi confidence
- Mirror, smoothing, ambang deteksi
- Filter: normal, grayscale, sepia, vintage, cool blue, warm glow, negative
- Efek: skeleton, neon, star points, minimal points, tanpa overlay
- Ambil foto PNG dan rekam canvas ke WebM
- Responsif untuk desktop dan mobile

## Cara menjalankan lokal
1. Ekstrak folder ZIP.
2. Buka terminal pada folder ini.
3. Jalankan server lokal, misalnya dengan Python:
   - Windows: `py -m http.server 8000`
   - macOS/Linux: `python3 -m http.server 8000`
4. Buka `http://localhost:8000` di Chrome atau Edge.
5. Tekan **Aktifkan Kamera** dan izinkan akses kamera.

Jangan hanya membuka `index.html` dengan double-click. Modul JavaScript dan akses kamera perlu dijalankan dari `localhost` atau HTTPS.

## Deploy ke Vercel (cara mudah)
### Opsi A — Upload lewat GitHub (direkomendasikan)
1. Buat akun / masuk di https://github.com.
2. Buat repository baru bernama `handtrackingai-web`.
3. Upload `index.html`, `vercel.json`, dan `README.md` ke root repository (bukan folder bersarang).
4. Buka https://vercel.com dan masuk.
5. Klik **Add New… → Project**.
6. Import repository `handtrackingai-web`.
7. Framework Preset: pilih **Other**.
8. Build Command: kosongkan atau pilih **Override** lalu kosongkan.
9. Output Directory: `.` (titik) jika diminta.
10. Klik **Deploy**.
11. Setelah selesai, buka domain `.vercel.app` yang diberikan.

### Opsi B — Vercel CLI
Perlu Node.js terpasang:
1. Buka terminal pada folder proyek.
2. Jalankan `npm install -g vercel`.
3. Jalankan `vercel` dan ikuti instruksi login/deploy.
4. Untuk production, jalankan `vercel --prod`.

## Troubleshooting
- Jika tombol kamera tidak memulai, pastikan izin kamera diizinkan dan browser mendukung WebAssembly/WebGL.
- Versi ini mencoba GPU terlebih dahulu lalu otomatis mencoba CPU jika GPU tidak didukung.
- Buka DevTools browser (F12 → Console) jika masih ada error; pesan di panel halaman juga menampilkan penyebab umum.

## Penting
- Kamera hanya bekerja pada `localhost` atau halaman HTTPS. Domain Vercel `.vercel.app` memakai HTTPS.
- Saat pertama kali membuka halaman, browser mungkin meminta izin kamera.
- Model MediaPipe dan library dimuat dari CDN, sehingga koneksi internet dibutuhkan.
- Proses video dilakukan di browser. Website ini tidak mengunggah video kamera ke server aplikasi.
- Untuk perangkat mobile, gunakan browser modern dan izinkan kamera. Dukungan dan performa bergantung pada perangkat.
- Jika model tidak termuat, periksa koneksi internet, pemblokir konten, dan Console browser.
- `MediaRecorder` menyimpan video dalam WebM; dukungan codec tergantung browser.
- Tidak ada backend/database pada versi ini; Vercel hanya menyajikan file statis.
