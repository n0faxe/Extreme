Ninja Saga Extreme Panel 0.1.0 - Portable
===============================================

Cara menjalankan
----------------
1. Extract seluruh folder ini ke lokasi mana pun (path boleh mengandung spasi).
2. Double-click "Start Panel.bat". Browser dibuka otomatis di:
     http://127.0.0.1:8101
3. Jika browser tidak terbuka, buka alamat itu manual.

Service ID Panda sudah otomatis terisi di file ".env" saat build, jadi tidak
perlu diubah. Kalau service Panda diganti, edit PANDA_SERVICE_ID di ".env",
lalu restart panel.

Ganti port
----------
  "Start Panel.bat" --port=8201
  REM lalu buka http://127.0.0.1:8201

Atau langsung: node.exe app.cjs --port=8201 --open

Hanya satu instance yang bisa memakai port 8101. Untuk akun kedua, pakai
--port=8201 (localStorage per-port berbeda, jadi Device ID juga berbeda dan
perlu Access Key Panda sendiri).

Access Key
----------
Panel terkunci sampai Access Key Panda valid. Di kartu Access Key:
  1. Klik "1. Ambil Access Key (Panda)" (tab baru). Device ID otomatis
     terkirim sebagai parameter hwid.
  2. Selesaikan GetKey/checkpoint, lalu tempel key EXTREME-... ke panel.
  3. Klik "2. Buka Panel".

Device ID dikirim ke Panda sebagai HWID sekaligus AccountID. Key yang dibuat
di browser/komputer lain TIDAK akan berfungsi di sini.

Kesalahan "Panda timeout / tidak dapat dihubungi" bersifat sementara: akses
tetap aktif dan panel mencoba lagi. Hubungi Panda hanya jika key invalid /
expired / HWID mismatch.

Data & keamanan
---------------
- data/access_cache.json berisi grant hasil validasi. Jangan dibagikan.
- Quick login menyimpan username + password di localStorage browser.
- Panel hanya listen di 127.0.0.1. Jangan ubah ke 0.0.0.0 tanpa autentikasi.
- Katalog misi/enemy diunduh dari CDN kotagames saat runtime (butuh internet).
- app.cjs dan script UI sudah di-minify + di-obfuscate. Source tidak disertakan.

Lisensi
-------
Folder ini membawa binary Node.js. Sertakan LICENSE Node.js saat
mendistribusikan ulang. Panel ini bukan produk resmi Ninja Saga.

Pembuat tidak bertanggung jawab untuk penyalah gunaan panel ini.
