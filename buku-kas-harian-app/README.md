# Buku Kas Harian (proyek APK)

Aplikasi pencatat pemasukan dan pengeluaran harian dengan kategori Pokok, Gaya Hidup, dan Kewajiban, ringkasan otomatis untuk bulan depan, dan unduh Excel. Dibungkus dengan Capacitor supaya jadi aplikasi Android.

## Cara mendapatkan file APK (tanpa Android Studio)

APK dibangun otomatis oleh GitHub Actions, gratis.

1. Buat akun di github.com kalau belum punya, lalu buat repository baru (boleh private, nama bebas).
2. Ekstrak file zip ini. Di halaman repository, pilih **uploading an existing file**, lalu seret semua isi folder hasil ekstrak, termasuk folder `.github`. Klik **Commit changes**.
   - Kalau folder `.github` tidak ikut terunggah (folder yang diawali titik kadang tersembunyi), pilih **Add file > Create new file**, ketik nama `.github/workflows/build-apk.yml`, tempel isi file dengan nama yang sama dari zip, lalu commit.
3. Buka tab **Actions**. Proses **Build APK** berjalan sendiri setelah commit. Kalau tidak, pilih **Build APK** di daftar kiri, lalu **Run workflow**.
4. Tunggu sekitar 5 sampai 10 menit sampai muncul centang hijau. Klik proses itu, turun ke bagian **Artifacts**, lalu unduh **buku-kas-harian-apk**. Ekstrak zip-nya untuk mendapatkan `app-debug.apk`.
5. Kirim `app-debug.apk` ke HP (WhatsApp ke diri sendiri, Google Drive, atau kabel data), lalu ketuk filenya.
6. Android akan meminta izin **pasang dari sumber ini**. Izinkan, lalu pasang. Kalau Play Protect memberi peringatan, pilih **Tetap pasang**.

## Catatan

- Data tersimpan di HP itu sendiri. Kalau aplikasi dihapus atau data aplikasi dibersihkan, catatan ikut hilang, jadi sering-seringlah menekan **Unduh Excel** di menu Riwayat sebagai cadangan.
- Data dari versi web di Claude tidak otomatis pindah ke aplikasi ini.
- Font Schibsted Grotesk dan IBM Plex Mono diambil dari Google Fonts. Tanpa internet, aplikasi memakai font bawaan HP dan semua fitur tetap jalan.
- APK ini ditandatangani dengan kunci debug, cukup untuk dipasang di HP sendiri. Untuk terbit di Play Store, kamu perlu membuat APK rilis dengan kunci sendiri dan akun Google Play Developer.

## Struktur

- `www/index.html` berisi seluruh aplikasi, dan `www/xlsx.full.min.js` adalah pustaka pembuat file Excel.
- `capacitor.config.json` berisi nama dan ID aplikasi (`id.bukukas.harian`).
- `assets/` berisi sumber ikon aplikasi.
- `.github/workflows/build-apk.yml` adalah resep pembangunan APK.
