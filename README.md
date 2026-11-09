# POS Toko – paket build

## Perubahan pada HTML (www/index.html)
- Daftar hasil pencarian produk: baris yang AKAN di-input (dipilih panah/Enter) berwarna solid teal + garis kuning di kiri;
  baris yang hanya dilewati kursor mouse berwarna tint lembut. Light & dark mode.
- Penyesuaian layar HP (safe-area, padding). Ekspor CSV/backup memakai Simpan/Bagikan saat berjalan di APK.

## APK (tanpa Android Studio)
1. Upload folder ini ke repo GitHub.
2. Tab Actions → "Build APK" → Run workflow.
3. Unduh `POS-Toko-apk` → `app-debug.apk`, instal di HP.
Lokal: `npm install && npx cap add android && npx cap sync android && cd android && ./gradlew assembleDebug`

## Desktop
- Nativefier (butuh URL hosting): `nativefier/build.bat https://domain-anda/index.html`
- Offline penuh (tanpa hosting): `cd electron-offline && npm install && npm run dist`

## Catatan
- Data tersimpan di IndexedDB per aplikasi: data di APK/desktop TIDAK sama dengan data di browser. Pindahkan via backup/restore.
- Web Serial/WebUSB (scanner serial, printer ESC/POS) tidak tersedia di Android WebView dan di Nativefier.
  Scanner mode keyboard tetap jalan. Cetak struk di desktop: pakai mode "driver Windows".
