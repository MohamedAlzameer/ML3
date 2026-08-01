# Geographic Consumer Clustering (K-Means)

Segments real estate consumers into groups based on geographic location and
purchasing profile, using K-Means clustering.

## Overview

This project applies K-Means clustering to a real estate consumer dataset in
order to identify natural groupings ("clusters") of buyers based on where
they are located and what kind of property they buy. The output can be used
for regional market segmentation, targeted marketing, or pricing strategy.

## Files

| File | Description |
|---|---|
| `Geographic_Consumer_Clustering_KMeans.ipynb` | Main Jupyter/Colab notebook containing the full analysis |
| `real_estate_consumer_data.csv` | Input dataset (20 property records) |
| `elbow_method.png` | Elbow method plot used to choose the number of clusters |
| `geographic_clusters.png` | Final scatter plot of clustered properties by lat/long |

## Dataset

`real_estate_consumer_data.csv` contains 20 rows with the following columns:

| Column | Description |
|---|---|
| `PropertyID` | Unique identifier for the property |
| `Latitude` | Property latitude |
| `Longitude` | Property longitude |
| `Price` | Property price (currency units) |
| `Area_sqft` | Property area in square feet |
| `Bedrooms` | Number of bedrooms |
| `ConsumerIncome` | Income of the associated consumer/buyer |

## Methodology

1. **Load data** — read the CSV into a pandas DataFrame.
2. **Feature selection** — use `Latitude`, `Longitude`, `Price`, `Area_sqft`,
   `Bedrooms`, and `ConsumerIncome` as clustering features.
3. **Scaling** — standardize features with `StandardScaler` so that no single
   feature (e.g. `Price`, which has a much larger scale) dominates the
   distance calculation.
4. **Elbow method** — fit K-Means for `k = 1` to `10` and plot the
   within-cluster sum of squares (WCSS) to identify the optimal number of
   clusters (`elbow_method.png`). The curve flattens noticeably after
   `k = 3`, so `k = 3` is chosen.
5. **Final clustering** — fit K-Means with `n_clusters=3` and assign a
   `Cluster` label (0, 1, 2) to each property.
6. **Visualization** — plot the properties by longitude/latitude, colored by
   cluster (`geographic_clusters.png`), showing three distinct geographic
   groupings.

## Requirements

```
python >= 3.8
pandas
numpy
matplotlib
scikit-learn
```

Install with:

```bash
pip install pandas numpy matplotlib scikit-learn
```

## How to Run

1. Place `real_estate_consumer_data.csv` in the same directory as the
   notebook.
2. Open `Geographic_Consumer_Clustering_KMeans.ipynb` in Jupyter, VS Code, or
   Google Colab.
3. Run all cells in order. The notebook will:
   - Load and inspect the data
   - Scale the features
   - Generate the elbow plot
   - Fit the final K-Means model (`k=3`)
   - Add a `Cluster` column to the DataFrame
   - Plot the geographic cluster visualization

## Results

- **Optimal clusters:** 3 (chosen via the elbow method)
- **Output:** Each property is assigned to one of 3 clusters representing
  distinct geographic/economic segments (e.g. lower-income southwestern
  properties, mid-range central properties, and higher-income northeastern
  properties, based on the visualized pattern).

## Possible Next Steps

- Use silhouette score to validate the choice of `k` alongside the elbow
  method.
- Add cluster-level summary statistics (average price, income, area per
  cluster).
- Overlay clusters on an actual map (e.g. with `folium` or `plotly`) instead
  of a plain lat/long scatter plot.
- Test alternative clustering algorithms (DBSCAN, hierarchical clustering)
  for comparison.
