# Bank Marketing Campaign Prediction

This project analyzes a bank marketing dataset to predict customer subscription to term deposits (`yes` or `no`). The dataset contains information on customer demographics, campaign interactions, and previous outcomes.

### Problem Statement

Predicting the success of marketing campaigns helps businesses optimize spending and improve ROI. This project analyzed a bank’s marketing data to predict customer subscription to term deposits.

### Solution Approach

Data: Demographics, engagement data, and campaign interaction history.

Methods:

- Applied feature engineering to create meaningful variables, such as past campaign success rates.
- Built predictive models (Logistic Regression, Gradient Boosting) to classify customers based on their likelihood of subscribing.
- Evaluated models using precision-recall metrics to optimize for campaign targeting.
- Tools: Python (pandas, Scikit-learn, Matplotlib).

### Results

- Achieved a precision of 0.78, ensuring high accuracy in targeting likely subscribers.
- Identified high-value customer segments to focus campaign efforts, reducing wasted outreach.

### Key Insights

- Predictive modeling enhances the efficiency and success rates of marketing campaigns.
- Data-driven targeting minimizes marketing costs while maximizing returns.

## Dataset Overview

- **Source**: Bank Marketing Data
- **Target Variable**: `y` (1 for "yes", 0 for "no")
- **Features**: Customer demographics, campaign details, and previous outcomes.

---

## Objectives

1. **Analyze the dataset**:
   - Handle missing values, outliers, and categorical data.
   - Perform exploratory data analysis (EDA).
2. **Build Classification Models**:
   - Predict customer subscription using Logistic Regression and Random Forest.
3. **Hyperparameter Tuning**:
   - Use `GridSearchCV` to optimize the Random Forest model.
4. **Evaluate Model Performance**:
   - Assess accuracy, precision, recall, F1-score, and AUC-ROC.

---

## Project Steps

### 1. Data Preprocessing
- One-hot encoded categorical columns.
- Converted target variable (`y`) to binary (1 for "yes", 0 for "no").
- Split data into training (80%) and test (20%) sets.

### 2. Exploratory Data Analysis (EDA)
- Checked for missing values and imputed them.
- Analyzed feature distributions and correlations.
- Identified and capped outliers.

### 3. Model Training and Evaluation
#### Models:
1. **Logistic Regression**:
   - Accuracy: 89.87%
   - Recall for minority class: 35%
   - AUC-ROC: Moderate
2. **Random Forest**:
   - Accuracy: 90.38%
   - Recall for minority class: 40%
   - AUC-ROC: Excellent (0.9265)

#### Hyperparameter Tuning:
- Best parameters for Random Forest:
  - `n_estimators=100`, `max_depth=None`, `min_samples_split=2`, `min_samples_leaf=1`, `bootstrap=True`
- Performance after tuning:
  - Accuracy: 90.31%
  - Recall for minority class: 34%
  - AUC-ROC: 0.9265

---

## Key Insights

- The Random Forest model outperformed Logistic Regression in overall metrics and AUC-ROC.
- The recall for the minority class (class `1`) is low, suggesting class imbalance affects model performance.

---

## Recommendations

- Address class imbalance using techniques like SMOTE or class weighting.
- Explore feature importance and ensemble methods to improve prediction.
- Fine-tune Logistic Regression with regularization.

---

## Visualization

### Receiver Operating Characteristic (ROC) Curve
![ROC Curve](path/to/roc_curve.png)

---

## Future Work

- Experiment with other classifiers (e.g., XGBoost, SVM).
- Implement ensemble techniques to combine model strengths.
- Use advanced imbalance handling techniques.

---

## Results

- **Best Model**: Random Forest
- **AUC-ROC**: 0.9265
- **Accuracy**: 90.31%
- **Recall (Minority Class)**: 34%


## Source

https://www.kaggle.com/datasets/nimishsawant/bankfull
