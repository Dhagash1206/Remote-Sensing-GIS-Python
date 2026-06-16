# Remote Sensing & GIS - Python Implementation

A hands-on Python project for geospatial analysis on Indian district boundary data. Part of a Remote Sensing and GIS training programme.

---

## Basis of This Project

This project is built on **GIS + Python** using:

- **Shapefile data:** `2011_Dist.shp` — India district boundaries from the 2011 Census
- **Libraries:** GeoPandas (maps), Matplotlib (charts), Pandas (tables and stats)
- **Goal:** Learn and apply remote sensing and GIS workflows in code — not just draw a map

---

## What Does It Do?

This project runs **two scripts**, not one map.

### Script 1 — `data_visualization.py`

- Loads district boundaries from the shapefile
- Plots the India district boundary map
- Builds line, bar, and scatter charts from sample time-series data
- Exports a statistical summary CSV to `outputs/`

### Script 2 — `advanced_spatial_analysis.py`

- Reprojects coordinates (EPSG:4326 → EPSG:3857)
- Creates 10 km buffers around districts
- Filters Rajasthan districts
- Finds neighbor districts touching Rajasthan (17 districts)
- Runs **intersection** and **union** between two meaningful layers:
  - Layer 1: Neighbor districts touching Rajasthan
  - Layer 2: 10 km buffer around Rajasthan

---

## Features

- Charts and CSV export
- CRS reprojection
- Buffer analysis
- State-level filtering
- Spatial neighbor queries
- Overlay operations (intersection and union)

---

## Where Does It Help?


- Hands-on GIS with Python 
- Boundary analysis, neighbor detection, buffer zones
- Base for zoning, border studies, regional analysis

**Example questions this project answers:**

- Which districts border Rajasthan?
- What area lies within 10 km of a state boundary?
- How do you overlay two geographic layers in Python?

---

## Project Structure

```
GeoSpatial_Project_test/
├── data/
│   ├── 2011_Dist.shp       # India district boundaries shapefile
│   ├── 2011_Dist.dbf       # Attribute data for shapefile
│   ├── 2011_Dist.shx       # Shape index file
│   ├── 2011_Dist.prj       # Projection info
│   └── 2011_Dist.sbx       # Spatial index
│
├── scripts/
│   ├── data_visualization.py        # Visualization and time-series analysis
│   └── advanced_spatial_analysis.py # Advanced GIS and spatial operations
│
├── outputs/                # Auto-generated maps, charts, CSV exports
├── requirements.txt        # Pinned Python dependencies
│
└── README.md
```

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.12+ | Runtime |
| GeoPandas | Vector geospatial data handling |
| Matplotlib | Plotting and map visualization |
| Pandas | Tabular data and time-series analysis |

---

## How to Run

### 1. Create virtual environment and install dependencies

**PowerShell (Windows):**

```powershell
cd GeoSpatial_Project_test
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

**Linux / macOS:**

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 2. Run Scripts

```bash
python scripts/data_visualization.py
python scripts/advanced_spatial_analysis.py
```

All outputs (PNG maps, CSV) are saved to the `outputs/` folder automatically.

---

## Sample Outputs

| File | Description |
|------|-------------|
| `01_district_boundaries.png` | India district boundary map (base layer) |
| `03_time_series_line.png` | Time-series line chart |
| `04_bar_chart.png` | Year-wise bar chart |
| `05_scatter_plot.png` | Scatter plot |
| `Statistical_Summary.csv` | Exported stats |
| `d8_01_district_boundaries.png` | District boundaries (spatial script) |
| `d8_02_buffer_analysis.png` | 10 km buffer around all districts |
| `d8_03_intersection_overlay.png` | Neighbor districts inside Rajasthan buffer |
| `d8_04_union_overlay.png` | Rajasthan districts + buffer zone |
| `d8_05_rajasthan_districts.png` | Rajasthan districts only |
| `d8_06_touching_districts.png` | Districts touching Rajasthan |

---

## Notes

- `unary_union` is deprecated — replaced with `union_all()` in the spatial analysis script
- Choropleth map requires `mean_value` column (from zonal statistics shapefile)
- All paths are relative — no hardcoded user paths
- `.venv/` and `outputs/` are gitignored

---
