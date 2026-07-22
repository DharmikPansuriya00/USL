# Mall Shopper Segmentation - Summary Report

## 1. Business Problem

The objective of this project is to help a mall retail operations team understand different types of shoppers based on their income and spending behaviour. A large mall such as Phoenix Marketcity or Nexus Malls needs this kind of customer segmentation to plan store placement, promotional campaigns, loyalty rewards, and personalised offers.

The main business question is: **Can we group mall customers into meaningful shopper personas using unsupervised learning?** Since there is no target label in the dataset, clustering algorithms are used to discover natural patterns in the data.

## 2. Dataset Overview

The project uses the Mall Customer Segmentation dataset from Kaggle. The dataset contains information about 200 mall customers. The original columns include:

- `CustomerID`
- `Genre`
- `Age`
- `Annual Income (k$)`
- `Spending Score (1-100)`

For better readability, the columns were renamed:

- `Genre` to `Gender`
- `Annual Income (k$)` to `AnnualIncome`
- `Spending Score (1-100)` to `SpendingScore`

The dataset is small and clean, with no major missing value problem. This means the main focus of the project is not data cleaning, but feature engineering, clustering, evaluation, and business interpretation.

## 3. Exploratory Data Analysis

The EDA showed that the dataset contains both male and female customers, with the gender distribution being reasonably balanced. Histograms were used to understand the distribution of Age, AnnualIncome, and SpendingScore. Boxplots were used to check visible outliers.

The most important visual insight came from the scatter plot of **AnnualIncome vs SpendingScore**. This plot showed around five natural customer groups:

- Low income, low spending
- Low income, high spending
- Medium income, medium spending
- High income, low spending
- High income, high spending

This early visual pattern suggested that **5 clusters** would likely be a good choice for K-Means and Hierarchical Clustering.

## 4. Feature Engineering

Several new features were created to improve analysis and interpretation:

- `Gender_enc`: Label encoded version of Gender, where Female and Male are converted into numeric values.
- `IncomeGroup`: AnnualIncome divided into Low, Medium, and High groups using equal-frequency binning.
- `AgeGroup`: Age divided into Young, Adult, Middle-Aged, and Senior categories.
- `SpendingCategory`: SpendingScore divided into Low, Medium, and High categories.

These engineered features helped in understanding the customer profile, but clustering was mainly performed using numerical features.

## 5. Feature Sets Used For Clustering

Two feature sets were prepared:

### 2D Feature Set

```text
AnnualIncome, SpendingScore
```

This feature set was used because income and spending score directly represent customer purchasing behaviour. It also gives a clear 2D visualization of customer groups.

### 4D Feature Set

```text
Age, AnnualIncome, SpendingScore, Gender_enc
```

This feature set was tested to check whether adding demographic information improves clustering. Although it gives more information, the clusters were less clearly separated compared to the 2D feature set.

All features were scaled using `StandardScaler` because clustering algorithms are distance-based. Without scaling, a feature with a larger numerical range could dominate the clustering result.

## 6. Algorithms Applied

Three unsupervised learning algorithms were used:

### K-Means Clustering

K-Means was tested for different values of `k` from 2 to 10. The Elbow Method and Silhouette Score were used to select the optimal number of clusters. The elbow curve and visual scatter plot both supported choosing:

```text
k = 5
```

K-Means produced clear and interpretable clusters, making it the best model for business use in this project.

### Agglomerative Hierarchical Clustering

Agglomerative Clustering was performed using Ward, Complete, and Average linkage methods. A dendrogram was used to visually inspect the natural number of clusters. Cutting the dendrogram at a suitable distance gave 5 clusters, matching the K-Means result.

Ward linkage performed well because it minimizes within-cluster variance, which makes its output similar to K-Means on this clean dataset.

### DBSCAN

DBSCAN was applied using a k-NN distance plot to choose epsilon. A grid search was also performed using different `eps` and `min_samples` values. DBSCAN identified dense groups and marked some customers as noise.

In this dataset, DBSCAN was useful for detecting borderline shoppers, but it was not the best final segmentation model because the dataset has clean, compact groups that are better handled by K-Means.

## 7. Algorithm Comparison

The algorithms were compared using internal clustering metrics:

- **Silhouette Score**: Higher is better.
- **Davies-Bouldin Index**: Lower is better.
- **Calinski-Harabasz Index**: Higher is better.
- **Noise Percentage**: Relevant mainly for DBSCAN.

Based on the comparison, K-Means was selected as the final recommended algorithm because it produced clear, compact, and easy-to-explain customer groups. Agglomerative Clustering gave similar results, while DBSCAN was less suitable as the final model because it may mark some normal borderline customers as noise.

## 8. Final Shopper Personas

Five customer personas were created from the K-Means cluster profiles:

### Big Spenders

These customers have high annual income and high spending scores. They are premium shoppers and are likely to respond well to luxury brands, exclusive product launches, VIP lounges, and premium loyalty rewards.

### Careful Spenders

These customers have high annual income but low spending scores. They have the ability to spend but may not be highly engaged with the current mall offerings. Personalised offers, premium trials, and exclusive shopping events can help convert them into more active shoppers.

### Young Aspirers

These customers have lower income but high spending scores. They may spend more on fashion, entertainment, food, and lifestyle purchases. Trend-based promotions, student-friendly offers, and youth-focused campaigns are suitable for this group.

### Budget Shoppers

These customers have low income and low spending scores. They are price-sensitive and are likely to respond to discount campaigns, value-for-money stores, coupons, and festive offers.

### Mature Savers

These customers have moderate income and moderate spending scores. They represent balanced shoppers who spend steadily but not heavily. Loyalty points, family offers, and seasonal promotions are suitable for them.

## 9. Business Recommendation

K-Means with `k = 5` should be used as the final clustering model for this project. It provides simple, meaningful, and business-friendly customer segments. The mall can use these segments to design better store placement, marketing campaigns, app-based offers, and loyalty rewards.

Recommended strategies:

- Place premium stores and luxury pop-ups near areas visited by Big Spenders.
- Use personalised campaigns to engage Careful Spenders.
- Promote fashion, food, and entertainment offers to Young Aspirers.
- Provide coupons and value offers for Budget Shoppers.
- Use loyalty points and family offers for Mature Savers.

## 10. Future Improvements

The current dataset contains only limited demographic and spending information. Better segmentation could be achieved by collecting more behavioural data, such as:

- Store visit frequency
- Purchase category history
- Loyalty app activity
- Coupon usage
- Festival season shopping behaviour
- Footfall sensor data
- Time spent inside the mall
- Transaction-level purchase data

With this additional data, the mall could build a real-time customer persona system that recommends offers and promotions through a mobile app.

## 11. Conclusion

This project successfully applies unsupervised learning to identify meaningful mall shopper segments. K-Means gives the most practical and interpretable result, Agglomerative Clustering supports the same customer grouping pattern, and DBSCAN helps identify shoppers who do not clearly belong to dense groups. The final customer personas can help the mall make better business decisions related to marketing, layout planning, and customer engagement.
