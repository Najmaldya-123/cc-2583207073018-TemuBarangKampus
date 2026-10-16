# Temu Barang Kampus
### Campus Lost & Found

**Tagline: Temukan. Laporkan. Kembali.**

## Deskripsi
Temu Barang Kampus merupakan aplikasi untuk melaporkan,
mencari, dan menemukan kembali barang yang hilang atau
ditemukan di lingkungan kampus.

## Author
- Nama: Najma Lidia Hasna
- NIM: 2583207073018
- Kelas: 2B
- Prodi: Pendidikan Teknologi Informasi

## Fitur Utama
- Login dan registrasi.
- Laporan barang hilang dan ditemukan.
- Pencarian dan filter barang.
- Smart Match.
- Riwayat dan status laporan.
- Pengelolaan laporan oleh admin.

*Fitur dikembangkan secara bertahap.*

## Teknologi
- Ubuntu Server 24.04
- Python, Flask, Gunicorn
- Caddy
- Git dan systemd

## Arsitektur

```mermaid
flowchart LR
    A[Pengguna] --> B[Browser]
    B --> C[Caddy]
    C --> D[Gunicorn]
    D --> E[Flask]
```

## Deployment M03
- Direktori: `/srv/cc-m03`
- Service: `cc-m03.service`
- Backend: `127.0.0.1:8000`
- Public endpoint: `http://20.2.114.157/`

## Pemeriksaan

```bash
sudo systemctl status cc-m03 --no-pager
curl -fsS http://127.0.0.1:8000/health
curl -fsS http://127.0.0.1/health
```

## Dokumentasi
- [Requirements](docs/requirements.md)
- [Deployment](docs/deployment.md)

## Milestone
- M03: Baseline aplikasi dan deployment.
- M05: Data.
- M06: Container.
- M07: IaC.
- M09: CI/CD.

