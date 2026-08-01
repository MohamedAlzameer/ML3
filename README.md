# 🏠 Geographic Consumer Clustering using K-Means

A Machine Learning project that applies the **K-Means Clustering** algorithm to segment real estate consumers based on their **geographic location** and **property purchasing profile**. The resulting clusters help identify similar consumer groups, enabling better market analysis and business decision-making.

---

## 📖 Project Overview

Understanding customer behavior is essential in the real estate industry. This project uses **unsupervised machine learning** to discover natural groupings of consumers without predefined labels.

Using property location and purchasing characteristics, the model identifies clusters of consumers with similar patterns. These insights can support:

- Regional market segmentation
- Targeted marketing campaigns
- Customer profiling
- Property pricing strategies
- Investment planning

---

## 🎯 Objectives

- Perform geographic consumer segmentation using K-Means clustering.
- Standardize numerical features before clustering.
- Determine the optimal number of clusters using the Elbow Method.
- Visualize clustered properties geographically.
- Analyze consumer purchasing patterns across different regions.

---

# 📂 Project Structure

```
Geographic-Consumer-Clustering-KMeans/
│
├── Geographic_Consumer_Clustering_KMeans.ipynb
├── real_estate_consumer_data.csv
├── elbow_method.png
├── geographic_clusters.png
├── README.md
├── requirements.txt
└── LICENSE
```

---

# 📊 Dataset

The dataset contains **20 real estate property records** with the following attributes.

| Feature | Description |
|----------|-------------|
| PropertyID | Unique property identifier |
| Latitude | Geographic latitude |
| Longitude | Geographic longitude |
| Price | Property price |
| Area_sqft | Property size in square feet |
| Bedrooms | Number of bedrooms |
| ConsumerIncome | Buyer's annual income |

---

# ⚙️ Methodology

## Step 1 – Load Dataset

The dataset is loaded into a Pandas DataFrame for preprocessing and analysis.

---

## Step 2 – Feature Selection

The following numerical features are used for clustering:

- Latitude
- Longitude
- Price
- Area_sqft
- Bedrooms
- ConsumerIncome

---

## Step 3 – Data Scaling

Since the selected features have different numerical ranges, they are standardized using **StandardScaler**.

Benefits of scaling:

- Prevents large-valued features from dominating distance calculations.
- Improves clustering performance.
- Ensures equal contribution of each feature.

---

## Step 4 – Elbow Method

The Elbow Method is applied by fitting K-Means models for values of **k = 1 to 10**.

The **Within Cluster Sum of Squares (WCSS)** is plotted to determine the optimal number of clusters.

**Selected Number of Clusters:**

```
k = 3
```

---

## Step 5 – K-Means Clustering

The final K-Means model is trained with:

```python
n_clusters = 3
```

Each property is assigned to one of three cluster labels:

- Cluster 0
- Cluster 1
- Cluster 2

---

## Step 6 – Visualization

The clustered properties are visualized using a scatter plot where:

- X-axis → Longitude
- Y-axis → Latitude
- Different colors represent different clusters.

This visualization clearly highlights geographic segmentation.

---

# 📈 Results

The clustering process successfully divided the properties into **three distinct consumer segments**.

### Key Findings

- Three meaningful geographic clusters were identified.
- Similar property characteristics were grouped together.
- Geographic distribution of consumers became visually distinguishable.
- The model can support marketing and investment decisions.

---

# 🛠 Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

---

# 📦 Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/Geographic-Consumer-Clustering-KMeans.git
```

Move into the project directory:

```bash
cd Geographic-Consumer-Clustering-KMeans
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Or install manually:

```bash
pip install pandas numpy matplotlib scikit-learn
```

---

# ▶️ How to Run

1. Open the notebook in Jupyter Notebook, VS Code, or Google Colab.
2. Ensure `real_estate_consumer_data.csv` is located in the project directory.
3. Run all notebook cells sequentially.
4. The notebook will:
   - Load the dataset
   - Standardize numerical features
   - Apply the Elbow Method
   - Train the K-Means model
   - Assign cluster labels
   - Generate visualization plots

---

# 📷 Output Files

| File | Description |
|------|-------------|
| elbow_method.png | Elbow curve showing the optimal value of K |
| geographic_clusters.png | Geographic visualization of clustered properties |

---

# 🚀 Future Improvements

- Validate clustering using the Silhouette Score.
- Generate cluster-wise statistical summaries.
- Visualize clusters on interactive maps using Folium or Plotly.
- Compare K-Means with DBSCAN and Hierarchical Clustering.
- Develop an interactive dashboard for real-time visualization.

---

# 📄 Requirements

```
Python >= 3.8

pandas
numpy
matplotlib
scikit-learn
```

---

# 👨‍💻 Author

**Mohamed Al Zameer**

AI Developer | Web Developer | Machine Learning Enthusiast

GitHub: https://github.com/yourusername

LinkedIn: https://linkedin.com/in/yourprofile

---

# ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub.
