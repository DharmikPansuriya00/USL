# Mall Shopper Segmentation - Unsupervised Learning

## Project Overview

This project uses the Mall Customer Segmentation dataset to identify different shopper groups using unsupervised learning. The goal is to help a mall business understand customer spending behaviour and create useful retail strategies for each customer segment.

The project includes Exploratory Data Analysis, feature engineering, scaling, K-Means Clustering, Agglomerative Hierarchical Clustering, DBSCAN, algorithm comparison, customer persona creation, and a final deployment-style prediction function.

## Dataset

- Dataset: Mall Customer Segmentation Data
- Source: [Kaggle - Customer Segmentation Tutorial in Python](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)
- Rows: 200 customers
- Main columns: `Gender`, `Age`, `AnnualIncome`, `SpendingScore`

## Video Submission Link

Video link: `PASTE_YOUR_GOOGLE_DRIVE_OR_YOUTUBE_LINK_HERE`

## Files Included

- `MallShopperSegmentation_UnsupervisedLearning.ipynb` - final practical notebook
- `Mall_Customers.csv` - dataset
- `mall_scaler.pkl` - saved StandardScaler
- `mall_segmentation_model.pkl` - saved K-Means model
- `summary_report.md` - short project report
- `requirements.txt` - required Python libraries
- `README.md` - project documentation

## How To Run

Install required libraries:

```bash
pip install -r requirements.txt
```

Then open the notebook and run all cells from top to bottom:

```text
MallShopperSegmentation_UnsupervisedLearning.ipynb
```

## Methods Used

- Exploratory Data Analysis
- Label Encoding
- Feature Engineering
- StandardScaler
- K-Means Clustering
- Elbow Method
- Silhouette Score
- Agglomerative Hierarchical Clustering
- Dendrogram Analysis
- DBSCAN
- k-NN Distance Plot
- Davies-Bouldin Index
- Calinski-Harabasz Index
- PCA Visualization
- Joblib Model Saving

## Final Customer Personas

- **Big Spenders** - High income and high spending customers. They are suitable for premium brand offers, luxury pop-ups, and VIP loyalty rewards.
- **Careful Spenders** - High income but low spending customers. They may need personalised discounts, exclusive events, or better engagement.
- **Young Aspirers** - Lower income but high spending customers. They are suitable for fashion, entertainment, food court, and lifestyle promotions.
- **Budget Shoppers** - Low income and low spending customers. They respond better to value stores, discount coupons, and budget-friendly campaigns.
- **Mature Savers** - Medium income and medium spending customers. They are balanced shoppers who can be targeted with seasonal offers and loyalty points.

## Graphs And Visualizations

### 1. Histograms for Age, Annual Income and Spending Score

![Histograms for Age, AnnualIncome and SpendingScore](graphs/01_histograms_for_age_annualincome_and_spendingscore.png)

### 2. Boxplots to Spot Outliers

![Boxplots to help spot outliers](graphs/02_boxplots_to_help_spot_outliers.png)

### 3. Countplot for Gender

![Countplot for Gender](graphs/03_countplot_for_gender.png)

### 4. Annual Income vs Spending Score

![Annual Income vs Spending Score](graphs/04_the_core_clustering_canvas_annualincome_vs_spendingscore.png)

### 5. Age vs Spending Score by Gender

![Age vs SpendingScore by Gender](graphs/05_age_vs_spendingscore_coloured_by_gender.png)

### 6. Age vs Annual Income by Gender

![Age vs AnnualIncome by Gender](graphs/06_age_vs_annualincome_coloured_by_gender.png)

### 7. Correlation Heatmap

![Correlation Heatmap](graphs/07_correlation_matrix_for_the_numeric_columns.png)

### 8. Gender Summary Bar Chart

![Gender Summary Bar Chart](graphs/08_show_the_same_summary_as_a_grouped_bar_chart.png)

### 9. Elbow Curve and Silhouette Score

![Elbow Curve and Silhouette Score](graphs/09_plot_the_elbow_curve_and_the_silhouette_scores_side_by_side.png)

### 10. K-Means Clusters with Centroids

![K-Means Clusters with Centroids](graphs/10_scatter_plot_of_annualincome_vs_spendingscore_coloured_by_cluster_with.png)

### 11. K-Means: Age vs Spending Score

![K-Means Age vs Spending Score](graphs/11_scatter_plot_of_age_vs_spendingscore_coloured_by_the_same_2d_cluster_l.png)

### 12. PCA Visualization for Multi-Feature K-Means

![PCA Visualization](graphs/12_for_the_5d_result_use_pca_to_reduce_to_2_components_so_we_can_plot_it.png)

### 13. Full Agglomerative Dendrogram

![Agglomerative Dendrogram](graphs/13_build_the_linkage_matrix_using_ward_s_method.png)

### 14. Truncated Agglomerative Dendrogram

![Truncated Agglomerative Dendrogram](graphs/14_build_the_linkage_matrix_using_ward_s_method.png)

### 15. Agglomerative Clusters: Income vs Spending

![Agglomerative Income vs Spending](graphs/15_scatter_plot_annualincome_vs_spendingscore_coloured_by_hierarchical_cl.png)

### 16. Agglomerative Clusters: Age vs Spending

![Agglomerative Age vs Spending](graphs/16_scatter_plot_age_vs_spendingscore_coloured_by_hierarchical_cluster.png)

### 17. k-NN Distance Plot for DBSCAN Epsilon

![k-NN Distance Plot](graphs/17_fit_a_nearest_neighbours_model_with_k_4_matches_min_samples_we_will_us.png)

### 18. DBSCAN Grid Search Heatmap

![DBSCAN Grid Search Heatmap](graphs/18_plot_a_heatmap_of_eps_vs_min_samples_coloured_by_silhouette_score.png)

### 19. DBSCAN Clusters: Income vs Spending

![DBSCAN Income vs Spending](graphs/19_scatter_plot_annualincome_vs_spendingscore_coloured_by_dbscan_cluster.png)

### 20. DBSCAN Clusters: Age vs Spending

![DBSCAN Age vs Spending](graphs/20_scatter_plot_age_vs_spendingscore_coloured_by_dbscan_cluster.png)

## Algorithm Recommendation

K-Means with `k = 5` is recommended as the final model because the Annual Income vs Spending Score plot clearly shows five natural customer groups. K-Means also creates easy-to-understand business segments and works well on this small, clean dataset. Agglomerative clustering gives a similar result, while DBSCAN is useful for identifying noise or borderline shoppers.

## Business Recommendation

The mall should use the five customer personas to plan targeted marketing and store placement. Premium offers should be aimed at Big Spenders, discount campaigns should target Budget Shoppers, and personalised engagement should be used for Careful Spenders. More behavioural data such as purchase history, visit frequency, loyalty app usage, and coupon redemption would improve future segmentation.

## GitHub Repository Name

Recommended repository name:

```text
mall-shopper-segmentation-unsupervised-learning
```
