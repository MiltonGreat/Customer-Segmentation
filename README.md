# Bank Marketing Campaign Prediction

This project analyzes a bank marketing dataset to predict customer subscription to term deposits (`yes` or `no`). The dataset contains information on customer demographics, campaign interactions, and previous outcomes.

### Dataset Overview

The dataset contains the following features:

- Age: Age of the customer
- Job: Type of job (e.g., admin, technician, etc.)
- Marital: Marital status (e.g., married, single, divorced)
- Education: Level of education (e.g., primary, secondary, tertiary)
- Default: Whether the customer has credit in default (yes/no)
- Balance: Account balance
- Housing: Whether the customer has a housing loan (yes/no)
- Loan: Whether the customer has a personal loan (yes/no)
- Contact: Contact communication type (e.g., cellular, telephone)
- Day: Last contact day of the month
- Month: Last contact month of year
- Duration: Duration of the last contact
- Campaign: Number of contacts performed during this campaign
- Pdays: Number of days since the client was last contacted from a previous campaign
- Previous: Number of contacts performed before this campaign
- Poutcome: Outcome of the previous marketing campaign
- y: Target variable (whether the customer subscribed to a term deposit)

### Objectives

1. **Analyze the dataset**:
   - Handle missing values, outliers, and categorical data.
   - Perform exploratory data analysis (EDA).
2. **Build Classification Models**:
   - Predict customer subscription using Logistic Regression and Random Forest.
3. **Hyperparameter Tuning**:
   - Use `GridSearchCV` to optimize the Random Forest model.
4. **Evaluate Model Performance**:
   - Assess accuracy, precision, recall, F1-score, and AUC-ROC.

### Methodology

#### 1. Data Preprocessing
- One-hot encoded categorical columns.
- Converted target variable (`y`) to binary (1 for "yes", 0 for "no").
- Split data into training (80%) and test (20%) sets.

#### 2. Exploratory Data Analysis (EDA)
- Checked for missing values and imputed them.
- Analyzed feature distributions and correlations.
- Identified and capped outliers.

### Model Evaluation

1. Random Forest Classifier

- Accuracy: 90.31%
- Precision (for class 0: not subscribed): 92%
- Recall (for class 0: not subscribed): 98%
- F1-score (for class 0: not subscribed): 95%
- Precision (for class 1: subscribed): 71%
- Recall (for class 1: subscribed): 34%
- F1-score (for class 1: subscribed): 46%

The Random Forest model performs well at predicting customers who are not subscribed to the marketing campaign but struggles with predicting those who are subscribed.

1. Logistic Regression

- Accuracy: 89.87%
- Precision (for class 0: not subscribed): 92%
- Recall (for class 0: not subscribed): 97%
- Precision (for class 1: subscribed): 65%
- Recall (for class 1: subscribed): 35%

The Logistic Regression model shows similar performance but is slightly less accurate than the Random Forest model.

### AUC-ROC

The best Random Forest model achieved an AUC-ROC of 0.9265, which indicates that the model has a high ability to distinguish between the two classes (subscribed vs not subscribed). The closer the AUC is to 1, the better the model is at making correct predictions.

### Future Work

1. Address Class Imbalance: The model performs poorly on the subscribed class (class 1), likely due to the imbalance in the dataset. Future work could involve using techniques like SMOTE or oversampling to balance the class distribution.

2. Feature Engineering: Additional feature engineering, such as creating interaction terms between variables or aggregating features, could improve model performance.

3. Model Experimentation: Experimenting with other classification algorithms like XGBoost, SVM, or Neural Networks might lead to better predictive performance, particularly for the subscribed class.

### Source

https://www.kaggle.com/datasets/nimishsawant/bankfull
