# sf-tourist-webgis

An interactive web map of San Francisco tourist attractions, built as a course project for Internet-Based GIS at Universitas Lampung.

Live: https://lior-pbl.github.io/sf-tourist-webgis-signet/

---

## Overview

The map overlays manually digitized attraction points on top of SF neighborhood boundary polygons sourced from DataSF. Popups pull photos from Wikimedia Commons. The whole thing is a static export from QGIS via qgis2web, hosted on GitHub Pages — no backend, no build step.

The goal was to practice the full GIS-to-web pipeline: data preparation in QGIS, export to Leaflet, and deploying a working interactive map without a server.

---

## Stack

- **QGIS 3.x** — data preparation, styling, and layer configuration
- **qgis2web** — exports the QGIS project to a self-contained Leaflet bundle
- **Leaflet.js** — handles the interactive map runtime
- **GitHub Pages** — static hosting

qgis2web was chosen over hand-writing the Leaflet config because the focus of this project is on the GIS data pipeline, not frontend JavaScript. The tradeoff is less flexibility in customizing the map behavior.

---

## Features

- Attraction markers categorized by type, color-coded via QGIS symbology
- Info popups with attraction name, description, and photo from Wikimedia Commons
- SF neighborhood polygon overlay for geographic reference
- Layer toggle to show/hide individual layers
- Basemap switcher between OpenStreetMap and Esri World Street Map
- Scale bar that adjusts between meters and kilometers
- Geolocation button to find your position on the map

---

## Data Sources

| Data | Source |
|---|---|
| Tourist attraction points | Manually digitized in QGIS |
| Neighborhood polygons | [DataSF Open Data](https://data.sfgov.org/) |
| Attraction photos | [Wikimedia Commons](https://commons.wikimedia.org/) |
| Basemap tiles | OpenStreetMap / Esri |

---

## Repository Structure

```
sf-tourist-webgis-signet/
├── index.html        # Entry point (qgis2web export)
├── data/             # GeoJSON: attraction points & neighborhood polygons
├── js/               # Leaflet scripts and layer configuration
├── css/              # Stylesheets from qgis2web export
├── images/           # Supporting image assets
├── legend/           # Map legend assets
└── webfonts/         # FontAwesome icon fonts
```

---

## Running Locally

The map fetches external basemap tiles, so it needs to run from a local server — opening `index.html` directly via `file://` will trigger a 403 on the OSM tile requests.

```bash
python -m http.server 8000
# Open http://localhost:8000
```

Or just use the live GitHub Pages link above.

---

## Known Limitations

- No offline support — basemap tiles require an internet connection
- Photo popups depend on Wikimedia Commons URLs staying stable; broken URLs will show a missing image
- The export is static: updating attraction data requires re-exporting from QGIS and redeploying

---

## Author

Rayhan Dwia Rukmana — 2315071087  
Geodesy & Geomatics Engineering, Universitas Lampung  
Course: Internet-Based GIS
