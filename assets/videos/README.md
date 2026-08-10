# Cara pasang video demo

Taruh file video screen-recording (.mp4) di folder ini, dengan nama file PERSIS seperti berikut
(sesuai id project di `preview.html`):

| Project                  | Nama file yang harus dipakai   |
|---------------------------|---------------------------------|
| Ingatanku App              | `ingatanku.mp4`                |
| Sekelilingmu Docs           | `sekelilingmu-docs.mp4`        |
| Nominal POS                 | `nominal-pos.mp4`              |
| Presensi App                 | `presensi.mp4`                 |
| Ardya Assist Smarthome        | `ardya-smarthome.mp4`         |
| Akaris HRIS                    | `akaris-hris.mp4`             |
| TuanTroli App SaaS               | `tuantroli.mp4`             |

## Tips membuat video demo yang bagus
- Rekam layar aplikasi (HP atau screen recorder), rasio **9:19.5 (portrait, seperti layar HP)** paling pas untuk mockup ini.
- Video akan diputar otomatis (autoplay, loop, tanpa suara) — jadi tidak perlu ada narasi/suara penting, cukup tunjukkan alur pemakaian aplikasi.
- Kompres videonya (misalnya pakai HandBrake atau ffmpeg) supaya ukurannya kecil dan cepat dimuat, contoh:
  ```
  ffmpeg -i input.mov -vcodec libx264 -crf 28 -preset veryslow -an ingatanku.mp4
  ```
- Selama video belum ditaruh, halaman preview akan otomatis menampilkan pesan "Video demo segera hadir" di dalam mockup HP — jadi halaman tetap rapi walau videonya belum ada.

Kalau ingin menambah project baru, tambahkan datanya di object `PROJECTS` pada `preview.html`,
lalu taruh video dengan nama `{id-project}.mp4` di folder ini.
