# Poverty Prediction: Predicting Household Poverty in Costa Rica

## Overview
This project supports the United Nations’ Sustainable Development Goal #1: the eradication of poverty by 2030. Using real-world survey data from Costa Rica, we built a machine learning model to classify households into one of four poverty levels. The project aims to assist government programs like *Puente al Desarrollo* in targeting at-risk households more effectively by considering more than just income.

## Table of Contents
- [Requirements](#requirements)
- [Dataset](#dataset)
- [Data Preparation](#data-preparation)
- [Modeling & Evaluation](#modeling--evaluation)
- [Results](#results)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Requirements
- pandas  
- numpy  
- scikit-learn  
- xgboost  
- imblearn  
- seaborn  
- matplotlib  

## Dataset
- **Source**: INEC Costa Rican household survey (9,557 households)  
- **Supplemented by**: World Bank socio-economic indicators  
- **Features**: 143 household-level attributes including:
  - Education
  - Roof/floor/wall type
  - Trash disposal method
  - Access to internet
  - Number of dependents
  - Household assets (e.g. tablets, refrigerators)
- **Target**: Poverty level
  - 1 = Extreme Poverty
  - 2 = Moderate Poverty
  - 3 = Vulnerable
  - 4 = Non-Vulnerable

## Data Preparation
- Renamed and cleaned variables for clarity.
- Dropped columns with >40% missing data.
- Handled multicollinearity by removing highly correlated features (|r| > 0.8).
- Encoded binary text values (“yes”/“no”) to 1/0.
- Used SMOTE (oversampling) and undersampling to address class imbalance:
  - Minority classes (1–3) oversampled.
  - Majority class (4) downsampled.
- Final dataset: 131 predictive features.

## Modeling & Evaluation

### Model Type
- **Ordinal classification problem** (1 to 4 ranked poverty levels)
- **Selected model**: XGBoost (Gradient Boosting Classifier)

### Initial Model Performance
- `objective='multi:softmax'`, `num_class=4`, `eval_metric='mlogloss'`
- **MAE**: 0.1156
- **QWK**: 0.8960

### Tuned Model (GridSearchCV + 5-Fold Cross Validation)
- Tuned parameters: `max_depth`, `learning_rate`, `n_estimators`, `subsample`, `colsample_bytree`
- **MAE**: 0.0842
- **QWK**: 0.9241
- **Key improvement**: Better precision on poverty level 3

## Results
- The tuned model performs exceptionally well with an MAE under 0.09 and QWK over 0.92.
- Misclassification is rare, but poverty levels 2 and 3 had slightly lower recall.
- The model is ready for pilot use in governmental programs targeting poverty alleviation.

## Conclusion
Our XGBoost model accurately predicts household poverty using a diverse set of features beyond income. With minor improvements to recall on poverty level 2, this model has strong potential for real-world deployment. It enables Costa Rican social programs to target vulnerable households more precisely and efficiently.

## Future Work
- Improve recall for poverty level 2 using model weighting or alternative ordinal classifiers.
- Integrate real-time feedback from field use to retrain and improve model.
- Expand features with geographic and policy-level data for holistic poverty modeling.
- Develop a user interface for government workers to input and retrieve predictions.

## License
This project is released under the MIT License.

## Acknowledgements
- Instituto Nacional de Estadística y Censos (INEC)
- World Bank
- United Nations Sustainable Development Goals (SDG)
- Kaggle Dataset: [Costa Rican Household Poverty](https://www.kaggle.com/datasets/data855/costa-rican-household-poverty-dataset)
