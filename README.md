# 🚦 Traffic Pattern Analysis Using Unsupervised Learning

## 📌 Project Overview

Traffic Pattern Analysis Using Unsupervised Learning is a Machine Learning project that analyzes traffic observations from five Indian cities: Mumbai, Nagpur, Nashik, Pune, and Thane.

The project uses clustering algorithms to identify different traffic patterns based on vehicle count, average speed, accidents, and traffic violations.

It also explores congestion classification, compares multiple clustering algorithms, and investigates whether traffic patterns change over different days, months, and seasons.

The main objective is to discover meaningful patterns in traffic data and understand the factors that influence traffic congestion.

## 🎯 Objectives

- Analyze traffic data from five Indian cities.
- Perform Exploratory Data Analysis (EDA).
- Apply feature scaling using StandardScaler.
- Implement K-Means clustering.
- Determine the optimal number of clusters using the Elbow Method and Silhouette Score.
- Compare K-Means, Gaussian Mixture, Agglomerative Clustering, and DBSCAN.
- Analyze cluster characteristics and distributions.
- Explore congestion classification and identify target leakage.
- Investigate traffic patterns across days, months, and seasons.

## 📊 Dataset Information

The project uses a traffic dataset containing **1,200 observations and 9 original columns**.

**Cities included:**
- Mumbai
- Nagpur
- Nashik
- Pune
- Thane

**Important dataset features:**

| Feature | Description |
|---|---|
| City | Name of the city |
| Area | Traffic observation area |
| Date | Date of observation |
| Vehicle_Type | Type of vehicle |
| Vehicle_Count | Number of vehicles |
| Avg_Speed_kmph | Average traffic speed |
| Accidents | Number of accidents |
| Traffic_Violations | Number of traffic violations |
| Congestion_Level | Low, Medium, or High congestion |

The dataset contains no missing values or duplicate records.

## 🛠️ Technologies Used

- **Python** – Programming language
- **Jupyter Notebook** – Development environment
- **Pandas** – Data manipulation and analysis
- **NumPy** – Numerical operations
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical visualization
- **Scikit-learn** – Machine Learning algorithms
- **SciPy** – Statistical analysis

## ⚙️ Project Workflow

### 1. Data Loading and Exploration
- Load the traffic dataset using Pandas.
- Inspect dataset structure and data types.
- Check missing values, duplicates, and outliers.
- Analyze numerical and categorical features.

### 2. Exploratory Data Analysis (EDA)
- Visualize feature distributions.
- Generate correlation heatmaps.
- Compare traffic conditions across cities.
- Analyze vehicle count and average speed.
- Study congestion levels.

### 3. Feature Selection and Scaling

Four numerical features were selected for the main clustering model:

- Vehicle_Count
- Avg_Speed_kmph
- Accidents
- Traffic_Violations

StandardScaler was applied to standardize the features so that variables with larger numerical ranges would not dominate the clustering process.

### 4. K-Means Clustering

K-Means was implemented to group similar traffic observations.

The Elbow Method and Silhouette Score were used to evaluate different cluster counts.

**Selected configuration:**
- Number of clusters (K): 8
- Random State: 42
- N_Init: 10
- Silhouette Score: 0.2376

### 5. Clustering Algorithm Comparison

Four algorithms were evaluated:

1. K-Means
2. Gaussian Mixture Model (GMM)
3. Agglomerative Clustering
4. DBSCAN

The algorithms were compared using:
- Silhouette Score
- Davies-Bouldin Index
- Calinski-Harabasz Index

K-Means performed best on the four numerical baseline features.

### 6. Congestion Classification

Supervised learning algorithms were also evaluated to classify traffic congestion.

Algorithms included:
- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting

Two feature settings were compared:
- With Vehicle_Count
- Without Vehicle_Count

This experiment identified target leakage because Congestion_Level is determined by Vehicle_Count in the dataset.

Without Vehicle_Count, the models did not demonstrate reliable predictive performance.

### 7. Time-Based Traffic Analysis

Traffic patterns were investigated using:
- Day of the week
- Month
- Season (Winter, Summer, Monsoon, and Post-monsoon)

Statistical tests, city-month clustering, daily clustering, and separate seasonal clustering were performed.

No meaningful time-based structure was established in the dataset.

## 📈 Results and Findings

| Parameter | Result |
|---|---|
| Total observations | 1,200 |
| Cities | 5 |
| Selected clusters | 8 |
| Silhouette Score | 0.2376 |
| Cluster 0 | 146 observations |
| Cluster 1 | 162 observations |
| Cluster 2 | 152 observations |
| Cluster 3 | 139 observations |
| Cluster 4 | 150 observations |
| Cluster 5 | 160 observations |
| Cluster 6 | 154 observations |
| Cluster 7 | 137 observations |

### Important Findings

- K-Means performed better than the other tested clustering algorithms on the baseline features.
- The four high-volume clusters showed approximately 67–81% high congestion.
- The four lower-volume clusters showed 9% or less high congestion.
- The Silhouette Score of 0.2376 indicates modest cluster separation.
- Adding city, vehicle type, and calendar features reduced clustering performance.
- Congestion classification using Vehicle_Count produced misleadingly high accuracy due to target leakage.
- Time-based clustering did not reveal meaningful seasonal or weekly traffic patterns.

## 📂 Project Structure

```text
Traffic-Pattern-Analysis/
│
├── ML_Project_CCE5.ipynb
│
├── Traffic_dataset.csv
│
├── deck_figures/
│   ├── 01_elbow_method.png
│   ├── 02_silhouette_scores.png
│   ├── 03_cluster_size_distribution.png
│   ├── 04_cluster_characteristics_heatmap.png
│   ├── 05_city_average_vehicle_count.png
│   ├── 06_city_average_speed.png
│   ├── 07_city_cluster_distribution_heatmap.png
│   └── 08_cluster_scatter.png
│
└── README.md
```

## 🚀 How to Run the Project

**Step 1: Clone the repository**

```bash
git clone <your-repository-link>
```

**Step 2: Navigate to the project folder**

```bash
cd Traffic-Pattern-Analysis
```

**Step 3: Install required libraries**

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy jupyter
```

**Step 4: Add the dataset**

Place the traffic dataset CSV file in the same directory as the notebook.

The notebook checks for these filenames:

- Traffic_dataset.csv
- traffic_dataset.csv
- Traffic dataset.csv

**Step 5: Open Jupyter Notebook**

```bash
jupyter notebook
```

**Step 6: Run the notebook**

Open `ML_Project_CCE5.ipynb` and execute the cells sequentially.

## 🔮 Future Scope

- Use real-time traffic data from sensors and GPS devices.
- Include hourly timestamps to identify rush-hour traffic patterns.
- Incorporate weather conditions and road capacity.
- Explore advanced clustering techniques.
- Collect more reliable and larger datasets.
- Develop time-series models for traffic volume forecasting.
- Build a traffic analysis dashboard for better visualization.

## 👨‍💻 Project Team

**Department:** Artificial Intelligence and Data Science

**College:** Dr. D. Y. Patil College of Engineering, Akurdi, Pune

| Name | Roll Number |
|---|---|
| Mayur Pardhi | TY2526AIDC216 |
| Suyash Pimpalshende | TY2526AIDC240 |
| Uday Pachpor | TY2526AIDC202 |

## 📚 References

- Lloyd, S. P. – Least Squares Quantization in PCM (1982).
- Scikit-learn Documentation – Clustering.
- Scikit-learn Documentation – StandardScaler.
- Scikit-learn Documentation – Model Evaluation.
- Traffic Dataset – GitHub dataset source.

---

**Note:** This project is an exploratory machine learning study. The clusters describe similarities in the available observations; they do not directly predict or control real-world traffic conditions.
