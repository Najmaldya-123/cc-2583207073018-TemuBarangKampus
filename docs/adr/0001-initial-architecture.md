# ADR-0001: Initial VPS Deployment Architecture

## Status
Accepted

## Context
VPS Ubuntu Server 24.04 dengan 2 vCPU, RAM sekitar 1 GB (887 MiB terbaca), dan disk 61 GB. Aplikasi Temu Barang Kampus perlu dapat diakses publik lewat IP dengan biaya dan kompleksitas operasional rendah.

## Decision
- Flask sebagai aplikasi web
- Gunicorn 1 worker, 2 thread, bind ke 127.0.0.1:8000
- systemd untuk mengelola service (cc-m03)
- Caddy sebagai reverse proxy di port 80
- UFW dengan port 22 dan 80
- GitHub sebagai sumber kode, deploy lewat deploy key

## Alternatives
1. Node.js + PM2
2. NGINX + Gunicorn
3. Docker
4. PHP-FPM

## Rationale
- Python/Flask sesuai stack yang sudah dipelajari dan cukup ringan untuk RAM terbatas.
- Gunicorn hanya listen di loopback sehingga tidak terekspos langsung; hanya Caddy yang menjadi pintu masuk publik.
- systemd membuat aplikasi hidup kembali setelah crash atau reboot.
- Caddy konfigurasinya lebih singkat daripada NGINX dan siap dipakai untuk HTTPS otomatis di M04.
- Satu worker dipilih karena RAM yang menjadi batasan utama, bukan CPU.
- Docker ditunda ke M06 agar baseline deployment mudah dipahami lebih dulu.

## Consequences
### Positive
- Arsitektur sederhana, mudah di-debug, dan footprint memori kecil.
- Backend tidak terekspos ke internet.

### Negative
- Masih HTTP saja dan satu VPS tanpa redundansi.
- Deployment masih manual (git pull lalu restart service).
- Satu worker membatasi konkurensi.

## Review Trigger
Review pada M06/M07.
