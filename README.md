# v4.1.6 Baghdad Marketplace
Offline: syiling, XP, KP dan Skill Point berasingan. Marketplace, inventori, ganjaran kosmetik, Secret Key, tiga cabang skill. Semua pembelian tanpa loading. KP 10 sekali bagi setiap kumpulan soalan unik yang betul dan bonus harian 2 per jawapan betul (percubaan pertama). Multiplayer masih server v4.1 HTTP polling dengan statistik sama.

## Hosting internet
Cara paling ringkas: hos folder ZIP server (bukan ZIP Netlify) sebagai satu aplikasi Node.js 20+ yang berjalan berterusan. Build: tiada dependency luar. Start: `npm start`. Port: `PORT` daripada hos, default 8080. Pastikan HTTPS dan storan kekal: tetapkan `RANK_FILE` kepada fail dalam volum kekal. Uji `/health` dan buka alamat HTTPS yang sama pada dua peranti. Tidak perlu isi URL pada pemain. Jika menggunakan Netlify berasingan, tetapkan `ARENA_DEFAULT_SERVER` kepada origin HTTPS server sebelum upload. Hosting awam belum dilakukan. Jangan dedahkan fail ranking yang mengandungi token profil.

# v4.1.5 Definitive Polish
Bank soalan 75 (soalan berbaris, pilihan jawapan ringkas; bukan semua pilihan berbaris), empat mekanik laluan pilihan, fakta loading, pembaikan checkpoint. Data 14 nota dan audio dikekalkan. Hos Node belum diterbitkan; protokol v4.1 HTTP polling kekal. Untuk sambungan automatik, disyorkan hos game dan server bersama menggunakan HTTPS.

# v4.1.1 Golden Welcome UI

Menu and entry screen updated; multiplayer API remains v4.1 and requires hosting.

# THE LOST MANUSCRIPTS v4.1 — The Legacy of Knowledge
Fasa pertama master upgrade berdasarkan v4.0. Offline kekal satu fail HTML, 4 chapter, 10 HP, 14 nota, 59 soalan, BGM asal, kedai/kuiz/boss tanpa loading. Sesi multiplayer menggunakan server v4.1, tidak serasi dengan server v4.0.

## Cara disyorkan: game dan server pada hos yang sama
1. Ekstrak ZIP Online Server. Pasang Node.js 20+.
2. Jalankan `npm start` dalam folder. Tiada dependency npm luar.
3. Buka http://localhost:8080 dalam browser. Scholar Arena terus menggunakan origin yang sama; tiada URL perlu ditaip.
4. Untuk ujian dua pemain gunakan dua profil browser atau satu incognito. Cipta bilik, kongsi kod, kedua-dua tekan Ready. Countdown 3 saat bermula selepas semua slot diisi dan semua sedia.
5. Untuk internet, hos folder ini pada hos proses Node berterusan dengan HTTPS dan storan kekal. Kongsi alamat HTTPS hos itu. Game dan API disediakan oleh proses sama. Uji /health (version 4.1). Hosting belum dilakukan.

## Jika menggunakan Netlify
ZIP Netlify hanya game statik. Online memerlukan hos Node.js berasingan. Selepas mendapatkan URL HTTPS backend, buka index.html dengan editor teks, cari `const ARENA_DEFAULT_SERVER = "";` dan isikan origin HTTPS sebenar (contoh placeholder sahaja: https://server-anda.example). Deploy semula index.html. Jangan masukkan URL palsu. Pemain kemudian menyambung tanpa mengisi URL. Butang Tetapan sambungan (hos) ialah override setempat untuk ujian, bukan tetapan global. Jika game statik tanpa server, status Offline adalah normal; Story Mode masih berfungsi.

## Penambahbaikan
- Enam kategori menu; tutorial melalui demo chapter 1 tanpa ganjaran; tiga kualiti partikel; transisi pantas pilihan; remap huruf Story Mode (anak panah/Space kekal).
- Profil tempatan, pilihan tiga warna jubah (dua dibuka dengan koleksi manuskrip), enam pencapaian. Bukan watak dengan statistik berlainan.
- Ready, countdown 3 saat, pilihan tiga tema visual arena (geometri asas sama), rematch jika semua peserta masih ada dan bersetuju. Quick Match menyertai tema bilik sedia ada jika ada.
- Ping ialah masa round-trip permintaan HTTP, bukan ICMP. Sambung semula menggunakan token sesi pada tab sama, sebelum had 30 saat terputus; sesi tidak bertahan selepas restart server.
- Laporan CSV dan JSON tanpa nama. Dashboard pensyarah mengimport fail JSON secara lokal, satu rekod setiap pelajar yang bersetuju; setiap import menggantikan senarai. Purata pre/post dikira hanya bagi rekod berpasangan. Statistik deskriptif, bukan bukti sebab-akibat. Rekod lokal tidak teresah.
- Presentation Mode mempunyai akses ke laporan dan dashboard. Demo sedia ada dikekalkan.

## Ranking dan batasan
Server mengira posisi, HP, skor dan ranking, menggunakan token sesi, rate limit dan had ganjaran lama. Ini bukan perlindungan anti-cheat penuh. Profil anonim kekal terikat pada browser. Tiada WebSocket, spectator, akaun rentas peranti, cloud save, local multiplayer satu skrin atau tournament automatik dalam fasa ini. HTTP polling kekal. Gunakan RANK_FILE pada volume kekal (contoh /data/rankings.json). Jangan dedahkan fail ranking atau token. Jalankan satu proses server sahaja. HTTPS diperlukan untuk internet.

## Ujian
Ujian API tempatan: bilik, ready/countdown, sambung token, soalan sama, tamat kuiz, rematch, permulaan PvP/race/coop. Ujian Chromium dengan kandungan HTML terus: menu, remap, profil, import dashboard, kuiz/kedai tanpa loading dan status offline. Navigasi fail sebenar disekat oleh persekitaran ujian. Kempen penuh, permainan multiplayer browser ke browser, prestasi internet dan hosting awam belum disahkan. Nota tertanam, bank soalan online dan enjin audio dibandingkan dengan v4.0 dan tidak berubah.
