# 🎯 To Do List & Music Bot

Bot Discord multifungsi untuk **mengelola to-do list** dan **memutar musik dari YouTube** dengan fitur antrean dan riwayat pemutaran.

---

## 📝 To-Do List Commands

| Command | Deskripsi | Contoh |
|----------|------------|---------|
| `/add <tugas> [tanggal]` | Tambahkan tugas baru (default: hari ini) | `/add Belajar Go 2025-11-09` |
| `/list [tanggal]` | Lihat daftar tugas di tanggal tertentu | `/list 2025-11-08` |
| `/done <tanggal> <nomor>` | Tandai tugas sebagai selesai | `/done 2025-11-09 1` |
| `/delete <tanggal> <nomor>` | Hapus tugas tertentu | `/delete 2025-11-08 2` |
| `/clear [tanggal]` | Hapus semua tugas di tanggal tertentu | `/clear 2025-11-09` |
| `/dates` | Lihat semua tanggal yang memiliki tugas | `/dates` |
| `/export_excel [start_date] [end_date]` | Export daftar tugas menjadi file Excel (bisa difilter tanggal) | `/export_excel start_date:2025-11-01 end_date:2025-11-09` |

---

## 🎵 Music Commands

| Command | Deskripsi | Contoh |
|----------|------------|---------|
| `/play <query>` | Putar musik dari YouTube (judul atau URL) | `/play Bohemian Rhapsody` |
| `/music-list` | Lihat daftar lagu dalam antrean | `/music-list` |
| `/stop` | Hentikan musik dan disconnect bot | `/stop` |
| `/history` | Lihat riwayat 10 lagu terakhir yang diputar | `/history` |

---

## 🎧 Cara Menggunakan Music Bot

1. **Join voice channel** terlebih dahulu  
2. Ketik `/play` di chat Discord  
3. Masukkan judul lagu atau URL YouTube  
4. Bot akan otomatis join dan mulai memutar musik  
5. Lagu berikutnya akan otomatis masuk ke antrean  

### Fitur Utama
- ✅ Auto-queue (antrean otomatis)
- ✅ YouTube search (cukup ketik judul lagu)
- ✅ Music history per server
- ✅ Queue management via `/music-list`
- ✅ Auto-disconnect setelah antrean kosong

---

## 📊 Contoh Hasil Export Excel `/export_excel`

File yang dihasilkan akan bernama seperti:
todo_JovL_2025-11-09.xlsx


Isi Excel:

| No | Tanggal | Judul Tugas | Status |
|----|----------|-------------|--------|
| 1 | 2025-11-09 | Belajar Golang | ✅ Selesai |
| 2 | 2025-11-09 | Kerjakan laporan | ❌ Belum |
| 3 | 2025-11-10 | Update bot Discord | ❌ Belum |

---

## ⚙️ Setup & Installation

### 1️⃣ Persiapan
Pastikan sudah menginstal:
- [Python 3.10+](https://www.python.org/downloads/)
- [PostgreSQL](https://www.postgresql.org/download/)
- [FFmpeg](https://ffmpeg.org/download.html)
- `git` (opsional)

---

### 2️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Konfigurasi Environment
Buat file `.env` di root project:

```env
DISCORD_TOKEN=your_discord_bot_token
DATABASE_URL=postgresql://user:password@localhost:5432/your_database_name
```

📦 Dependencies
| Library             | Fungsi                                        |
| ------------------- | --------------------------------------------- |
| `discord.py[voice]` | Interaksi dengan Discord API (termasuk voice) |
| `asyncpg`           | Driver PostgreSQL asynchronous                |
| `python-dotenv`     | Load environment variables dari file `.env`   |
| `PyNaCl`            | Voice encryption (untuk fitur musik)          |
| `yt-dlp`            | Mengunduh audio dari YouTube                  |
| `FFmpeg`            | Proses audio streaming                        |

## 🌐 Add to Your Server
**[Klik di sini untuk Invite Bot ke Server Discord](https://discord.com/oauth2/authorize?client_id=1436766092251893770)**

## 🔒 Permissions yang Diperlukan
* Send Messages
* Connect (Voice)
* Speak (Voice)
* Use Slash Commands
* Read Message History

## 🕒 Timezone
Semua waktu menggunakan **Asia/Jakarta (WIB / GMT+7)**.

## 🧰 Admin Commands

| Command | Deskripsi | Access |
|---------|-----------|--------|
| `/restart` | Restart bot | Owner only |

## 🐛 Troubleshooting

### 🎙️ Music bot tidak bisa join voice channel
```bash
pip install PyNaCl
```

### 🎵 FFmpeg not found
```bash
# Ubuntu/Debian
sudo apt-get install ffmpeg

# CentOS/RHEL
sudo yum install ffmpeg

# Windows
# Download dari https://ffmpeg.org/download.html dan tambahkan ke PATH
```

### ⚡ Slash commands tidak muncul
* Tunggu 5–10 menit setelah bot online
* Kick dan invite ulang bot ke server
* Pastikan bot punya izin **Use Application Commands**

## 🧾 Catatan Tambahan
* Format tanggal: `YYYY-MM-DD` (contoh: `2025-11-09`)
* Semua data to-do list disimpan per user
* Semua data music history disimpan per server
* Tidak menggunakan Docker — cukup jalankan langsung dengan Python