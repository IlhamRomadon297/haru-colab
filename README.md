# Haru Colab

Toolkit Google Colab untuk **muxing/extract MKV ala MKVToolNix** + **downloader serbaguna** — semuanya lewat web terminal di browser (HP & laptop).

## Isi Repo

| File | Isi |
|------|-----|
| `muxing.ipynb` | Muxing & extract MKV (`haru-mux`, `haru-extract`) |
| `aio.ipynb` | Downloader: YouTube (`haru-ytdl`), LRC (`haru-lrc`), MangaDex (`haru-manga`) |

Tanpa file pendukung — semua tool ter-embed di notebook dan terinstall otomatis sebagai command.

## Cara Pakai (cukup 2 cell)

1. **1A Setup** — install dasar (mkvtoolnix, mediainfo).
2. **1B Web Terminal + CLI** — install tools otomatis, lalu buka link terminal yang muncul.

Di terminal:

```bash
haru-mux        # muxing: download, pilih file, edit track, mux, upload
haru-extract    # extract track audio/subtitle/video per episode
haru-ytdl       # download YouTube (video/audio/playlist/subtitle) — aio.ipynb
haru-lrc        # cari & download lirik LRC/SRT — aio.ipynb
haru-manga      # download chapter MangaDex — aio.ipynb
```

Fitur `haru-mux`: auto-detect semua track di dalam MKV (bahasa & nama asli kebaca), tabel ala MKVToolNix, auto-fix 1 default per tipe, **batch series mux** (pairing subtitle per episode + konfirmasi dulu), upload Gofile / Google Drive (API), notif Telegram.

## Secrets (menu Rahasia di Colab, aktifkan toggle-nya)

| Key | Keterangan |
|-----|------------|
| `GOFILE_API_TOKEN` | `fb` — proxy download/upload Gofile |
| `GDRIVE_CLIENT_ID` / `GDRIVE_CLIENT_SECRET` / `GDRIVE_REFRESH_TOKEN` | Upload Google Drive via API (tanpa mount) |
| `GDRIVE_FOLDER_ID` | (opsional) Folder GDrive tujuan |
| `HARU_BOT_TOKEN` | Token bot Telegram (BotFather) untuk notif |
| `OWNER_ID` | Chat ID Telegram penerima notif |

Tanpa secret pun tool inti tetap jalan — yang nonaktif hanya upload terkait & notif Telegram.

## Catatan

- Pakai **runtime CPU** (jangan GPU).
- Jangan commit file `cookies.txt` / secret apa pun ke repo ini.
