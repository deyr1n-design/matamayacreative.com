# Tayangkan matamayacreative.com (GitHub Pages + domain Squarespace)

Seluruh isi folder ini adalah websitenya. Tidak perlu build. File `CNAME` sudah berisi `matamayacreative.com`.

## 1. Buat repo di GitHub
1. Login di https://github.com, klik **New repository**.
2. Nama: `matamayacreative` (bebas). Pilih **Public** (GitHub Pages gratis butuh repo public). **Jangan** centang README/.gitignore.
3. Salin URL repo, misalnya `https://github.com/USERNAME/matamayacreative.git`.

## 2. Push dari komputer ini
Jalankan di terminal (repo lokal sudah di-commit):

```bash
cd "D:/Job/Claude Code/mata-maya-website"
git branch -M main
git remote add origin https://github.com/USERNAME/matamayacreative.git
git push -u origin main
```
Ganti `USERNAME`. Saat diminta login, ikuti jendela login GitHub yang muncul.

## 3. Aktifkan Pages
Repo > **Settings > Pages** > Source: **Deploy from a branch** > Branch: `main` / `(root)` > Save.
Di kolom **Custom domain** pastikan terisi `matamayacreative.com` (otomatis dari file CNAME). Alamat sementara: `https://USERNAME.github.io/matamayacreative/`.

## 4. Isi DNS di Squarespace
Squarespace: **Domains > matamayacreative.com > DNS > DNS Settings**. Hapus record bawaan untuk `@` dan `www`, lalu tambahkan:

| Host | Tipe | Nilai |
|---|---|---|
| `@` | A | `185.199.108.153` |
| `@` | A | `185.199.109.153` |
| `@` | A | `185.199.110.153` |
| `@` | A | `185.199.111.153` |
| `www` | CNAME | `USERNAME.github.io` |

(Cek IP terbaru di dokumentasi GitHub Pages "Managing a custom domain" jika ragu.)

## 5. HTTPS
Tunggu 15 menit sampai 48 jam, lalu di Settings > Pages centang **Enforce HTTPS**.

## Update situs
Edit file, lalu:
```bash
git add -A && git commit -m "update" && git push
```
Situs terbarui otomatis dalam 1-2 menit.

## Mengganti placeholder
- Foto karya: taruh di `assets/`, ganti `src` di bagian `#karya` pada `index.html`.
- Logo klien: cari komentar `PLACEHOLDER` di `index.html`.
