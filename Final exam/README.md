# 🛍️ Mall Shopper Segmentation - Unsupervised Learning

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Unsupervised-green)
![Clustering](https://img.shields.io/badge/Algorithms-KMeans%20%7C%20Agglomerative%20%7C%20DBSCAN-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)


## 🎥 Video Submission Link

📌 **Practical Exam Video:** [Click here to watch the video](https://drive.google.com/file/d/12-RPgQunJLVzQhoMLlp2HNZGMHLlOnpl/view?usp=sharing)


## 📌 Project Overview

This project performs **Mall Shopper Profiling** using unsupervised learning. The aim is to identify natural customer groups based on mall visitors' **annual income**, **spending score**, **age**, and **gender**.

The project is designed for a retail analytics use case where a mall operations team wants to understand customer behaviour, improve store layouts, plan targeted promotions, and create personalised loyalty rewards.

The notebook covers:

- 📊 Exploratory Data Analysis
- 🧹 Data preprocessing
- 🏷️ Label encoding
- 🛠️ Feature engineering
- ⚖️ Feature scaling
- 🔵 K-Means Clustering
- 🌳 Agglomerative Hierarchical Clustering
- 🔴 DBSCAN Clustering
- 📈 Model evaluation metrics
- 🧑‍💼 Customer persona creation
- 💼 Business recommendations
- 🚀 Model saving and shopper classification function

---

## 🎯 Business Problem

Retail malls such as Phoenix Marketcity or Nexus Malls need to understand different types of shoppers so they can:

- Place premium and budget stores in the right locations
- Send targeted offers to different customer groups
- Improve loyalty programs
- Increase customer engagement
- Identify high-value customer segments
- Understand shoppers who do not clearly fit into any group

Since the dataset does not contain predefined customer labels, **unsupervised learning** is used to discover hidden patterns.

---

## 📁 Dataset Information

Dataset used: **Mall Customer Segmentation Data**

Source: [Kaggle - Customer Segmentation Tutorial in Python](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)

### Dataset Details

| Item | Description |
|---|---|
| Total Records | 200 customers |
| Original Columns | CustomerID, Genre, Age, Annual Income (k$), Spending Score (1-100) |
| Target Variable | No target variable |
| Problem Type | Unsupervised Learning |
| Main Goal | Cluster shoppers into meaningful retail personas |

### Renamed Columns

| Original Column | New Column |
|---|---|
| Genre | Gender |
| Annual Income (k$) | AnnualIncome |
| Spending Score (1-100) | SpendingScore |

---

## 🎥 Video Submission Link

📌 **Practical Exam Video Link:** `PASTE_YOUR_GOOGLE_DRIVE_OR_YOUTUBE_LINK_HERE`

> Replace the placeholder above with your Google Drive or YouTube unlisted video link before final submission.

---

## 📦 Files Included

| File | Description |
|---|---|
| `MallShopperSegmentation_UnsupervisedLearning.ipynb` | Main Jupyter Notebook with full analysis |
| `Mall_Customers.csv` | Dataset file |
| `mall_scaler.pkl` | Saved StandardScaler object |
| `mall_segmentation_model.pkl` | Saved final clustering model |
| `summary_report.md` | Detailed project summary report |
| `requirements.txt` | Required Python libraries |
| `README.md` | Project documentation |
| `graphs/` | Exported graph images from the notebook |

---

## ⚙️ Installation And Setup

### 1. Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/mall-shopper-segmentation-unsupervised-learning.git
cd mall-shopper-segmentation-unsupervised-learning
```

### 2. Install Required Libraries

```bash
pip install -r requirements.txt
```

### 3. Run Notebook

Open and run:

```text
MallShopperSegmentation_UnsupervisedLearning.ipynb
```

---

## 🧰 Libraries Used

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
scipy
plotly
joblib
```

---

## 🧭 Notebook Topics Covered

## 1️⃣ Dataset Loading And EDA

The dataset is loaded using pandas. Column names are cleaned for easier coding. The notebook checks dataset shape, information, first 10 rows, missing values, and gender count.

Important checks:

- Dataset shape
- Data types
- Missing values
- Gender distribution
- First 10 rows

## 2️⃣ Univariate Analysis

Univariate analysis is performed on:

- Age
- AnnualIncome
- SpendingScore
- Gender

Histograms show distribution patterns, boxplots help detect outliers, and the countplot shows gender balance.

## 3️⃣ Bivariate Analysis

Bivariate plots are used to study relationships between two variables:

- AnnualIncome vs SpendingScore
- Age vs SpendingScore by Gender
- Age vs AnnualIncome by Gender

The **AnnualIncome vs SpendingScore** graph is the most important clustering canvas because it visually shows around **5 natural customer groups**.

## 4️⃣ Correlation Analysis

A correlation matrix and heatmap are used to check relationships between numerical features:

- Age
- AnnualIncome
- SpendingScore

The features show weak correlations, meaning each feature provides different information.

## 5️⃣ Gender-Wise Summary

The notebook calculates mean Age, AnnualIncome, and SpendingScore separately for male and female customers. A grouped bar chart is used to compare gender-based differences.

## 6️⃣ Feature Engineering

New columns are created:

- `Gender_enc`
- `IncomeGroup`
- `AgeGroup`
- `SpendingCategory`

These features help make the analysis easier to interpret.

## 7️⃣ Feature Selection

Two feature sets are used:

### Experiment A - 2D Clustering

```text
AnnualIncome, SpendingScore
```

### Experiment B - Multi-Feature Clustering

```text
Age, AnnualIncome, SpendingScore, Gender_enc
```

The 2D feature set gives clearer and more interpretable clusters.

## 8️⃣ Feature Scaling

`StandardScaler` is applied because clustering algorithms use distance calculations. Scaling prevents large-range features from dominating smaller-range features.

## 9️⃣ K-Means Clustering

K-Means is tested for values of `k` from 2 to 10. The Elbow Method and Silhouette Score are used to choose the best number of clusters.

Final choice:

```text
k = 5
```

K-Means creates five clear customer segments and is selected as the final recommended algorithm.

## 🔟 Agglomerative Hierarchical Clustering

Agglomerative clustering is performed using:

- Ward linkage
- Complete linkage
- Average linkage

A dendrogram is used to decide the natural number of clusters. The result supports choosing 5 clusters, similar to K-Means.

## 1️⃣1️⃣ DBSCAN Clustering

DBSCAN is tuned using:

- k-NN distance plot
- Epsilon value
- min_samples
- Grid search

DBSCAN identifies dense customer groups and marks some shoppers as noise. These noise shoppers are not always true outliers; they may be average customers between segments.

## 1️⃣2️⃣ Algorithm Comparison

The algorithms are compared using:

- Silhouette Score
- Davies-Bouldin Index
- Calinski-Harabasz Index
- Noise Percentage

K-Means is recommended because it produces clear, compact, stable, and business-friendly clusters.

## 1️⃣3️⃣ Customer Personas

Each cluster is converted into a business persona:

- Big Spenders
- Careful Spenders
- Young Aspirers
- Budget Shoppers
- Mature Savers

## 1️⃣4️⃣ Deployment

The final scaler and clustering model are saved using `joblib`. A `classify_shopper()` function is created to classify new customers into shopper personas.

---

## 👥 Final Customer Personas

| Persona | Profile | Business Strategy |
|---|---|---|
| 💎 Big Spenders | High income, high spending | Premium lounges, luxury pop-ups, VIP rewards |
| 🧠 Careful Spenders | High income, low spending | Personalised offers, premium trials, exclusive events |
| 🛍️ Young Aspirers | Low income, high spending | Fashion deals, food court offers, youth campaigns |
| 💸 Budget Shoppers | Low income, low spending | Coupons, discount stores, value-for-money campaigns |
| 👨‍👩‍👧 Mature Savers | Medium income, medium spending | Loyalty points, seasonal offers, family bundles |

---

## 📊 Graphs And Visualizations

## 📌 EDA Graphs

### 📈 1. Histograms for Age, Annual Income and Spending Score

This graph shows the distribution of Age, AnnualIncome, and SpendingScore.

![Histograms for Age, AnnualIncome and SpendingScore](graphs/01_histograms_for_age_annualincome_and_spendingscore.png)

### 📦 2. Boxplots to Spot Outliers

Boxplots help check if Age, AnnualIncome, or SpendingScore contain visible outliers.

![Boxplots to help spot outliers](graphs/02_boxplots_to_help_spot_outliers.png)

### 👥 3. Countplot for Gender

This graph shows the number of male and female customers.

![Countplot for Gender](graphs/03_countplot_for_gender.png)

### 🎯 4. Annual Income vs Spending Score

This is the main clustering canvas. It visually shows around five customer groups.

![Annual Income vs Spending Score](graphs/04_the_core_clustering_canvas_annualincome_vs_spendingscore.png)

### 🧑‍🤝‍🧑 5. Age vs Spending Score by Gender

This plot shows spending score across age groups, separated by gender.

![Age vs SpendingScore by Gender](graphs/05_age_vs_spendingscore_coloured_by_gender.png)

### 💰 6. Age vs Annual Income by Gender

This plot compares income and age patterns for male and female customers.

![Age vs AnnualIncome by Gender](graphs/06_age_vs_annualincome_coloured_by_gender.png)

### 🔥 7. Correlation Heatmap

The heatmap shows correlation between numerical variables.

![Correlation Heatmap](graphs/07_correlation_matrix_for_the_numeric_columns.png)

### 📊 8. Gender Summary Bar Chart

This grouped bar chart compares average Age, AnnualIncome, and SpendingScore by gender.

![Gender Summary Bar Chart](graphs/08_show_the_same_summary_as_a_grouped_bar_chart.png)

## 🔵 K-Means Graphs

### 📉 9. Elbow Curve and Silhouette Score

This graph helps select the optimal number of clusters for K-Means.

![Elbow Curve and Silhouette Score](graphs/09_plot_the_elbow_curve_and_the_silhouette_scores_side_by_side.png)

### ⭐ 10. K-Means Clusters with Centroids

This graph shows K-Means clusters using AnnualIncome and SpendingScore. The star markers show cluster centroids.

![K-Means Clusters with Centroids](graphs/10_scatter_plot_of_annualincome_vs_spendingscore_coloured_by_cluster_with.png)

### 📍 11. K-Means: Age vs Spending Score

This graph shows how K-Means cluster labels appear when plotted against Age and SpendingScore.

![K-Means Age vs Spending Score](graphs/11_scatter_plot_of_age_vs_spendingscore_coloured_by_the_same_2d_cluster_l.png)

### 🧬 12. PCA Visualization for Multi-Feature K-Means

PCA reduces multi-feature clustering results into two dimensions for visualization.

![PCA Visualization](graphs/12_for_the_5d_result_use_pca_to_reduce_to_2_components_so_we_can_plot_it.png)

## 🌳 Agglomerative Clustering Graphs

### 🌲 13. Full Agglomerative Dendrogram

The full dendrogram shows hierarchical merging of all customers.

![Agglomerative Dendrogram](graphs/13_build_the_linkage_matrix_using_ward_s_method.png)

### ✂️ 14. Truncated Agglomerative Dendrogram

The truncated dendrogram gives a cleaner view of the final cluster merging structure.

![Truncated Agglomerative Dendrogram](graphs/14_build_the_linkage_matrix_using_ward_s_method.png)

### 🟢 15. Agglomerative Clusters: Income vs Spending

This graph shows hierarchical clusters using AnnualIncome and SpendingScore.

![Agglomerative Income vs Spending](graphs/15_scatter_plot_annualincome_vs_spendingscore_coloured_by_hierarchical_cl.png)

### 🟣 16. Agglomerative Clusters: Age vs Spending

This graph shows hierarchical cluster labels against Age and SpendingScore.

![Agglomerative Age vs Spending](graphs/16_scatter_plot_age_vs_spendingscore_coloured_by_hierarchical_cluster.png)

## 🔴 DBSCAN Graphs

### 📏 17. k-NN Distance Plot for DBSCAN Epsilon

This graph is used to choose the epsilon value for DBSCAN.

![k-NN Distance Plot](graphs/17_fit_a_nearest_neighbours_model_with_k_4_matches_min_samples_we_will_us.png)

### 🔥 18. DBSCAN Grid Search Heatmap

This heatmap compares DBSCAN parameter combinations using silhouette score.

![DBSCAN Grid Search Heatmap](graphs/18_plot_a_heatmap_of_eps_vs_min_samples_coloured_by_silhouette_score.png)

### ❌ 19. DBSCAN Clusters: Income vs Spending

This graph shows DBSCAN clusters and noise points using AnnualIncome and SpendingScore.

![DBSCAN Income vs Spending](graphs/19_scatter_plot_annualincome_vs_spendingscore_coloured_by_dbscan_cluster.png)

### ➕ 20. DBSCAN Clusters: Age vs Spending

This graph shows DBSCAN cluster labels against Age and SpendingScore.

![DBSCAN Age vs Spending](graphs/20_scatter_plot_age_vs_spendingscore_coloured_by_dbscan_cluster.png)

---

## 🏆 Final Algorithm Recommendation

✅ **Recommended Algorithm: K-Means Clustering**

✅ **Recommended Number of Clusters: 5**

K-Means is selected as the final model because:

- It gives clear and compact clusters.
- The result is easy to visualize.
- It matches the natural groups seen in the scatter plot.
- It is stable across multiple runs.
- The cluster profiles are easy to convert into business personas.

Agglomerative Clustering gives similar results, which supports the K-Means solution. DBSCAN is useful for identifying noise shoppers but is not the best final model for this clean dataset.

---

## 💼 Business Recommendations

- 💎 **Big Spenders:** Create premium brand zones, luxury pop-ups, and VIP lounges.
- 🧠 **Careful Spenders:** Use personalised offers and exclusive events to increase engagement.
- 🛍️ **Young Aspirers:** Promote fashion, entertainment, and lifestyle offers.
- 💸 **Budget Shoppers:** Provide coupons, discount campaigns, and value store promotions.
- 👨‍👩‍👧 **Mature Savers:** Use family bundles, seasonal campaigns, and loyalty points.

---

## 🚀 Future Improvements

More accurate segmentation can be created by collecting:

- Purchase category history
- Store visit frequency
- Loyalty app behaviour
- Coupon redemption history
- Festival season shopping data
- Time spent inside the mall
- Transaction-level purchase data

---

## 📌 GitHub Repository Name

Recommended repository name:

```text
mall-shopper-segmentation-unsupervised-learning
```

---

## ✅ Final Submission Checklist

- ✅ Notebook runs from top to bottom
- ✅ EDA completed
- ✅ Feature engineering completed
- ✅ K-Means clustering completed
- ✅ Agglomerative clustering completed
- ✅ DBSCAN clustering completed
- ✅ Graphs added
- ✅ Customer personas created
- ✅ Business recommendation added
- ✅ Model and scaler saved
- ✅ `summary_report.md` added
- ✅ `requirements.txt` added
- ✅ README with video link section added

---

## 👨‍💻 Author

Created for Practical Exam - Unsupervised Learning Set B.
