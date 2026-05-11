# sf-tourist-webgis

An interactive web map of San Francisco tourist attractions, built as a course project for Internet-Based GIS at Universitas Lampung.

Live: https://lior-pbl.github.io/sf-tourist-webgis-signet/

![Preview](sfpreview.jpeg)

---

## Overview

The map overlays a curated set of 9 tourist attraction points on top of San Francisco neighborhood boundary polygons sourced from DataSF. Each point is categorized (Iconic, History, Nature, etc.) with color-coded markers, and popups embed image tags pointing to Wikimedia Commons photos along with entry fee and operating hour info. The default basemap is OpenStreetMap, with Esri World Street Map available as an alternative via the layer switcher.

The whole thing is a static export from QGIS via the qgis2web plugin, with hand-edited additions to `index.html` for an interactive scale bar and a floating info box. Hosted on GitHub Pages — no backend, no build step, no server.

The goal was to practice the full GIS-to-web pipeline end-to-end: data preparation and styling in QGIS, export to a Leaflet-based static site, custom polishing in raw HTML/JS, and deployment to a free public host.

---

## Stack

- **QGIS 3.x** — data preparation, styling, and layer configuration
- **qgis2web** — exports the QGIS project to a self-contained Leaflet bundle
- **Leaflet.js** — handles the interactive map runtime
- **GitHub Pages** — static hosting

qgis2web was chosen over hand-writing the Leaflet config because the focus of this project is on the GIS data pipeline, not frontend JavaScript. The tradeoff is less flexibility in customizing the map behavior.

---

## Features

- 9 attraction points categorized by type (Iconic, History, Nature, etc.) with color-coded markers
- Info popups with entry fee, operating hours, and photos hotlinked from Wikimedia Commons
- SF neighborhood polygon overlay for geographic reference
- Layer toggle to show/hide individual layers
- Basemap switcher between OpenStreetMap (default) and Esri World Street Map
- Interactive scale bar (hand-added to the qgis2web export)
- Floating info box (hand-added to `index.html`)
- Geolocation button to find your position on the map

---

## Data Sources

| Data | Source |
|---|---|
| Tourist attraction points | Manually curated — coordinates from public sources |
| Neighborhood polygons | [DataSF Open Data](https://data.sfgov.org/) |
| Attraction photos | [Wikimedia Commons](https://commons.wikimedia.org/) |
| Basemap tiles | OpenStreetMap (default) & Esri World Street Map |

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
