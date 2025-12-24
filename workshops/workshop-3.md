---
layout: default
title: Workshop 3 - Time Series and Forecasting
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
  <a href="{{ site.baseurl }}/workshops/workshop-2.html" style="display: block; margin-bottom: 0.5rem; text-decoration: none; color: white; padding: 0.4rem 0.5rem; font-size: 0.9rem; border-radius: 3px;">Workshop 2</a>
  <a href="{{ site.baseurl }}/workshops/workshop-3.html" style="display: block; margin-bottom: 0.5rem; text-decoration: none; color: white; font-weight: bold; padding: 0.4rem 0.5rem; font-size: 0.9rem; background-color: #34495e; border-radius: 3px;">Workshop 3</a>
</nav>
<div style="margin-left: 220px;">

# Workshop 3: Time Series and Forecasting

## Duration
3 hours

## Overview

This workshop focuses on temporal analysis of thunderstorm data and introduces forecasting techniques. You'll learn to analyze time series patterns, perform spatiotemporal analysis, and build predictive models for lightning activity.

## Learning Objectives

By the end of this workshop, you will be able to:

1. Analyze temporal patterns in lightning data
2. Perform time series decomposition and trend analysis
3. Conduct spatiotemporal clustering
4. Build forecasting models for lightning activity
5. Validate and interpret model predictions

## Prerequisites

- Completion of Workshops 1 and 2
- Basic understanding of statistics
- Familiarity with machine learning concepts (helpful but not required)

## Schedule

### Part 1: Temporal Pattern Analysis (60 min)

**Topics:**
- Time series basics for point data
- Aggregating lightning data by time intervals
- Seasonal and diurnal patterns
- Trend detection and decomposition

**Exercises:**
- Analyze hourly, daily, and seasonal lightning patterns
- Identify peak activity periods
- Decompose time series into components

### Part 2: Spatiotemporal Analysis (45 min)

**Topics:**
- Space-time cubes and visualization
- Spatiotemporal clustering (ST-DBSCAN)
- Tracking storm movement
- Calculating propagation velocity

**Exercises:**
- Track individual storm systems over time
- Calculate storm speed and direction
- Create space-time visualizations

### Break (15 min)

### Part 3: Forecasting Methods (45 min)

**Topics:**
- Time series forecasting (ARIMA, Prophet)
- Machine learning approaches (Random Forest, XGBoost)
- Feature engineering for lightning prediction
- Model evaluation metrics

**Exercises:**
- Build an ARIMA model for hourly lightning counts
- Use environmental variables for ML predictions
- Compare model performance

### Part 4: Model Validation and Applications (45 min)

**Topics:**
- Cross-validation for time series
- Spatial validation techniques
- Uncertainty quantification
- Operational forecasting considerations

**Exercises:**
- Validate models using holdout data
- Create probabilistic forecasts
- Build a simple forecasting dashboard

## Key Concepts

### Time Series Aggregation

```python
import pandas as pd

# Ensure datetime index
lightning['timestamp'] = pd.to_datetime(lightning['timestamp'])
lightning = lightning.set_index('timestamp')

# Aggregate by hour
hourly_counts = lightning.resample('H').size()

# Calculate rolling statistics
rolling_mean = hourly_counts.rolling(window=24).mean()
rolling_std = hourly_counts.rolling(window=24).std()

# Plot
fig, ax = plt.subplots(figsize=(12, 6))
hourly_counts.plot(ax=ax, label='Hourly Strikes', alpha=0.5)
rolling_mean.plot(ax=ax, label='24-hour Average', linewidth=2)
ax.fill_between(
    rolling_mean.index,
    rolling_mean - rolling_std,
    rolling_mean + rolling_std,
    alpha=0.3,
    label='±1 Std Dev'
)
ax.set_ylabel('Lightning Strikes')
ax.legend()
```

### Time Series Decomposition

```python
from statsmodels.tsa.seasonal import seasonal_decompose

# Daily aggregation
daily_counts = lightning.resample('D').size()

# Decompose
decomposition = seasonal_decompose(
    daily_counts,
    model='additive',
    period=7  # Weekly seasonality
)

# Plot components
fig, axes = plt.subplots(4, 1, figsize=(12, 10))
decomposition.observed.plot(ax=axes[0], title='Observed')
decomposition.trend.plot(ax=axes[1], title='Trend')
decomposition.seasonal.plot(ax=axes[2], title='Seasonal')
decomposition.resid.plot(ax=axes[3], title='Residual')
plt.tight_layout()
```

### Spatiotemporal Clustering

```python
# ST-DBSCAN implementation
from sklearn.cluster import DBSCAN

# Normalize time to same scale as space
# Convert time to hours since start
lightning['time_hours'] = (
    lightning.index - lightning.index.min()
).total_seconds() / 3600

# Create spatiotemporal coordinate array
coords_st = np.column_stack([
    lightning.geometry.x,
    lightning.geometry.y,
    lightning['time_hours'] * 0.1  # Scale time relative to space
])

# Cluster
st_clustering = DBSCAN(eps=0.5, min_samples=10).fit(coords_st)
lightning['st_cluster'] = st_clustering.labels_

# Analyze clusters
for cluster_id in set(st_clustering.labels_):
    if cluster_id == -1:
        continue
    
    cluster_data = lightning[lightning['st_cluster'] == cluster_id]
    
    # Calculate cluster statistics
    duration = (cluster_data.index.max() - cluster_data.index.min())
    centroid = cluster_data.geometry.unary_union.centroid
    
    print(f"Cluster {cluster_id}:")
    print(f"  Duration: {duration}")
    print(f"  Centroid: {centroid}")
    print(f"  Strikes: {len(cluster_data)}")
```

### ARIMA Forecasting

```python
from statsmodels.tsa.arima.model import ARIMA

# Prepare data
train = hourly_counts[:-24]  # All but last 24 hours
test = hourly_counts[-24:]   # Last 24 hours for validation

# Fit ARIMA model
model = ARIMA(train, order=(2, 1, 2))
model_fit = model.fit()

# Forecast
forecast = model_fit.forecast(steps=24)

# Evaluate
from sklearn.metrics import mean_absolute_error, mean_squared_error

mae = mean_absolute_error(test, forecast)
rmse = np.sqrt(mean_squared_error(test, forecast))

print(f"MAE: {mae:.2f}")
print(f"RMSE: {rmse:.2f}")

# Plot
plt.figure(figsize=(12, 6))
train[-72:].plot(label='Training Data')
test.plot(label='Actual', color='green')
forecast.plot(label='Forecast', color='red')
plt.legend()
plt.title('24-Hour Lightning Forecast')
```

### Machine Learning Forecasting

```python
from sklearn.ensemble import RandomForestRegressor
from sklearn.model_selection import TimeSeriesSplit

# Feature engineering
def create_features(df):
    df = df.copy()
    df['hour'] = df.index.hour
    df['dayofweek'] = df.index.dayofweek
    df['month'] = df.index.month
    df['lag_1h'] = df['strikes'].shift(1)
    df['lag_24h'] = df['strikes'].shift(24)
    df['rolling_mean_6h'] = df['strikes'].rolling(6).mean()
    return df

# Prepare data
df = pd.DataFrame({'strikes': hourly_counts})
df = create_features(df)
df = df.dropna()

# Features and target
features = ['hour', 'dayofweek', 'month', 'lag_1h', 'lag_24h', 'rolling_mean_6h']
X = df[features]
y = df['strikes']

# Time series cross-validation
tscv = TimeSeriesSplit(n_splits=5)

# Train model
model = RandomForestRegressor(n_estimators=100, random_state=42)

# Cross-validate
scores = []
for train_idx, val_idx in tscv.split(X):
    X_train, X_val = X.iloc[train_idx], X.iloc[val_idx]
    y_train, y_val = y.iloc[train_idx], y.iloc[val_idx]
    
    model.fit(X_train, y_train)
    pred = model.predict(X_val)
    score = mean_absolute_error(y_val, pred)
    scores.append(score)

print(f"Average MAE: {np.mean(scores):.2f}")

# Feature importance
importance = pd.DataFrame({
    'feature': features,
    'importance': model.feature_importances_
}).sort_values('importance', ascending=False)

print("\nFeature Importance:")
print(importance)
```

## Case Study: Storm Forecasting System

Build an operational forecasting system:

1. **Data Pipeline**: Ingest real-time lightning data
2. **Feature Engineering**: Create predictive features from recent observations
3. **Model**: Train ensemble of forecasting models
4. **Validation**: Test on historical events
5. **Deployment**: Generate hourly forecasts

### Performance Metrics

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Forecast skill score
- Probability of Detection (POD) for threshold exceedance

## Advanced Topics

### Prophet for Seasonal Forecasting

```python
from prophet import Prophet

# Prepare data for Prophet
prophet_df = pd.DataFrame({
    'ds': hourly_counts.index,
    'y': hourly_counts.values
})

# Fit model
model = Prophet(
    daily_seasonality=True,
    weekly_seasonality=True,
    yearly_seasonality=True
)
model.fit(prophet_df)

# Make future dataframe
future = model.make_future_dataframe(periods=24, freq='H')

# Forecast
forecast = model.predict(future)

# Plot
model.plot(forecast)
model.plot_components(forecast)
```

### Probabilistic Forecasting

```python
# Quantile regression for uncertainty
from sklearn.ensemble import GradientBoostingRegressor

# Train models for different quantiles
quantiles = [0.1, 0.5, 0.9]
models = {}

for q in quantiles:
    model = GradientBoostingRegressor(
        loss='quantile',
        alpha=q,
        n_estimators=100
    )
    model.fit(X_train, y_train)
    models[q] = model

# Predict with uncertainty
predictions = {}
for q, model in models.items():
    predictions[q] = model.predict(X_test)

# Plot prediction intervals
plt.figure(figsize=(12, 6))
plt.plot(y_test.values, label='Actual', color='black')
plt.plot(predictions[0.5], label='Median Forecast', color='blue')
plt.fill_between(
    range(len(y_test)),
    predictions[0.1],
    predictions[0.9],
    alpha=0.3,
    label='80% Prediction Interval'
)
plt.legend()
```

## Datasets Used

- **Historical lightning data**: Multi-year dataset for training
- **Environmental variables**: Temperature, humidity, CAPE, wind shear
- **Verification data**: Independent test set from recent storms

## Homework (Optional)

1. Implement ST-DBSCAN and track storm cells through time
2. Compare ARIMA, Prophet, and ML forecasting performance
3. Incorporate environmental variables into predictions
4. Create a nowcasting system (0-2 hour forecasts)
5. Build an interactive forecast dashboard with uncertainty visualization

## Additional Resources

- [Statsmodels Time Series](https://www.statsmodels.org/stable/tsa.html)
- [Prophet Documentation](https://facebook.github.io/prophet/)
- [Scikit-learn Time Series](https://scikit-learn.org/stable/modules/classes.html#module-sklearn.model_selection)
- [Spatiotemporal Analysis in Python](https://pysal.org/splot/)

## Conclusion

This workshop series has covered:
- Geospatial data fundamentals
- Advanced spatial analysis techniques
- Temporal and spatiotemporal methods
- Forecasting and prediction

Continue exploring these techniques with your own datasets and applications!

[← Back to Workshops](../index.html)
