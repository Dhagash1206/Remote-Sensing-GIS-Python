## Remote Sensing & GIS - Python Implementation

---

## About the Project

This project performs geospatial analysis on Census district boundary data using Python. It combines GIS operations, spatial queries, and data visualization into two clean, production-ready scripts.

The project covers two core areas:
- **Data Visualization** — loading district shapefiles, plotting choropleth maps, analyzing time-series raster values, and exporting statistical summaries
- **Advanced Spatial Analysis** — reprojecting coordinate systems, generating buffer zones, performing overlay operations (intersection/union), filtering by state, and running spatial queries to find neighboring districts

**Real-world use case:** Understanding spatial relationships between Indian districts — such as which districts border Rajasthan, or how raster values like NDVI change over time across regions.

---

## Project Structure

```
GeoSpatial_Project/
├── data/
│   ├── 2011_Dist.shp       # India district boundaries shapefile
│   ├── 2011_Dist.dbf       # Attribute data for shapefile
│   ├── 2011_Dist.shx       # Shape index file
│   ├── 2011_Dist.prj       # Projection info
│   └── 2011_Dist.sbx       # Spatial index
│
├── scripts/
│   ├── data_visualization.py        # Visualization & time-series analysis
│   └── advanced_spatial_analysis.py # Advanced GIS & spatial operations
│
├── outputs/                # Auto-generated maps, charts, CSV exports
│
└── README.md
```

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.12 |  |
| GeoPandas | Vector geospatial data handling |
| Matplotlib | Plotting and map visualization |
| Pandas | Tabular data and time-series analysis |

---

## How to Run

### 1. Install dependencies
```bash
pip install geopandas matplotlib pandas
```

### 2. Run visualization script
```bash
python scripts/data_visualization.py
```

### 3. Run spatial analysis script
```bash
python scripts/advanced_spatial_analysis.py
```

All outputs (PNG maps, CSV) are saved to the `/outputs` folder automatically.

---

## Script 1 - Data Visualization
- Load and plot India district shapefile
- Choropleth map using mean raster values
- Time-series line chart (2022-2025)
- Bar chart, scatter plot, correlation analysis
- Export statistical summary to CSV

## Script 2 - Advanced Spatial Analysis
- CRS inspection (EPSG:4326) and reprojection (EPSG:3857)
- 10km buffer zone analysis around districts
- Intersection and Union overlay operations
- State-level filtering (Rajasthan)
- Spatial query: districts touching Rajasthan boundary

---

## Notes
- `unary_union` is deprecated — replaced with `union_all()` in spatial analysis script
- Choropleth map requires `mean_value` column (from zonal statistics shapefile)
- All paths are relative — no hardcoded user paths
