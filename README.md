# LogbookTracker MagangHub (PWA)

Aplikasi web **Progressive Web App (PWA)** ringan, responsif, dan dapat digunakan secara **offline** untuk membantu peserta **MagangHub** mencatat poin aktivitas harian, mendapatkan pengingat jadwal pengisian logbook, menyusun draf logbook otomatis, serta memantau progress magang jangka panjang.

## Fitur Utama

- **Quick Notes Aktivitas Harian**: Catat poin pekerjaan, kendala, dan pembelajaran dalam hitungan detik sepanjang jam kerja.
- **Pengingat Harian (Visual Banner & Web Notification API)**: Atur jam pengingat harian agar tidak lupa mengisi logbook ke portal MagangHub.
- **Generator Draf Logbook Otomatis**: Merangkum poin catatan harian secara otomatis (format terstruktur per kategori atau paragraf ringkas) lengkap dengan tombol satu klik **Salin Teks Logbook**.
- **Tracker Progress Jangka Panjang**: Pantau total hari magang berjalan, *streak* pengisian logbook berturut-turut, dan bar persentase durasi magang.
- **Riwayat & Filter Status**: Cari catatan berdasarkan tanggal atau kata kunci, filter berdasarkan status (`Belum Dikirim` / `Sudah Dikirim`), serta edit catatan kapan saja.
- **Offline-First & Installable (PWA)**: Dapat di-install langsung ke layar utama HP Android, iOS, maupun Desktop, dan tetap berjalan penuh tanpa koneksi internet.
- **Penyimpanan Lokal + Ekspor CSV/JSON**: Semua data tersimpan privat di `localStorage` perangkat pengguna dengan fitur ekspor ke CSV dan backup/restore JSON.

## Struktur Folder Repository

```text
├── index.html                  # Halaman utama aplikasi (HTML, CSS, JS + UI_TEXT terpusat)
├── manifest.json               # Web App Manifest (ikon, nama aplikasi, mode standalone)
├── sw.js                       # Service Worker untuk caching offline & klik notifikasi
├── offline.html                # Halaman fallback saat perangkat offline
├── icons/
│   ├── icon-192.png            # Ikon PWA 192x192
│   ├── icon-512.png            # Ikon PWA 512x512
│   ├── icon-maskable-512.png   # Ikon PWA Maskable 512x512 (Android adaptive icon)
│   └── apple-touch-icon.png    # Ikon layar utama iOS 180x180
├── .gitignore                  # Daftar file yang diabaikan Git
└── README.md                   # Dokumentasi proyek
```

## Cara Deploy ke GitHub Pages

1. Buat repository baru di GitHub (misalnya: `logbook-maganghub`).
2. Upload seluruh isi folder package ini ke branch `main` repository tersebut.
3. Buka tab **Settings** → **Pages** di repository GitHub kamu.
4. Pada bagian **Build and deployment**, pilih **Source: Deploy from a branch**, lalu pilih branch `main` dan folder `/ (root)`, kemudian klik **Save**.
5. Tunggu 1–2 menit hingga URL GitHub Pages aktif (`https://<username>.github.io/logbook-maganghub/`). Buka URL tersebut di HP atau browser laptop, lalu klik **Install Aplikasi**.

## Kustomisasi Teks Antarmuka

Seluruh teks antarmuka disimpan dalam satu objek JavaScript bernama `UI_TEXT` di dalam `index.html` sehingga mudah disesuaikan tanpa mengubah logika aplikasi.
