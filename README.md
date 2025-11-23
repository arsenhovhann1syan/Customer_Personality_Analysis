# Marketing Campaign Customer Segmentation (K-Means Clustering)

## Project Overview
This project performs **customer segmentation** on a marketing campaign dataset using **K-Means clustering**. The goal is to identify distinct customer segments based on **Income** and **Total Spending**, and provide actionable business strategies for each segment.

- **Dataset:** `marketing_campaign.csv`  
- **Primary Features Used:** `Income`, `TotalSpend`  
- **Number of Clusters:** 2 (Optimized using business understanding and silhouette scores)  

## Technologies & Libraries
- Python 3.x  
- Pandas, NumPy  
- Scikit-learn (KMeans, StandardScaler, silhouette_score, davies_bouldin_score)  
- Matplotlib & Seaborn  
- SciPy (ANOVA for statistical significance)  
- Logging for workflow tracking  

## Data Cleaning & Feature Engineering
- Converted `Income` to numeric and imputed missing values based on `Education` groups.  
- Converted `Dt_Customer` to datetime.  
- Calculated derived features:  
  - `Age` = Current Year - Year_Birth  
  - `TotalSpend` = sum of all Mnt* columns  
  - `FamilySize` = Kidhome + Teenhome  
  - `TotalAccepted` = sum of all AcceptedCmp* columns  
- Cleaned and grouped `Marital_Status` into `Living_Status` (`Single` vs `Partner`)  
- Removed extreme outliers:  
  - `Year_Birth < 1945`  
  - `Income > 200,000`  

## Clustering
- **Scaling:** StandardScaler for `Income` and `TotalSpend`.  
- **K-Means Clustering:** K=2  
- **Evaluation Metrics:**  
  - Silhouette Score: 0.589 → reasonable separation  
  - Davies-Bouldin Index: 0.586 → lower is better  

### Cluster Profiles

| Cluster_ID | Customers | Avg_Income | Avg_TotalSpend | Avg_TotalAccepted | Avg_Age | Avg_FamilySize |
|------------|-----------|------------|----------------|------------------|---------|----------------|
| 0          | 900       | 72,390     | 1,225          | 0.58             | 57.7    | 0.55           |
| 1          | 1,320     | 37,889     | 178            | 0.10             | 54.7    | 1.23           |

## Statistical Significance
ANOVA test on `TotalSpend` across clusters:  
- **F-Statistic:** 6094.69  
- **P-Value:** < 0.0001  
- **Conclusion:** The difference in spending between clusters is **statistically significant**.

## Business Interpretation & Strategy
### Segment 0: High-Value / Affluent Core
- **Size:** 900 customers  
- **Profile:** High income, high total spend  
- **Strategy:** Retention and premiumization — loyalty programs, exclusive offers, personalized high-end recommendations, high-touch service.  

### Segment 1: Budget / Low-Engagement Majority
- **Size:** 1,320 customers  
- **Profile:** Low income, minimal total spend  
- **Strategy:** Acquisition and efficiency — cost-effective campaigns, value-oriented pricing, entry-level products.  

## Visualizations
- Scatter plot of `Income vs TotalSpend` with cluster assignments and centroids  
- Bar charts for cluster profile comparison (optional)  
