# 🗺️ San Francisco Tourist WebGIS

> Internet-Based GIS Practicum — Geodesy & Geomatics Engineering, Universitas Lampung

An interactive WebGIS application displaying the distribution of major tourist attractions in San Francisco, USA, complete with neighborhood boundary overlay.

## 🌐 Live Demo

👉 **[https://lior-pbl.github.io/sf-tourist-webgis-signet/](https://lior-pbl.github.io/sf-tourist-webgis-signet/)**

---

## 🖼️ Preview

![Preview WebGIS San Francisco](sfpreview.jpeg)

---

## ✨ Features

| Feature | Description |
|---|---|
| 📍 Tourist Attraction Points | Major tourist spots with detailed info popups |
| 📷 Photo Popups | Attraction photos sourced from Wikimedia Commons |
| 🏘️ Neighborhood Overlay | San Francisco neighborhood boundaries (polygon layer) |
| 🎨 Categorized Symbology | Markers differentiated by attraction type |
| 📏 Dynamic Scale Bar | Automatically switches between meters and kilometers |
| 🔍 Layer Toggle | Control panel to show/hide individual layers |
| 📍 Geolocation | Button to locate the user's position on the map |
| 🗺️ Basemap Switcher | OpenStreetMap (default) & Esri World Street Map — switchable directly on the map |

---

## 🛠️ Built With

- **QGIS 3.x** — Desktop GIS software for data preparation and management
- **qgis2web** — QGIS plugin for exporting projects into web-based WebGIS
- **Leaflet.js** — JavaScript library for interactive browser maps
- **GitHub Pages** — Free static hosting for WebGIS publication

---

## 📂 Repository Structure

```
sf-tourist-webgis-signet/
├── index.html        ← WebGIS application entry point
├── sfpreview.jpeg    ← Map preview screenshot
├── css/              ← Stylesheets (qgis2web export)
├── data/             ← GeoJSON data for tourist spots & neighborhoods
├── images/           ← Supporting image assets
├── js/               ← Leaflet scripts & layer configuration
├── legend/           ← Map legend files
└── webfonts/         ← Icon fonts (Leaflet/FontAwesome)
```

---

## 📡 Data Sources

| Data | Source |
|---|---|
| Tourist attraction points | Primary data — manual digitizing |
| Neighborhood polygons | [DataSF Open Data](https://data.sfgov.org/) |
| Attraction photos | [Wikimedia Commons](https://commons.wikimedia.org/) |
| Basemap | OpenStreetMap & Esri World Street Map |

---

## 🚀 Running Locally

Since this app uses external basemap tiles, run it via a local server — do not open the file directly:

```bash
# Python 3
python -m http.server 8000
# Open: http://localhost:8000
```

> ⚠️ Opening `index.html` directly via `file://` may cause a 403 error on the OSM basemap. Use a local server or access via the GitHub Pages URL instead.

---

## 🔧 Troubleshooting

| Issue | Solution |
|---|---|
| Blank/white basemap | Open via local server or GitHub Pages, not `file://` directly |
| Photo popups not showing | Check browser console — ensure photo URLs use HTTPS |
| 404 after deployment | Wait 2–5 minutes, ensure `index.html` is at the repo root |
| Changes not visible | Hard refresh: `Ctrl + Shift + R` |

---

## 👤 Author

**Rayhan Dwia Rukmana**  
Student ID: 2315071087  
Geodesy & Geomatics Engineering  
Universitas Lampung

---

*Built as a practicum project for the Internet-Based GIS course*
