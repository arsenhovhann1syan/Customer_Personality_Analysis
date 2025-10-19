# 🛒 Customer Segmentation: K-Means Optimization with PCA

## 🚀 Project Goal

To segment customers based on purchasing behavior and demographics using Unsupervised Learning, providing actionable profiles for targeted marketing campaigns.

## ✨ Key Achievements

This project successfully implemented a robust $K$-Means clustering model, with the following highlights:

| Category | Method Used | Impact / Result |
| :--- | :--- | :--- |
| **Feature Engineering** | **SQL Queries (pandasql)** | Created key metrics like `TotalSpend`, `AcceptanceRate`, and various spending ratios. |
| **Data Cleaning** | **IQR** Outlier Removal & Group-based Mean Imputation. | Ensured data quality for accurate distance calculation. |
| **Optimization** | **Principal Component Analysis (PCA)** | Applied PCA (N=4) to denoise the feature space, significantly improving the clustering metrics (Silhouette Score: **[Insert PCA Score]**). |
| **Profiling** | **SQL Aggregation on Non-Scaled Data** | Generated two distinct, highly interpretable customer profiles for direct marketing application. |

## 💰 Final Business Segments (K=2)

The two derived segments are clearly differentiated by income and spending:

| Cluster | Avg. Annual Income | Avg. Total Spend | Recommended Strategy |
| :--- | :--- | :--- | :--- |
| **High-Value Patrons** | $**[Insert Cluster 0 Avg Income]**$ | $**[Insert Cluster 0 Avg Spend]**$ | **Focus on Retention & Premium Upsell.** |
| **Value/Family Focus** | $**[Insert Cluster 1 Avg Income]**$ | $**[Insert Cluster 1 Avg Spend]**$ | **Focus on Engagement & Cost-Efficient Campaigns.** |

---

## 💻 Tech Stack & Dependencies

* **Language:** Python 3.x
* **Core Libraries:** `scikit-learn`, `pandas`, `pandasql`, `matplotlib`, `seaborn`
* **Methodology:** K-Means Clustering, PCA, $SQL$ for Data Manipulation.

---
**[Link to the Jupyter Notebook (customer_segmentation.ipynb)]**
