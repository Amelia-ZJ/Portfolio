# Shelter Dog Adoptability Prediction

## Overview
This project explores shelter dog data to predict adoptability outcomes based on breed, age, intake condition, size, and other characteristics. The goal is to help shelters prioritize care and marketing strategies for dogs less likely to be adopted. By building a classification model using historical intake and outcome data, we aim to support data-driven adoption efforts and improve shelter efficiency.

## Table of Contents
- [Requirements](#requirements)
- [Dataset](#dataset)
- [Data Preparation](#data-preparation)
- [Modeling & Evaluation](#modeling--evaluation)
- [Results](#results)
- [Challenges](#challenges)
- [Future Work](#future-work)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Requirements
- pandas  
- numpy  
- scikit-learn  
- matplotlib  
- seaborn  
- xgboost  
- imblearn  

## Dataset
- **Source**: Public animal shelter intake and outcome dataset (e.g., Austin Animal Center or Kaggle)
- **Features Included**:
  - Age at intake
  - Breed type (pure vs. mixed)
  - Size category (small, medium, large)
  - Intake condition (healthy, injured, stray, etc.)
  - Spay/neuter status
  - Length of stay
  - Color and coat type
- **Target Variable**: Adoptability status (Adopted vs. Not Adopted)

## Data Preparation
- Cleaned missing values and removed ambiguous records (e.g., incomplete outcome data).
- Binned age into categories (puppy, adult, senior).
- Encoded categorical features using one-hot encoding.
- Balanced classes using SMOTE for adoptability prediction.

## Modeling & Evaluation
- Models tested:
  - Logistic Regression
  - Random Forest
  - XGBoost Classifier
- Evaluation Metrics:
  - Accuracy
  - Precision/Recall
  - F1 Score
  - ROC-AUC
- SHAP used for interpretability to understand top predictors of adoptability.

## Results
- **Best Model**: XGBoost Classifier
- **Top Predictors**: Age group, intake condition, breed type, length of stay
- **Accuracy**: ~87% (depending on version/tuning)
- Dogs with poor health intake or non-spayed conditions were less likely to be adopted.
- Puppies and small breeds had the highest adoptability rates.

## Challenges
- Breed and color classification inconsistencies required extensive cleaning.
- Length of stay often skews the classification label (time-dependent bias).
- Mixed-breed identification can vary between shelters.

## Future Work
- Integrate text data from behavioral notes or adoption descriptions (NLP).
- Expand model to multiclass outcomes (e.g., Adopted, Transferred, Euthanized).
- Deploy web tool for shelter staff to receive adoptability scores during intake.
- Explore breed-specific policy recommendations based on model output.

## License
This project is released under the MIT License.

## Acknowledgements
- Austin Animal Center Open Data Portal (or appropriate source)
- Scikit-learn and XGBoost documentation
- SMOTE implementation from imbalanced-learn
