# SuaraRouter

Router CodeBuddy yang jalan di komputermu sendiri. Pasang sekali, lalu semua aplikasi AI-mu (opencode, Hermes, pi, omp, dan lainnya) cukup diisi **base URL, API key, dan nama model**.

SuaraRouter khusus pelanggan **@chinra_apikey_bot**. Router hanya bisa dipakai setelah ditautkan ke akun Telegram yang pernah membeli token CodeBuddy di bot.

## Yang dibutuhkan

- **Node.js 22 atau lebih baru.** Cek dengan `node -v`. Unduh di https://nodejs.org kalau belum ada.
- Akun Telegram yang pernah membeli token CodeBuddy di **@chinra_apikey_bot**.

## Install

1. Di Telegram, kirim `/router` ke **@chinra_apikey_bot**.
2. Bot membalas dengan perintah install khusus untukmu. Salin, lalu jalankan di terminal (Command Prompt / PowerShell di Windows).
3. Jalankan router:
   ```
   suara
   ```
4. Buka **http://127.0.0.1:8317** di browser.

Perintah install itu pribadi. Jangan dibagikan ke orang lain.

## Pertama kali dibuka

1. **Buat password admin dan PIN pemulihan.** Simpan keduanya. PIN dipakai kalau kamu lupa password.
2. **Tautkan akun Telegram.** Kirim `/tautkan` ke bot, lalu tempel kodenya di router. Kode berlaku 10 menit dan hanya bisa dipakai sekali.
3. **Tambah token.** Pilih transaksimu dari daftar, atau ketik ID transaksinya. Token dari klaim garansi, hadiah referral, dan bonus admin juga ikut.

## Pasang di aplikasi

Di router, buka **Panduan → Pasang di aplikasi**. Konfigurasi untuk opencode, Hermes, pi, dan omp dibuat otomatis lengkap dengan API key-mu, tinggal salin.

Untuk aplikasi lain, pilih provider **OpenAI-compatible (Chat Completions)** lalu isi:

| | |
|---|---|
| Base URL | `http://127.0.0.1:8317/v1` |
| API key | API key router, ada di menu **Pengaturan** |
| Model | salah satu nama di bawah |

Model yang tersedia: `gpt-5.3-codex`, `claude-opus-4.7-1m`, `claude-opus-4.6`, `gemini-3.1-pro`, `deepseek-v4.1-flash`, `glm-5.3`, `glm-5.3-flash`, `glm-5.2`, `kimi-k3`, `kimi-k2.8-preview`, `kimi-k2.6`, `hy4-preview`, `hy3`, `step-5-preview`.

Pakai **API key router**, bukan token CodeBuddy. Aplikasi yang hanya mendukung OpenAI Responses API (misalnya Codex CLI) atau Anthropic Messages (misalnya Claude Code) belum didukung.

## Update

Jalankan lagi perintah install dari `/router`. Token dan pengaturanmu tetap aman.

## Masalah umum

- **"Router belum ditautkan ke akun Telegram"**: buka dashboard, lalu tautkan akun dengan kode dari `/tautkan`.
- **HTTP 401 / "API key router diperlukan"**: API key di aplikasi salah. Salin ulang dari menu Pengaturan.
- **Jawaban terpotong**: aplikasi tidak mengirim batas output, jadi router memakai 4.096 token. Naikkan batas output di pengaturan aplikasi.
- **Semua request gagal**: buka menu Token, klik **Tes token bermasalah**. Kalau tetap gagal, tambah token baru.
- **`suara` tidak dikenal**: tutup lalu buka lagi terminal setelah install. Kalau masih, cek `node -v` minimal 22.

Panduan lengkap ada di menu **Panduan** di dalam router. Butuh bantuan? Kirim `/tiket` ke bot.

## Data dan keamanan

Router hanya bisa dibuka dari komputermu sendiri (`127.0.0.1`). Token disimpan terenkripsi di folder `.suararouter` di folder home-mu. Yang dikirim ke server toko hanya kode tautan, ID transaksi, dan pengecekan status tautan.

## Lisensi

Hak cipta dilindungi. Lihat file `LICENSE`.
