# Bank Customer Segmentation Using Clustering Techniques

## Project Overview

This project aims to segment bank customers based on their transaction history and demographic data. The goal is to use clustering techniques, such as K-Means, to group customers into distinct segments. By understanding the characteristics of each segment, the bank can offer more tailored services and marketing strategies, helping improve customer satisfaction and engagement.

## Dataset

The dataset used in this project is the [Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing), which contains information about the bank's customers, including their age, job type, balance, previous contact information, and other demographic and transactional details.

- **Data Source**: UCI Machine Learning Repository
- **Number of Rows**: 45,211
- **Number of Features**: 17

### Key Features:

- `age`: Age of the customer.
- `job`: Type of job.
- `balance`: Customer's account balance.
- `duration`: Duration of the last contact with the customer.
- `campaign`: Number of contacts performed during the campaign.
- `previous`: Number of contacts before the campaign.
- `loan`: Whether the customer has a loan.

The data is related with direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be ('yes') or not ('no') subscribed.

## Project Steps

### 1. **Data Preprocessing**
   - **Data Cleaning**: Handle missing values, drop duplicates, and handle outliers using the Interquartile Range (IQR) method.
   - **Feature Engineering**: Encode categorical variables using OneHotEncoder and create additional features such as `total_contacts` and `avg_duration` for clustering.

### 2. **Clustering with K-Means**
   - **Dimensionality Reduction**: Apply Principal Component Analysis (PCA) to reduce the dimensionality of the dataset while preserving 95% of the variance.
   - **Finding Optimal Clusters**: Use the **Elbow Method** and **Silhouette Analysis** to determine the optimal number of clusters.
   - **K-Means Clustering**: Train the K-Means clustering model with the optimal number of clusters.
   
### 3. **Cluster Profiling**
   - **Cluster Profiling**: Analyze the characteristics of each cluster by calculating average age, balance, and other key variables.
   - **Visualization**: Visualize cluster distributions using boxplots and scatterplots of the principal components.

### 4. **Business Insights**
   - Extract key insights for each cluster, such as average customer age, balance, and loan status, to help the bank design more targeted offers.

## Key Results

- The clustering model grouped customers into **4 clusters** with the following distribution:
  - Cluster 2: 21,624 customers
  - Cluster 0: 11,787 customers
  - Cluster 1: 9,782 customers
  - Cluster 3: 2,018 customers
- **Silhouette Scores** indicated the clusters' separation quality, with the highest score for 2 clusters (0.0766). However, 4 clusters were chosen for more detailed segmentation.
  
### Cluster Profiles
Each cluster has different characteristics based on demographics and transactional data:

- **Cluster 0**:  
  - **Average Age**: -0.02 (after standardization)
  - **Median Balance**: -0.29 (standardized)
  - **Percentage with Loan**: -6.88%

- **Cluster 1**:  
  - **Average Age**: -0.72
  - **Median Balance**: -0.48
  - **Percentage with Loan**: -4.83%

- **Cluster 2**:  
  - **Average Age**: 0.31
  - **Median Balance**: -0.44
  - **Percentage with Loan**: 8.29%

- **Cluster 3**:  
  - **Average Age**: 0.34
  - **Median Balance**: -0.31
  - **Percentage with Loan**: -25.17%

### **Code Explanation & Insights:**

#### **1. Data Preprocessing:**
- **Handling Missing Values**: No missing values were found in the dataset based on the output.
- **Outliers**: Outliers were detected in several columns, such as `balance`, `duration`, and `campaign`, which were handled through capping based on the Interquartile Range (IQR).

#### **2. Feature Engineering & Scaling:**
- **Encoding Categorical Variables**: The dataset contains several categorical variables (e.g., `job`, `marital`, `education`). These were encoded using **OneHotEncoder**, which converted them into binary variables.
- **New Features**:
  - `total_contacts`: The sum of previous contacts plus one, indicating the total number of contacts a customer had with the bank.
  - `avg_duration`: The average duration of each contact during the campaign.

#### **3. Clustering:**
- **Principal Component Analysis (PCA)**: PCA was used to reduce dimensionality while retaining 95% of the variance. This transformation helped to simplify the clustering process by reducing complexity.
- **K-Means Clustering**: The **Elbow Method** and **Silhouette Analysis** were applied to find the optimal number of clusters. The Silhouette scores indicated that 2 clusters yielded the best separation, but 4 clusters were chosen for better segmentation granularity.

#### **4. Cluster Profiling:**
- **Cluster 0**: Customers in this cluster have a low average age (standardized around -0.02), a relatively low balance, and a lower likelihood of having a loan.
- **Cluster 1**: Customers tend to have a lower average age (-0.72) and a negative median balance (-0.48). They are also less likely to have a loan (-4.83%).
- **Cluster 2**: This cluster has higher average ages and is more likely to have loans (8.29%). They have slightly better financial profiles compared to Cluster 0 and 1.
- **Cluster 3**: These customers have the highest average ages (0.34) but also a negative median balance. Interestingly, they are the least likely to have loans.

#### **5. Insights:**
- **Loan Services**: Based on the clustering, Cluster 2 appears to have a higher loan uptake. Banks may target this group with loan products or offers.
- **Older Customers**: Clusters 2 and 3 tend to have older customers. Offering tailored financial services, such as retirement planning or investment products, may be beneficial for these clusters.
- **Younger Customers**: Cluster 1, with younger customers and lower balances, may be offered savings products or educational content to help them build wealth.

### Source

https://www.kaggle.com/datasets/krantiswalke/bankfullcsv
