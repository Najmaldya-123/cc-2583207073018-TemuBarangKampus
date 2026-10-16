# Notes M03

- Deployment diverifikasi dari browser eksternal: http://20.2.114.157/ dan /health.
- Service cc-m03 dan caddy tetap aktif setelah reboot VPS.
- Spesifikasi VPS aktual: 2 vCPU, sekitar 1 GB RAM, 61 GB disk (berbeda dari asumsi modul).
- Backend Gunicorn hanya listen di 127.0.0.1:8000, akses publik lewat Caddy port 80.
