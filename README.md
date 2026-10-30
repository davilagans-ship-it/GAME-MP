# TAP ROYALE

Game reaksi multiplayer real-time. Semua perangkat yang membuka alamat server yang sama masuk ke satu arena bersama.

## Jalankan di komputer
1. Install Node.js versi LTS.
2. Ekstrak ZIP ini.
3. Buka terminal di folder `tap_royale`.
4. Jalankan `npm install`
5. Jalankan `npm start`
6. Buka `http://localhost:3000`.

Untuk mencoba dari HP lain di Wi-Fi yang sama, buka `http://IP-KOMPUTER:3000` (ganti dengan IP lokal komputer).

## Online untuk banyak perangkat
Deploy folder project ini ke layanan hosting Node.js yang mendukung WebSocket (misalnya Render atau Railway):
- Buat Web Service dari repository GitHub project ini.
- Build command: `npm install`
- Start command: `npm start`
- Setelah deploy, bagikan URL HTTPS yang diberikan ke semua pemain.

Penting: gunakan satu instance/server aktif agar semua pemain berada di arena yang sama. Jangan aktifkan autoscaling/multiple instances untuk versi starter ini.

## Aturan game
- Pemain masuk memakai nama.
- Match mulai otomatis 5 detik setelah pemain pertama bergabung.
- Durasi match 60 detik.
- Target berganti setiap detik. Pemain pertama yang menekan target pada ronde itu mendapat 1 poin.
- Setelah waktu habis, tiga skor teratas tampil di podium.

## Catatan
Versi starter menyimpan skor dan pemenang di memori server. Data akan reset jika server restart/deploy ulang. Untuk leaderboard permanen lintas restart, sambungkan database seperti PostgreSQL/Redis dan simpan skor di sana.

## Deploy website publik di Render
1. Upload isi folder `tap_royale` (bukan file ZIP) ke repository GitHub.
2. Di Render pilih **New > Blueprint** dan hubungkan repository tersebut.
3. Render membaca `render.yaml`; periksa konfigurasi lalu deploy.
4. Setelah status Live, buka URL `https://tap-royale.onrender.com` (nama URL bisa berbeda jika sudah dipakai) dan bagikan URL dari dashboard kepada teman.
5. Gunakan satu instance agar semua pemain tetap berada di satu server. Free web service dapat tidur setelah 15 menit tidak aktif dan perlu waktu untuk aktif kembali.
