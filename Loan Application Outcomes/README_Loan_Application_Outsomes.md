# Loan Application Outcomes

## Overview
This project analyzes loan application outcomes (approved or denied) using machine learning classification models. The goal was to determine the best-performing algorithm through model comparison and hyperparameter tuning. The analysis includes K-Nearest Neighbors (KNN), Logistic Regression, and Random Forest classifiers with cross-validation.

## Table of Contents
- [Requirements](#requirements)
- [Dataset](#dataset)
- [Data Preparation](#data-preparation)
- [Modeling & Evaluation](#modeling--evaluation)
- [Results](#results)
- [Conclusion](#conclusion)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Requirements
- pandas  
- numpy  
- scikit-learn  
- matplotlib  
- seaborn  

## Dataset
- **Source**: Provided loan application dataset (Loan_Train.csv)
- **Records**: ~480 samples after cleaning
- **Features**:
  - Applicant and Coapplicant Income
  - Loan Amount and Term
  - Credit History
  - Education, Gender, Marital Status, Dependents, Employment

## Data Preparation
- Dropped `Loan_ID` as it had no predictive value.
- Removed rows with missing values to ensure clean input data.
- Categorical variables converted into dummy/indicator variables.
- Final feature matrix included 14 numeric/binary variables.
- Target variable: `Loan_Status` (Y = 1, N = 0)

## Modeling & Evaluation

### Step 1: KNN Baseline Model
- **Pipeline**: MinMaxScaler + KNeighborsClassifier (k=5)
- **Test Accuracy**: 70.8%

### Step 2: Hyperparameter Tuning (KNN)
- **GridSearchCV**: `n_neighbors` from 1 to 10
- **Best k**: 4
- **Cross-Validation Accuracy**: 74.9%
- **Test Accuracy**: 66.7%

### Step 3: Model Comparison with GridSearchCV
- **Models Tested**:
  - KNN: `n_neighbors` 1–10
  - Logistic Regression: `penalty`, `C`, solver='liblinear'
  - Random Forest: `n_estimators`, `max_features`
- **Best Model**: Logistic Regression
- **Best Parameters**: `penalty='l1'`, `C=1.0`, `solver='liblinear'`
- **Final Test Accuracy**: **83.3%**

## Results
- Logistic Regression outperformed both KNN and Random Forest.
- Strong performance likely due to binary/numeric data and linear separation in features.
- KNN struggled with binary features due to distance limitations.
- Random Forest showed signs of overfitting given the small dataset size.

## Conclusion
Logistic Regression proved to be the most effective classifier for this dataset, achieving over 83% test accuracy. It was chosen based on robust cross-validation results and strong generalization. This reinforces the idea that simpler models can outperform more complex ones when the data is structured and features are well-behaved.

## License
This project is released under the MIT License.

## Acknowledgements
- Sklearn documentation for GridSearchCV and model tuning strategies
- UCI/Kaggle datasets for foundational examples
