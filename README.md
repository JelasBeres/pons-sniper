# Pons Sniper (Robinhood Chain)

Bot snipe token Pons v2 di Robinhood Chain, lengkap dengan dashboard web lokal.

- Menunggu launch dari wallet dev tertentu (atau semua dev), lalu membeli begitu snipe tax Pons turun di bawah batas.
- Jual otomatis saat take profit, stop loss, atau waktu hold habis (`maxHoldSeconds: 0` = tanpa batas waktu hold). Ada juga tombol **Jual sekarang**.
- Menampilkan untung/rugi posisi terbuka dan riwayat trade.

## Cara pakai

```bash
git clone https://github.com/JelasBeres/pons-sniper.git
cd pons-sniper
npm install
npm start
```

Buka **http://127.0.0.1:3010**, lalu:

1. Isi **Pengaturan**: private key wallet sniper (pakai wallet khusus, jangan wallet utama), beli per token, budget total, take profit, stop loss, dan alamat dev.
2. Tekan **Simpan pengaturan**.
3. Tekan **Mulai Dry Run** untuk mencoba tanpa uang, lalu **Stop** dan **Mulai LIVE** untuk trade sungguhan.

Bot hanya membeli kalau **saldo ≥ beli per token + cadangan gas**.

## Catatan

- Private key hanya disimpan di `sniper-config.json` di komputer kamu (tidak ikut ke git, tidak pernah dikirim ke browser).
- Dashboard hanya bisa dibuka dari komputer sendiri (127.0.0.1). **Jangan** dibuka ke internet: siapa pun yang bisa membuka halamannya bisa trade dengan wallet sniper.
- Bot hanya jalan selama terminal/laptop menyala.
- Kalau provider internet memblokir RPC Robinhood (misalnya XL), pakai VPN/DNS 1.1.1.1, atau isi **RPC URL** sendiri di Pengaturan lanjutan.
- Port lain: `SNIPER_UI_PORT=3020 npm start`.
- Token yang sudah graduate ke DEX tidak bisa dijual oleh bot, jual manual.
