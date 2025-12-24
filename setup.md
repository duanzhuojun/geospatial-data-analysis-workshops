---
layout: default
title: Setup Guide
---

<nav style="background-color: #f4f4f4; padding: 1rem; margin-bottom: 2rem; border-radius: 5px;">
  <a href="{{ site.baseurl }}/" style="margin-right: 20px; text-decoration: none;">🏠 Home</a>
  <a href="{{ site.baseurl }}/setup.html" style="margin-right: 20px; text-decoration: none; font-weight: bold;">⚙️ Setup</a>
  <a href="{{ site.baseurl }}/materials.html" style="margin-right: 20px; text-decoration: none;">📚 Materials</a>
  <a href="{{ site.baseurl }}/about.html" style="margin-right: 20px; text-decoration: none;">ℹ️ About</a>
</nav>

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
