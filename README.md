# Bank Customer Segmentation Using Clustering Techniques

## Project Overview

This project aims to segment bank customers based on their transaction history and demographic data. The goal is to use clustering techniques, such as K-Means, to group customers into distinct segments. By understanding the characteristics of each segment, the bank can offer more tailored services and marketing strategies, helping improve customer satisfaction and engagement.

### Objectives
- Analyze customer transaction patterns and demographic information.
- Segment customers into distinct groups using K-Means clustering.
- Identify key characteristics of each segment to enhance marketing strategies and improve customer retention.
- Provide insights for risk management and service customization based on customer profiles.

## Dataset

The dataset used for this project is the "Bank Customer Dataset," which includes the following columns:

- `cat__job_*`: One-hot encoded categorical features representing various job types.
- `cat__marital_*`: Categorical features for marital status.
- `cat__education_*`: Categorical features for education level.
- `cat__default_*`: Whether the customer has credit default.
- `cat__housing_*`: Whether the customer has a housing loan.
- `cat__loan_*`: Whether the customer has a personal loan.
- `remainder__age`: Age of the customer.
- `remainder__balance`: Balance on the customer's account.
- `remainder__duration`: Duration of the last contact.
- `remainder__campaign`: Number of contacts during this campaign.
- Additional features representing various characteristics of the customer.

### Methodology
1. **Data Loading and Initial Exploration**:
   - Load the dataset and perform initial exploration to understand its structure and contents.

2. **Missing Values Handling**:
   - Identify and handle missing values by imputing numerical columns with their median and categorical columns with their mode.

3. **Duplicate Data Check**:
   - Check for and remove duplicate rows from the dataset.

4. **Outlier Detection and Handling**:
   - Detect outliers using the IQR method and cap them accordingly.

5. **Feature Engineering**:
   - Encode categorical features into numerical values and scale numerical features using `StandardScaler`.

6. **K-Means Clustering**:
   - Determine the optimal number of clusters using the Elbow Method and Silhouette Analysis.
   - Fit the K-Means model and evaluate its performance.

7. **Cluster Analysis**:
   - Analyze the characteristics of each segment and visualize the results.

## Key Results

The clustering analysis produced four distinct customer segments. 

## Source

https://www.kaggle.com/datasets/nimishsawant/bankfull
