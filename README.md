# 🗺️ San Francisco Tourist WebGIS

> Praktikum Sistem Informasi Geografi Berbasis Internet — Teknik Geodesi dan Geomatika, Universitas Lampung

Aplikasi WebGIS interaktif yang menampilkan persebaran objek wisata utama di San Francisco, USA, lengkap dengan overlay batas-batas neighborhood kota.

## 🌐 Live Demo

👉 **[https://lior-pbl.github.io/sf-tourist-webgis-signet/](https://lior-pbl.github.io/sf-tourist-webgis-signet/)**

## 🖼️ Preview

![Preview WebGIS San Francisco](sfpreview.jpeg)
---

## ✨ Fitur

| Fitur | Keterangan |
|---|---|
| 📍 Titik Objek Wisata | Objek wisata utama dengan popup info lengkap |
| 📷 Popup Foto | Foto objek dari Wikimedia Commons |
| 🏘️ Neighborhood Overlay | Batas-batas neighborhood kota SF (polygon layer) |
| 🎨 Simbologi Kategorik | Marker dibedakan berdasarkan tipe objek wisata |
| 📏 Scale Bar Dinamis | Otomatis beralih satuan meter ↔ kilometer |
| 🔍 Layer Toggle | Panel kontrol untuk mengaktifkan/menonaktifkan layer |
| 📍 Geolocation | Tombol untuk menemukan posisi pengguna di peta |
| 🗺️ Basemap Esri | Esri World Street Map |

---

## 🛠️ Teknologi yang Digunakan

- **QGIS 3.x** — Perangkat lunak GIS desktop untuk mempersiapkan dan mengelola data
- **qgis2web** — Plugin QGIS untuk mengekspor proyek menjadi WebGIS berbasis web
- **Leaflet.js** — Library JavaScript untuk peta interaktif di browser
- **GitHub Pages** — Hosting statis gratis untuk publikasi WebGIS

---

## 📂 Struktur Repositori

```
sf-tourist-webgis-signet/
├── index.html        ← Entry point aplikasi WebGIS
├── css/              ← Stylesheet (hasil export qgis2web)
├── data/             ← Data GeoJSON layer objek wisata & neighborhood
├── images/           ← Aset gambar pendukung
├── js/               ← Script Leaflet & konfigurasi layer
├── legend/           ← Gambar/file legenda peta
└── webfonts/         ← Font icon (Leaflet/FontAwesome)
```

---

## 📡 Sumber Data

| Data | Sumber |
|---|---|
| Titik objek wisata | Data primer — digitasi manual |
| Polygon neighborhood | [DataSF Open Data](https://data.sfgov.org/) |
| Foto objek wisata | [Wikimedia Commons](https://commons.wikimedia.org/) |
| Basemap | Esri World Street Map |

---

## 🚀 Cara Menjalankan Secara Lokal

Karena menggunakan tile basemap eksternal, jalankan via server lokal — bukan buka file langsung:

```bash
# Python 3
python -m http.server 8000
# Buka: http://localhost:8000
```

> ⚠️ Membuka `index.html` langsung (`file://`) dapat menyebabkan error 403 pada basemap. Gunakan server lokal atau akses via URL GitHub Pages.

---

## 🔧 Troubleshooting

| Masalah | Solusi |
|---|---|
| Basemap tidak muncul (layar putih) | Pastikan basemap sudah diganti ke Esri di `index.html` |
| Foto popup tidak tampil | Cek browser console — pastikan URL foto menggunakan HTTPS |
| Halaman 404 setelah deploy | Tunggu 2–5 menit, pastikan `index.html` ada di root repo |
| Update tidak kelihatan | Hard refresh: `Ctrl + Shift + R` |

---

## 👤 Penulis

**Rayhan Dwia Rukmana**  
NPM: 2315071087  
Program Studi Teknik Geodesi dan Geomatika  
Universitas Lampung

---

*Dibuat sebagai tugas praktikum mata kuliah SIG Berbasis Internet*
