# Cara pasang video demo

Taruh file video screen-recording (.mp4) di folder ini, dengan nama file PERSIS seperti tabel
di bawah. Beberapa project punya 2 tampilan (Mobile App + Web Admin) — kalau project itu punya
2 video, otomatis muncul tab pemilih di halaman preview supaya pengunjung bisa pilih mau lihat
versi mobile atau versi web-nya.

| Project                | Device                   | Nama file yang harus dipakai   |
|-------------------------|--------------------------|----------------------------------|
| Ingatanku App            | Mobile App               | `ingatanku.mp4`                 |
| Sekelilingmu Docs         | Web (Laptop)              | `sekelilingmu-docs.mp4`        |
| Nominal POS                 | Kasir (Tablet)             | `nominal-pos-tablet.mp4`     |
| Nominal POS                   | Dashboard Admin (PC)         | `nominal-pos-desktop.mp4`  |
| Presensi App                     | Mobile App                 | `presensi.mp4`            |
| Presensi App                       | Web Admin                    | `presensi-admin.mp4`   |
| Ardya Assist Smarthome                | Mobile App                | `ardya-smarthome.mp4`|
| Akaris HRIS                             | Mobile App               | `akaris-hris.mp4`   |
| Akaris HRIS                               | Web Admin                  | `akaris-hris-admin.mp4` |
| TuanTroli App SaaS                          | Mobile App                | `tuantroli.mp4` |
| TuanTroli App SaaS                            | Web Admin                   | `tuantroli-admin.mp4` |

## Rasio video per jenis mockup
Supaya videonya pas mengisi bingkai mockup tanpa terpotong aneh, rekam dengan rasio berikut:

| Mockup        | Rasio disarankan   | Contoh resolusi |
|----------------|---------------------|-------------------|
| Phone (HP)      | 9:19.5 (potret)       | 720×1560        |
| Tablet            | 4:3 (landscape)         | 1024×768      |
| Laptop              | 16:10 (landscape)         | 1280×800    |
| Desktop/PC            | 16:9 (landscape)            | 1280×720  |

## Tips membuat video demo yang bagus
- Video akan diputar otomatis (autoplay, loop, tanpa suara) — jadi tidak perlu ada narasi/suara penting, cukup tunjukkan alur pemakaian aplikasi.
- Durasi pendek saja, cukup **10–20 detik** looping.
- **Ukuran file: usahakan 3–8 MB per video** (maksimal ±10–15 MB), supaya video langsung muncul tanpa buffering saat autoplay, dan tidak membebani repo Git / kuota hosting Vercel.
- Kompres videonya pakai ffmpeg, contoh untuk mockup HP (720 lebar):
  ```
  ffmpeg -i input.mov -vcodec libx264 -crf 28 -preset veryslow -an -vf scale=720:-2 ingatanku.mp4
  ```
  Untuk mockup landscape (tablet/laptop/desktop), ganti scale jadi lebar sesuai tabel di atas, contoh:
  ```
  ffmpeg -i input.mov -vcodec libx264 -crf 28 -preset veryslow -an -vf scale=1024:-2 nominal-pos-tablet.mp4
  ```
- Selama video belum ditaruh, halaman preview akan otomatis menampilkan pesan "Video demo segera hadir" di dalam mockup — jadi halaman tetap rapi walau videonya belum ada.

## Menambah / mengubah device sebuah project
Edit object `PROJECTS` di `preview.html`, pada bagian `devices: [...]`. Setiap device punya:
```js
{ type: "phone" | "tablet" | "laptop" | "desktop", label: "Nama tab yang tampil", video: "nama-file.mp4" }
```
Kalau cuma isi 1 device, tab pemilih otomatis disembunyikan (langsung tampil mockup itu saja).
