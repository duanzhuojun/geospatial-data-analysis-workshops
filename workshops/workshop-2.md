---
layout: default
title: Workshop 2 - Advanced Spatial Analysis
---

<nav style="position: fixed; left: 0; top: 0; width: 200px; background-color: #2c3e50; padding: 1rem; height: 100vh; z-index: 1000; overflow-y: auto;">
  <div style="margin-bottom: 2rem;">
    <h3 style="color: white; margin-top: 0; font-size: 1rem;">Navigation</h3>
  </div>
  <a href="{{ site.baseurl }}/" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; padding: 0.5rem; border-radius: 3px;">🏠 Home</a>
  <a href="{{ site.baseurl }}/setup.html" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; padding: 0.5rem; border-radius: 3px;">⚙️ Setup</a>
  <a href="{{ site.baseurl }}/materials.html" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; padding: 0.5rem; border-radius: 3px;">📚 Materials</a>
  <a href="{{ site.baseurl }}/about.html" style="display: block; margin-bottom: 0.8rem; text-decoration: none; color: white; padding: 0.5rem; border-radius: 3px;">ℹ️ About</a>
  <hr style="border-color: #34495e; margin: 1.5rem 0;">
  <div style="color: #95a5a6; font-size: 0.85rem; margin-bottom: 0.5rem;">Workshops:</div>
  <a href="{{ site.baseurl }}/workshops/workshop-1.html" style="display: block; margin-bottom: 0.5rem; text-decoration: none; color: white; padding: 0.4rem 0.5rem; font-size: 0.9rem; border-radius: 3px;">Workshop 1</a>
  <a href="{{ site.baseurl }}/workshops/workshop-2.html" style="display: block; margin-bottom: 0.5rem; text-decoration: none; color: white; font-weight: bold; padding: 0.4rem 0.5rem; font-size: 0.9rem; background-color: #34495e; border-radius: 3px;">Workshop 2</a>
  <a href="{{ site.baseurl }}/workshops/workshop-3.html" style="display: block; margin-bottom: 0.5rem; text-decoration: none; color: white; padding: 0.4rem 0.5rem; font-size: 0.9rem; border-radius: 3px;">Workshop 3</a>
</nav>
<div style="margin-left: 220px;">

# Workshop 2: Advanced Spatial Analysis

## Duration
3 hours

## Overview

Building on Workshop 1, this session explores advanced spatial analysis techniques for identifying patterns in thunderstorm data. You'll learn clustering algorithms, kernel density estimation, and spatial statistics.

## Learning Objectives

By the end of this workshop, you will be able to:

1. Apply DBSCAN clustering to identify storm cells
2. Perform kernel density estimation for hotspot analysis
3. Calculate spatial autocorrelation (Moran's I)
4. Analyze point patterns and spatial randomness
5. Create advanced visualizations of spatial patterns

## Prerequisites

- Completion of Workshop 1
- Familiarity with NumPy and basic statistics
- Understanding of coordinate systems

## Schedule

### Part 1: Spatial Clustering (60 min)

**Topics:**
- Overview of clustering algorithms
- DBSCAN: parameters and applications
- K-means vs. spatial clustering
- Interpreting cluster results

**Exercises:**
- Identify distinct thunderstorm cells from lightning data
- Optimize clustering parameters
- Visualize cluster boundaries

### Part 2: Kernel Density Estimation (45 min)

**Topics:**
- Concepts of density estimation
- Bandwidth selection
- Creating heat maps
- Identifying hotspots

**Exercises:**
- Generate lightning strike density maps
- Compare different kernel functions
- Identify high-risk zones

### Break (15 min)

### Part 3: Spatial Statistics (45 min)

**Topics:**
- Spatial autocorrelation (Moran's I, Geary's C)
- Nearest neighbor analysis
- Ripley's K function
- Testing for spatial randomness

**Exercises:**
- Test if lightning strikes are randomly distributed
- Calculate spatial correlation of strike intensity
- Identify clustering at different scales

### Part 4: Advanced Visualization (45 min)

**Topics:**
- Multi-layer maps
- 3D visualization of density
- Time-animated spatial patterns
- Dashboard creation

**Exercises:**
- Create publication-ready figures
- Build an interactive analysis dashboard
- Visualize cluster evolution over time

## Key Concepts

### DBSCAN Clustering

```python
from sklearn.cluster import DBSCAN
import numpy as np

# Extract coordinates
coords = np.column_stack((
    lightning.geometry.x,
    lightning.geometry.y
))

# Apply DBSCAN
# eps: maximum distance between points (in map units)
# min_samples: minimum points to form a cluster
clustering = DBSCAN(eps=0.1, min_samples=10).fit(coords)

# Add cluster labels to GeoDataFrame
lightning['cluster'] = clustering.labels_

# -1 indicates noise points
n_clusters = len(set(clustering.labels_)) - (1 if -1 in clustering.labels_ else 0)
print(f'Found {n_clusters} storm cells')
```

### Kernel Density Estimation

```python
from scipy.stats import gaussian_kde

# Create density estimation
x = lightning.geometry.x
y = lightning.geometry.y

# Create grid
xi = np.linspace(x.min(), x.max(), 100)
yi = np.linspace(y.min(), y.max(), 100)
Xi, Yi = np.meshgrid(xi, yi)

# Calculate KDE
positions = np.vstack([Xi.ravel(), Yi.ravel()])
values = np.vstack([x, y])
kernel = gaussian_kde(values)
Zi = np.reshape(kernel(positions).T, Xi.shape)

# Plot
plt.figure(figsize=(12, 8))
plt.contourf(Xi, Yi, Zi, levels=20, cmap='YlOrRd')
plt.colorbar(label='Lightning Density')
plt.title('Lightning Strike Density Heat Map')
```

### Spatial Autocorrelation

```python
from esda.moran import Moran
from libpysal.weights import DistanceBand

# Create spatial weights matrix
w = DistanceBand.from_dataframe(
    lightning, 
    threshold=0.5,
    binary=True
)

# Calculate Moran's I for strike intensity
moran = Moran(lightning['intensity'], w)

print(f"Moran's I: {moran.I:.3f}")
print(f"P-value: {moran.p_sim:.3f}")

if moran.I > 0:
    print("Positive spatial autocorrelation (clustering)")
elif moran.I < 0:
    print("Negative spatial autocorrelation (dispersion)")
else:
    print("Random spatial pattern")
```

## Case Study: Severe Thunderstorm Analysis

We'll analyze a real severe weather event:

1. **Data**: Lightning strikes from a supercell thunderstorm
2. **Goal**: Identify the storm core and track its movement
3. **Methods**: 
   - Temporal clustering to separate storm phases
   - Spatial clustering to identify core regions
   - Density analysis to map intensity

### Results Interpretation

- Cluster centers indicate storm cell locations
- Density peaks show areas of highest activity
- Temporal progression reveals storm tracks

## Advanced Topics

### Spatial Statistics with PySAL

```python
import esda
from libpysal import weights

# Create queen contiguity weights
w = weights.Queen.from_dataframe(counties)

# Local Moran's I for each county
from esda.moran import Moran_Local

lisa = Moran_Local(counties['strike_count'], w)

# Identify significant clusters
counties['hotspot'] = lisa.q  # Quadrant classification
```

### 3D Visualization

```python
from mpl_toolkits.mplot3d import Axes3D

fig = plt.figure(figsize=(12, 8))
ax = fig.add_subplot(111, projection='3d')

# Plot strikes with intensity as height
ax.scatter(
    lightning.geometry.x,
    lightning.geometry.y,
    lightning['intensity'],
    c=lightning['intensity'],
    cmap='plasma'
)

ax.set_xlabel('Longitude')
ax.set_ylabel('Latitude')
ax.set_zlabel('Intensity (kA)')
```

## Datasets Used

- **High-resolution lightning data**: 100,000+ strikes from major storm event
- **Radar data**: Reflectivity for validation
- **Terrain data**: Digital elevation model

## Homework (Optional)

1. Compare clustering results using different DBSCAN parameters
2. Implement a custom distance metric for temporal-spatial clustering
3. Create an animation showing cluster evolution
4. Perform nearest neighbor analysis on identified storm cores

## Additional Resources

- [Scikit-learn Clustering](https://scikit-learn.org/stable/modules/clustering.html)
- [PySAL Spatial Analysis](https://pysal.org/)
- [Spatial Point Pattern Analysis](https://mgimond.github.io/Spatial/point-pattern-analysis.html)

## Next Workshop

[Workshop 3: Time Series and Forecasting](workshop-3.html) - Temporal analysis and predictive modeling

[← Back to Workshops](../index.html)
