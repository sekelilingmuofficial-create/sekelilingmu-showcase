# Sekelilingmu — Project Showcase

Landing page satu halaman yang menampilkan semua project yang sudah dibuat, lengkap dengan status (Live / In Progress / Coming Soon), stack teknologi, dan link live demo masing-masing.

## Isi Folder
```
sekelilingmu-showcase/
├── index.html   # halaman utama (semua CSS & JS sudah ada di dalam file ini)
└── README.md
```

## Cara Upload ke GitHub

1. Buat repository baru di GitHub, misalnya `sekelilingmu-showcase`.
2. Upload isi folder ini (drag & drop file `index.html` dan `README.md` lewat tombol **Add file > Upload files** di GitHub), atau via terminal:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: project showcase landing page"
   git branch -M main
   git remote add origin https://github.com/USERNAME/sekelilingmu-showcase.git
   git push -u origin main
   ```

## Cara Publish Gratis dengan GitHub Pages

1. Buka repository di GitHub > **Settings** > **Pages**.
2. Pada bagian **Source**, pilih branch `main` dan folder `/ (root)`.
3. Klik **Save**. Setelah beberapa menit, halaman akan aktif di:
   ```
   https://USERNAME.github.io/sekelilingmu-showcase/
   ```

## Kustomisasi

- Ganti link **LinkedIn** dan **Email** di bagian `<footer>` pada `index.html`.
- Tambah/ubah project di dalam `<div class="grid" id="grid">` — cukup salin satu blok `<div class="card">...</div>` dan sesuaikan isinya.
- Warna aksen bisa diubah lewat variabel `--cyan` di bagian `:root` pada tag `<style>`.
