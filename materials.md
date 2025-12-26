---
layout: default
title: Workshop Materials
---

<style>
  .content-wrapper {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
  }
  
  .nav-links {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    margin-bottom: 3rem;
    padding: 1.5rem;
    background: #f6f8fa;
    border-radius: 8px;
  }
  
  .nav-links a {
    padding: 0.6rem 1.2rem;
    background: white;
    border: 1px solid #e1e4e8;
    border-radius: 6px;
    text-decoration: none;
    color: #24292e;
    font-weight: 500;
    transition: all 0.2s;
  }
  
  .nav-links a:hover {
    background: #3498db;
    color: white;
    text-decoration: none;
    border-color: #3498db;
  }
  
  .resource-box { 
    background: #f0f8f0; 
    padding: 1.2rem; 
    margin: 1rem 0; 
    border-radius: 5px; 
    border-left: 4px solid #27ae60;
  }
  
  .resource-box h3 { margin-top: 0; color: #27ae60; }
  
  .section {
    margin-bottom: 3rem;
  }
  
  .section h2 {
    color: #2c3e50;
    border-bottom: 2px solid #3498db;
    padding-bottom: 0.5rem;
    margin-bottom: 1.5rem;
  }
</style>

<div class="content-wrapper">

<nav class="nav-links">
  <a href="{{ site.baseurl }}/">🏠 Home</a>
  <a href="{{ site.baseurl }}/setup.html">⚙️ Setup</a>
  <a href="{{ site.baseurl }}/materials.html" style="background: #3498db; color: white; border-color: #3498db;">📚 Materials</a>
  <a href="{{ site.baseurl }}/about.html">ℹ️ About</a>
  <span style="flex-grow: 1;"></span>
  <a href="{{ site.baseurl }}/workshops/workshop-1.html">Workshop 1</a>
  <a href="{{ site.baseurl }}/workshops/workshop-2.html">Workshop 2</a>
  <a href="{{ site.baseurl }}/workshops/workshop-3.html">Workshop 3</a>
</nav>

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
