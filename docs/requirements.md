# Requirements — Temu Barang Kampus

## 1. Deskripsi
Temu Barang Kampus adalah aplikasi Lost & Found untuk
membantu mahasiswa mencari, melaporkan, dan menemukan
kembali barang yang hilang atau ditemukan di kampus.

## 2. Tujuan
- Memusatkan informasi barang hilang dan ditemukan.
- Mempermudah pencarian dan pelaporan barang.
- Menghubungkan pemilik dengan penemu barang.

## 3. Pengguna
- Mahasiswa
- Dosen
- Staf kampus
- Admin kampus

## 4. Kebutuhan Fungsional
- Registrasi dan login pengguna.
- Pelaporan barang hilang dan ditemukan.
- Pencarian dan filter barang.
- Smart Match untuk mencocokkan laporan.
- Riwayat dan status barang.
- Pengelolaan laporan oleh admin.

## 5. Kebutuhan Nonfungsional
- Mudah digunakan melalui browser.
- Menjaga keamanan data pengguna.
- Dapat dijalankan pada VPS.
- Mudah diperbarui dan dipelihara.

## 6. Teknologi
- Ubuntu Server 24.04
- Python dan Flask
- Gunicorn dan Caddy
- Git dan systemd
- VPS: 2 vCPU, RAM 1 GB

## 7. Target M03
- Aplikasi berjalan pada VPS.
- Service dapat diperiksa melalui systemd.
- Endpoint /health dapat diuji.
- Aplikasi dapat diakses melalui reverse proxy.

## 8. Pengembangan Berikutnya
M05: Data
M06: Container
M07: Infrastructure as Code
M09: CI/CD

