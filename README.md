# Customer Segmentation Analysis

## Overview
This project focuses on **customer segmentation** using **RFM (Recency, Frequency, Monetary)** analysis and **K-Means clustering**. The goal is to analyze customer behavior and group customers into distinct segments based on their purchasing patterns. These segments can be used to tailor marketing strategies, improve customer retention, and maximize revenue.

## Dataset
The dataset used in this project is the **Online Retail II** dataset from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Online+Retail+II). It contains transactional data for an online retail store, including information such as:
- **Invoice**: Unique identifier for each transaction.
- **StockCode**: Product code.
- **Description**: Product description.
- **Quantity**: Number of items purchased.
- **InvoiceDate**: Date and time of the transaction.
- **Price**: Unit price of the product.
- **Customer ID**: Unique identifier for each customer.
- **Country**: Country where the transaction occurred.

## Methodology
1. **Data Preprocessing**:
   - Handled missing values and removed canceled transactions.
   - Calculated the **TotalPrice** for each transaction (`Quantity * Price`).

2. **RFM Analysis**:
   - Computed **Recency**, **Frequency**, and **Monetary** metrics for each customer:
     - **Recency**: Days since the last purchase.
     - **Frequency**: Number of unique purchases.
     - **Monetary**: Total amount spent by the customer.
   - Applied log transformation to normalize the skewed RFM data.

3. **K-Means Clustering**:
   - Used the **Elbow Method** and **Silhouette Score** to determine the optimal number of clusters.
   - Applied **K-Means clustering** to group customers into **4 distinct segments** based on their RFM scores.

4. **Visualization**:
   - Created visualizations to explore the distribution of customers across clusters and the characteristics of each segment:
     - **Count plots** to show the distribution of clusters.
     - **Scatter plots** to visualize relationships between RFM metrics.
     - **Boxplots** to analyze the distribution of Recency, Frequency, and Monetary values within each cluster.

## Results
The analysis identified **4 customer segments**:

### Cluster 0 (839 customers):
- **Recency**: Low (18.7 days)
- **Frequency**: Low (2.1 purchases)
- **Monetary Value**: Moderate (£538.25)
- **Characteristics**: These are **recent but low-engagement customers**. They have made purchases recently but have low frequency and spending.
- **Marketing Strategy**: Encourage repeat purchases with targeted promotions or loyalty programs.

### Cluster 1 (723 customers):
- **Recency**: Very Low (12.1 days)
- **Frequency**: High (13.6 purchases)
- **Monetary Value**: High (£8015.42)
- **Characteristics**: These are **high-value, loyal customers**. They purchase frequently and spend the most.
- **Marketing Strategy**: Reward loyalty with exclusive offers or VIP programs to retain them.

### Cluster 2 (1183 customers):
- **Recency**: High (70.7 days)
- **Frequency**: Moderate (4.1 purchases)
- **Monetary Value**: Moderate (£1791.09)
- **Characteristics**: These are **at-risk customers**. They haven’t purchased recently but have moderate engagement.
- **Marketing Strategy**: Re-engage with personalized offers or reminders to prevent churn.

### Cluster 3 (1594 customers):
- **Recency**: Very High (184 days)
- **Frequency**: Low (1.3 purchases)
- **Monetary Value**: Low (£342.42)
- **Characteristics**: These are **inactive customers**. They haven’t purchased in a long time and have low engagement.
- **Marketing Strategy**: Win-back campaigns with discounts or reactivation offers.
