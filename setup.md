---
layout: default
title: Setup Guide
---

<nav style="position: fixed; left: 0; top: 0; width: 200px; background-color: #2c3e50; padding: 1rem; height: 100vh; z-index: 1000;">
  <div style="margin-bottom: 2rem;">
    <h3 style="color: white; margin-top: 0; font-size: 1rem;">Navigation</h3>
  </div>
  <a href="{{ site.baseurl }}/" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; padding: 0.5rem; border-radius: 3px;">🏠 Home</a>
  <a href="{{ site.baseurl }}/setup.html" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; font-weight: bold; padding: 0.5rem; background-color: #34495e; border-radius: 3px;">⚙️ Setup</a>
  <a href="{{ site.baseurl }}/materials.html" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; padding: 0.5rem; border-radius: 3px;">📚 Materials</a>
  <a href="{{ site.baseurl }}/about.html" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; padding: 0.5rem; border-radius: 3px;">ℹ️ About</a>
  <hr style="border-color: #34495e; margin: 1.5rem 0;">
  <div style="color: #95a5a6; font-size: 0.85rem; margin-bottom: 0.5rem;">Workshops:</div>
  <a href="{{ site.baseurl }}/workshops/workshop-1.html" style="display: block; margin-bottom: 0.5rem; text-decoration: none; color: white; padding: 0.4rem 0.5rem; font-size: 0.9rem; border-radius: 3px;">Workshop 1</a>
  <a href="{{ site.baseurl }}/workshops/workshop-2.html" style="display: block; margin-bottom: 0.5rem; text-decoration: none; color: white; padding: 0.4rem 0.5rem; font-size: 0.9rem; border-radius: 3px;">Workshop 2</a>
  <a href="{{ site.baseurl }}/workshops/workshop-3.html" style="display: block; margin-bottom: 0.5rem; text-decoration: none; color: white; padding: 0.4rem 0.5rem; font-size: 0.9rem; border-radius: 3px;">Workshop 3</a>
</nav>
<div style="margin-left: 220px;">

# Setup Guide

Follow these instructions to prepare your environment for the workshops.

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

## Verification

Test your installation:

```python
import geopandas as gpd
import pandas as pd
import matplotlib.pyplot as plt
import cartopy.crs as ccrs

print("All packages installed successfully!")
```

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

## Additional Resources

- [GeoPandas Documentation](https://geopandas.org/)
- [Cartopy Tutorial](https://scitools.org.uk/cartopy/docs/latest/)
- [Python for Data Science](https://jakevdp.github.io/PythonDataScienceHandbook/)

## Need Help?

Contact us at [zhuoj.duan@gmail.com](mailto:zhuoj.duan@gmail.com) or open an issue on GitHub.

[← Back to Home](index.html)
