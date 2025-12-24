---
layout: default
title: Workshop Materials
---

<style>
  nav a:hover { background-color: #34495e !important; }
  .resource-box { 
    background: #f0f8f0; 
    padding: 1.2rem; 
    margin: 1rem 0; 
    border-radius: 5px; 
    border-left: 4px solid #27ae60;
  }
  .resource-box h3 { margin-top: 0; color: #27ae60; }
</style>

<nav style="position: fixed; left: 0; top: 0; width: 200px; background-color: #2c3e50; padding: 1rem; height: 100vh; z-index: 1000; overflow-y: auto;">
  <div style="margin-bottom: 2rem;">
    <h3 style="color: white; margin-top: 0; font-size: 1rem;">Navigation</h3>
  </div>
  <a href="{{ site.baseurl }}/" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; padding: 0.5rem; border-radius: 3px;">🏠 Home</a>
  <a href="{{ site.baseurl }}/setup.html" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; padding: 0.5rem; border-radius: 3px;">⚙️ Setup</a>
  <a href="{{ site.baseurl }}/materials.html" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; font-weight: bold; padding: 0.5rem; background-color: #34495e; border-radius: 3px;">📚 Materials</a>
  <a href="{{ site.baseurl }}/about.html" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; padding: 0.5rem; border-radius: 3px;">ℹ️ About</a>
  <hr style="border-color: #34495e; margin: 1.5rem 0;">
  <div style="color: #95a5a6; font-size: 0.85rem; margin-bottom: 0.5rem;">Workshops:</div>
  <a href="{{ site.baseurl }}/workshops/workshop-1.html" style="display: block; margin-bottom: 0.5rem; text-decoration: none; color: white; padding: 0.4rem 0.5rem; font-size: 0.9rem; border-radius: 3px;">Workshop 1</a>
  <a href="{{ site.baseurl }}/workshops/workshop-2.html" style="display: block; margin-bottom: 0.5rem; text-decoration: none; color: white; padding: 0.4rem 0.5rem; font-size: 0.9rem; border-radius: 3px;">Workshop 2</a>
  <a href="{{ site.baseurl }}/workshops/workshop-3.html" style="display: block; margin-bottom: 0.5rem; text-decoration: none; color: white; padding: 0.4rem 0.5rem; font-size: 0.9rem; border-radius: 3px;">Workshop 3</a>
</nav>
<div style="margin-left: 240px; padding: 2rem; max-width: 900px;">

# Workshop Materials

All workshop materials are available for download. Please ensure you have completed the [Setup Guide](setup.html) before proceeding.

## Datasets

### Lightning Data
- **Description**: Sample lightning strike data with timestamps, locations, and intensity
- **Format**: CSV, GeoJSON
- **Size**: ~50 MB
- **Download**: [lightning-data.zip](#) *(coming soon)*

### Geospatial Boundaries
- **Description**: Administrative boundaries, terrain data, and base maps
- **Format**: Shapefiles, GeoPackage
- **Size**: ~25 MB
- **Download**: [boundaries.zip](#) *(coming soon)*

### Environmental Variables
- **Description**: Temperature, humidity, wind data for case studies
- **Format**: NetCDF, CSV
- **Size**: ~100 MB
- **Download**: [environmental-data.zip](#) *(coming soon)*

## Jupyter Notebooks

Interactive notebooks for each workshop:

### Workshop 1: Introduction to Geospatial Data
- [01-coordinate-systems.ipynb](#) - Understanding projections and CRS
- [02-reading-spatial-data.ipynb](#) - Loading and exploring geospatial files
- [03-basic-mapping.ipynb](#) - Creating your first maps

### Workshop 2: Advanced Spatial Analysis
- [04-spatial-joins.ipynb](#) - Combining spatial datasets
- [05-clustering.ipynb](#) - DBSCAN and other clustering algorithms
- [06-kernel-density.ipynb](#) - Density estimation and hotspot analysis

### Workshop 3: Time Series and Forecasting
- [07-temporal-patterns.ipynb](#) - Analyzing time series of thunderstorms
- [08-spatiotemporal.ipynb](#) - Combined space-time analysis
- [09-forecasting.ipynb](#) - Predictive modeling techniques

**Download All Notebooks**: [notebooks.zip](#) *(coming soon)*

## Code Examples

Standalone Python scripts for reference:

- [lightning_mapper.py](#) - Complete lightning visualization tool
- [spatial_stats.py](#) - Statistical analysis utilities
- [data_processor.py](#) - Data cleaning and preprocessing

**Download All Scripts**: [scripts.zip](#) *(coming soon)*

## Slides

Presentation slides in PDF format:

- [Workshop 1 Slides](slides/workshop1-slides.pdf) *(coming soon)*
- [Workshop 2 Slides](slides/workshop2-slides.pdf) *(coming soon)*
- [Workshop 3 Slides](slides/workshop3-slides.pdf) *(coming soon)*

## Additional Resources

### External Datasets

Publicly available datasets for further exploration:

- [NOAA Lightning Data](https://www.ncdc.noaa.gov/data-access)
- [Natural Earth Data](https://www.naturalearthdata.com/) - Free vector and raster map data
- [GHCN Climate Data](https://www.ncei.noaa.gov/products/land-based-station/global-historical-climatology-network-daily)

### Reference Documents

- [GeoPandas Cheat Sheet](https://github.com/geopandas/geopandas/raw/main/doc/source/_static/geopandas_cheat_sheet.pdf)
- [Coordinate Reference Systems Guide](https://www.earthdatascience.org/courses/earth-analytics/spatial-data-r/intro-to-coordinate-reference-systems/)

## Updates

Materials are regularly updated. Check back for:
- New datasets
- Updated notebooks with improvements
- Additional case studies

*Last updated: December 2025*

---

[← Back to Home](index.html)

</div>
