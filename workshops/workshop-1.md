---
layout: default
title: Workshop 1 - Getting Started with Thunderstorm datasets & Jupyter Notebook
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
  
  .schedule-section { 
    background: #f8f9fa; 
    padding: 1.2rem; 
    margin: 1rem 0; 
    border-radius: 5px; 
    border-left: 4px solid #3498db;
  }
  
  .code-example { 
    background: #f4f4f4; 
    padding: 1rem; 
    border-radius: 5px; 
    margin: 1rem 0;
  }
  
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
  <a href="{{ site.baseurl }}/materials.html">📚 Materials</a>
  <a href="{{ site.baseurl }}/about.html">ℹ️ About</a>
  <span style="flex-grow: 1;"></span>
  <a href="{{ site.baseurl }}/workshops/workshop-1.html" style="background: #3498db; color: white; border-color: #3498db;">Workshop 1</a>
  <a href="{{ site.baseurl }}/workshops/workshop-2.html">Workshop 2</a>
  <a href="{{ site.baseurl }}/workshops/workshop-3.html">Workshop 3</a>
</nav>
</div>

# Workshop 1: Getting Started with Thunderstorm datasets & Jupyter Notebook

## Duration
3 hours

## Level
Beginner

## Overview

Set up your environment using Jupyter Notebook and explore real-world meteorological datasets to see what storm data looks like in practice.

## Learning Objectives

By the end of this workshop, you will be able to:

1. Understand coordinate reference systems (CRS) and map projections
2. Read and write common geospatial data formats (Shapefiles, GeoJSON, GeoPackage)
3. Perform basic spatial operations (buffering, intersections, unions)
4. Create static and interactive maps with lightning data
5. Calculate basic spatial statistics

## Prerequisites

- Basic Python knowledge
- Completed [Setup Guide](../setup.html)
- Downloaded [Workshop Materials](../materials.html)

## Schedule

### Part 1: Coordinate Systems and Projections (45 min)

**Topics:**
- Geographic vs. Projected coordinate systems
- Common CRS for meteorological data (WGS84, Web Mercator)
- Reprojecting data
- Understanding distortion

**Exercises:**
- Convert lightning coordinates between different CRS
- Calculate distances with appropriate projections

### Part 2: Working with Spatial Data (60 min)

**Topics:**
- Vector data: Points, Lines, Polygons
- Reading geospatial files with GeoPandas
- Data exploration and attributes
- Spatial indexing

**Exercises:**
- Load lightning strike data (point features)
- Load state/county boundaries (polygon features)
- Inspect spatial properties and attributes

### Break (15 min)

### Part 3: Basic Spatial Operations (45 min)

**Topics:**
- Buffering points
- Spatial joins
- Clipping and intersections
- Calculating areas and distances

**Exercises:**
- Create buffer zones around lightning strikes
- Count strikes within administrative boundaries
- Find strikes within a certain distance of cities

### Part 4: Creating Maps (45 min)

**Topics:**
- Static maps with Matplotlib and Cartopy
- Styling: colors, symbols, labels
- Adding base layers and context
- Interactive maps with Folium

**Exercises:**
- Create a publication-quality lightning map
- Build an interactive web map
- Add layers showing strike density

## Key Concepts

### Coordinate Reference Systems

```python
import geopandas as gpd

# Read data
lightning = gpd.read_file('lightning_data.geojson')

# Check CRS
print(lightning.crs)

# Reproject to appropriate CRS for distance calculations
lightning_proj = lightning.to_crs('EPSG:3857')
```

### Spatial Joins

```python
# Load boundaries
counties = gpd.read_file('counties.shp')

# Count lightning strikes per county
strikes_per_county = gpd.sjoin(
    counties, 
    lightning, 
    how='left', 
    predicate='contains'
).groupby('COUNTY_NAME').size()
```

### Basic Mapping

```python
import matplotlib.pyplot as plt
import cartopy.crs as ccrs

fig, ax = plt.subplots(
    subplot_kw={'projection': ccrs.PlateCarree()},
    figsize=(12, 8)
)

# Plot boundaries
counties.plot(ax=ax, facecolor='lightgray', edgecolor='black')

# Plot lightning strikes
lightning.plot(
    ax=ax, 
    marker='o', 
    color='red', 
    markersize=5, 
    alpha=0.6,
    label='Lightning Strikes'
)

ax.coastlines()
ax.set_title('Lightning Strikes by County')
plt.legend()
plt.show()
```

## Datasets Used

- **Lightning strikes**: 10,000 sample strikes from summer storm season
- **County boundaries**: US counties from Natural Earth Data
- **Cities**: Major cities for reference points

## Homework (Optional)

1. Create a map showing lightning density by county
2. Calculate the average distance between consecutive strikes
3. Identify the county with the highest strike rate per square kilometer
4. Create an animated map showing temporal progression of a storm system

## Additional Resources

- [GeoPandas Documentation](https://geopandas.org/en/stable/)
- [Cartopy Gallery](https://scitools.org.uk/cartopy/docs/latest/gallery/index.html)
- [EPSG.io](https://epsg.io/) - CRS reference

## Next Workshop

[Workshop 2: Advanced Spatial Analysis](workshop-2.html) - Deep dive into clustering and pattern detection

---

[← Back to Workshops](../index.html)


