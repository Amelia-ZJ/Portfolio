# Smart Manufacturing: Predictive Maintenance with Machine Learning

## Overview
This project applies machine learning techniques to minimize unplanned downtime in manufacturing facilities using IoT sensor data. By predicting machine failures in advance and identifying root causes, the model enables proactive maintenance, improving productivity and reducing operational costs. The system uses XGBoost for binary and multiclass classification, supported by SHAP for interpretability and SMOTE to address class imbalance.

## Table of Contents
- [Requirements](#requirements)
- [Dataset](#dataset)
- [Results](#results)
- [Challenges](#challenges)
- [Limitations](#limitations)
- [Future Work](#future-work)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Requirements
- pandas  
- numpy  
- scikit-learn  
- xgboost  
- imblearn  
- shap  
- matplotlib  
- seaborn  

## Dataset
- Source: Simulated machine failure dataset from Kaggle/UCI.
- ~1,000 records with 10 key variables including:
  - **Air Temperature**
  - **Process Temperature**
  - **Rotational Speed**
  - **Torque**
  - **Tool Wear**
- Target: Binary machine failure status and 5 multiclass failure types.
- Feature engineering included:
  - **Temperature Difference**
  - **Torque-to-Speed Ratio**
  - **Principal Component Analysis (PCA)** for clustering.

## Results

### Binary Classification (Failure Prediction)
- **Model**: XGBoost
- **Accuracy**: 91%
- **Recall (Failure)**: 0.90
- **Key Predictors**: Tool wear, torque, torque/speed ratio (based on SHAP)

### Multiclass Classification (Root Cause Prediction)
- **Model**: XGBoost + SMOTE
- **Accuracy**: 98%
- **Precision/Recall**: >95% for all failure types
- **Top Features by Failure Type**:  
  - Power failure: torque, speed, wear  
  - Tool wear failure: tool wear, torque/speed  
  - Heat dissipation: temperature difference, PCA component

## Challenges
- Severe class imbalance initially biased the model toward predicting no failure.
- SMOTE was used to rebalance the dataset, but careful validation was needed to avoid overfitting.
- Translating model outputs into actionable insights required SHAP visualization and threshold tuning.

## Limitations
- Dataset is synthetic; real-world performance will require retraining on factory-specific data.
- Analysis was performed on batch data, not real-time streaming.
- SHAP explanations may be too complex for non-technical users without additional UI or training support.

## Future Work
- Deploy pilot on actual manufacturing line with historical sensor data.
- Incorporate real-time streaming via IoT integration.
- Develop user-friendly dashboard to surface SHAP insights in an interpretable format.
- Scale to multi-site deployment and retrain regularly to adapt to new equipment behavior.

## License
This project is released under the MIT License.

## Acknowledgements
- Dataset: Kaggle / UCI Predictive Maintenance Dataset  
- Tools: XGBoost, SHAP, SMOTE, PCA  
- Framework: CRISP-DM
