# Adult Census Income Prediction

## Project Overview

This project analyzes the Adult Census Income dataset (1994 U.S. Census data) to predict whether an individual's annual income exceeds $50K.

The objective is to apply data preprocessing, exploratory data analysis (EDA), feature engineering, dimensionality reduction, and multiple machine learning models to evaluate predictive performance.

---

## Dataset Information

- Total observations: 32,561  
- Total attributes: 15 (including target variable)  
- Observations after cleaning: 30,162  

### Numerical Features
- age  
- education.num  
- capital.gain  
- capital.loss  
- hours.per.week  

### Categorical Features
- workclass  
- education  
- marital.status  
- occupation  
- relationship  
- race  
- sex  
- native.country  

### Target Variable
- <=50K  
- >50K  

---

## Data Preprocessing

1. Converted missing values represented as "?" into NaN.
2. Removed rows containing missing values (7.37% of dataset).
3. Dropped the `fnlwgt` column.
4. Applied OneHotEncoding to categorical variables.
5. Standardized numerical features using StandardScaler.
6. Final feature space after encoding: 96 features.

---

## Exploratory Data Analysis

Key findings from EDA:

- Approximately 75% of individuals earn <=50K.
- Male individuals represent about 68% of the dataset.
- Higher education level strongly correlates with higher income.
- Individuals earning >50K:
  - Are older (median age ~43 vs 34).
  - Work more hours per week (~45 hours).
  - Have higher education years.
- Capital gain and capital loss are highly skewed.
- No strong linear correlation among numerical variables.

---

## Model Development

### Train-Test Split
- 70% training data
- 30% testing data
- random_state = 25

---

## Feature Selection

Recursive Feature Elimination (RFE) was applied using Logistic Regression to select the top 30 important features.

Accuracy remained stable (~84.59%) after feature selection.

---

## Dimensionality Reduction

Principal Component Analysis (PCA):

- Cumulative variance analysis performed.
- 42 principal components selected.
- Reduced dimensionality from 95+ features to 42 components.

---

## Model Performance (With PCA)

| Model                    | Accuracy |
|--------------------------|----------|
| Logistic Regression      | 84.46%   |
| Support Vector Machine   | 84.10%   |
| Random Forest            | 83.42%   |
| K-Nearest Neighbors      | 81.29%   |
| Decision Tree            | 80.18%   |

---

## Cross-Validation (5-Fold)

| Model                    | CV Accuracy |
|--------------------------|-------------|
| Logistic Regression      | 84.67%      |
| Support Vector Machine   | 84.45%      |
| Random Forest            | 83.46%      |
| K-Nearest Neighbors      | 81.31%      |
| Decision Tree            | 79.88%      |

---

## Final Observations

- Logistic Regression achieved the highest and most stable performance.
- SVM performed very close to Logistic Regression.
- Random Forest showed competitive results.
- PCA maintained model stability with reduced dimensionality.
- Education level, working hours, and capital gain significantly influence income classification.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

## Project Workflow

1. Load dataset  
2. Handle missing values  
3. Perform EDA  
4. Encode categorical features  
5. Standardize numerical features  
6. Train-test split  
7. Train classification models  
8. Apply RFE  
9. Apply PCA  
10. Evaluate and compare models  
11. Perform cross-validation  