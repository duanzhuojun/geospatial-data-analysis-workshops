---
layout: default
title: Setup Guide
---

<style>
  .content-wrapper {
    display: flex;
    max-width: 1400px;
    margin: 0 auto;
    padding: 2rem;
    gap: 2rem;
  }
  
  .nav-links {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    width: 200px;
    flex-shrink: 0;
    padding: 1.5rem;
    background: #f6f8fa;
    border-radius: 8px;
    height: fit-content;
    position: sticky;
    top: 2rem;
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
    text-align: center;
  }
  
  .nav-links a:hover {
    background: #3498db;
    color: white;
    text-decoration: none;
    border-color: #3498db;
  }
  
  .nav-links .spacer {
    height: 1rem;
  }
  
  .main-content {
    flex: 1;
    min-width: 0;
  }
  
  .info-box { 
    background: #e8f4f8; 
    padding: 1rem; 
    margin: 1rem 0; 
    border-radius: 5px; 
    border-left: 4px solid #3498db;
  }
  
  code { background: #f4f4f4; padding: 0.2rem 0.4rem; border-radius: 3px; }
  
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
  <a href="{{ site.baseurl }}/setup.html" style="background: #3498db; color: white; border-color: #3498db;">⚙️ Setup</a>
  <a href="{{ site.baseurl }}/materials.html">📚 Materials</a>
  <a href="{{ site.baseurl }}/about.html">ℹ️ About</a>
  <div class="spacer"></div>
  <a href="{{ site.baseurl }}/workshops/workshop-1.html">Workshop 1</a>
  <a href="{{ site.baseurl }}/workshops/workshop-2.html">Workshop 2</a>
  <a href="{{ site.baseurl }}/workshops/workshop-3.html">Workshop 3</a>
</nav>

<div class="main-content" markdown="1">

<div class="section">

# Setup Guide

Follow these instructions to prepare your environment for the workshops.

</div>

<div class="section">

## Required Software

### 1. Python Environment

We recommend using Python 3.8 or later. Install Anaconda or Miniconda:

- **Download**: [Anaconda](https://www.anaconda.com/download) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
- **Installation**: Follow the installer instructions for your operating system

### 2. Essential Libraries

Create a conda environment with required packages:

```bash
conda create -n geoworkshop python=3.10
conda activate geoworkshop
conda install -c conda-forge geopandas pandas numpy matplotlib cartopy jupyter
pip install pyproj shapely folium
```

### 3. Code Editor / IDE

Choose one:
- **VS Code** (recommended): [Download here](https://code.visualstudio.com/)
- **Jupyter Lab**: `conda install -c conda-forge jupyterlab`
- **PyCharm Community Edition**: [Download here](https://www.jetbrains.com/pycharm/)

</div>

<div class="section">

## Data Downloads

Workshop datasets will be provided during each session. To prepare:

1. Create a workshop directory:
   ```bash
   mkdir ~/geospatial-workshops
   cd ~/geospatial-workshops
   ```

2. Download sample datasets:
   - [Lightning data sample](https://example.com/lightning-sample.csv)
   - [Boundary files](https://example.com/boundaries.zip)

</div>

<div class="section">

## Verification

Test your installation:

```python
import geopandas as gpd
import pandas as pd
import matplotlib.pyplot as plt
import cartopy.crs as ccrs

print("All packages installed successfully!")
```

</div>

<div class="section">

## Troubleshooting

### Issue: Import errors with geopandas

**Solution**: Ensure GDAL is properly installed:
```bash
conda install -c conda-forge gdal
```

### Issue: Cartopy installation fails

**Solution**: Install dependencies first:
```bash
conda install -c conda-forge cartopy
```

</div>

<div class="section">

## Additional Resources

- [GeoPandas Documentation](https://geopandas.org/)
- [Cartopy Tutorial](https://scitools.org.uk/cartopy/docs/latest/)
- [Python for Data Science](https://jakevdp.github.io/PythonDataScienceHandbook/)

</div>

<div class="section">

## Need Help?

Contact us at [zhuoj.duan@gmail.com](mailto:zhuoj.duan@gmail.com) or open an issue on GitHub.

</div>

</div>

</div>
