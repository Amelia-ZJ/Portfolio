# Phishing Link Identifier
  

Overview
The Phishing Link Identifier is a machine learning project designed to detect phishing URLs using XGBoost. By engineering 43 features from a Kaggle dataset of 450,176 URLs, the model identifies phishing patterns such as suspicious keywords and typosquatting, achieving an accuracy of over 0.99. This project aims to enhance cybersecurity by enabling real-time phishing detection, with potential deployment as a browser extension.

## Table of Contents
- [Installation](#installation)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [Features](#features)
- [Results](#results)
- [Challenges and Limitations](#challenges-and-limitations)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)


Requirements

pandas
numpy
scikit-learn
xgboost
matplotlib
seaborn


Prepare the Dataset:
Download the dataset from Kaggle and place it in the data/ directory as url_data.csv.
The dataset contains 450,176 URLs labeled as "legitimate" or "phishing."
Run the Feature Extraction and Model Training:
The main script (train_model.py) extracts 43 features, balances the dataset, trains the XGBoost model, and evaluates its performance.
bash

Collapse

Wrap

Copy
python train_model.py
Visualize Results:
Feature importance plots and evaluation metrics (e.g., accuracy, AUC-ROC) are saved in the results/ directory.
Example command to generate a feature importance plot:
python

Collapse

Wrap

Copy
python plot_feature_importance.py
Test a URL:
Use the predict.py script to classify a new URL:
bash

Collapse

Wrap

Copy
python predict.py --url "https://example.com"
Features
The model uses 43 engineered features to detect phishing URLs, including:

Structural Features: num_dots, num_slashes, total_length
Content-Based Features: has_suspicious_keywords, num_special_chars
Domain Features: has_punycode, min_levenshtein_distance
Statistical Features: entropy, vowel_to_consonant_ratio
Key features like has_suspicious_keywords (highest importance) effectively identify phishing patterns such as deceptive keywords and typosquatting.

Results
Model Performance:
XGBoost achieved an accuracy of over 0.99, slightly outperforming Logistic Regression (accuracy 0.9888, AUC-ROC 0.9975).
Precision: 0.9966, Recall: 0.9794, F1-Score: 0.9879 (Logistic Regression).
Feature Importance (Gain-Based):
Top features: has_suspicious_keywords, has_https, num_numbers.
has_suspicious_keywords was the most impactful, reflecting its role in identifying phishing URLs with deceptive keywords.
Sample Prediction:
Test URL classified as "Phishing" with 100% probability, validating real-world applicability.
Challenges and Limitations
Challenges:
Initial concern over indistinct phishing patterns; mitigated by extensive feature engineering.
Imbalanced dataset (77% legitimate) required undersampling, reducing sample size.
Undefined suspicious_keywords list risked incomplete detection.
Limitations:
Dataset limited to 450,176 URLs, may miss emerging phishing tactics.
Lacks contextual features (e.g., web traffic, WHOIS data).
Hardcoded list of known domains for min_levenshtein_distance may not scale.
Risk of overfitting to features like has_suspicious_keywords.
Future Work
Validate the model on real-world datasets like PhishTank to improve generalization.
Incorporate contextual features (e.g., domain age, redirect count) for better accuracy.
Deploy as a browser extension with optimized feature extraction for real-time use.
Retrain every 3–6 months using sources like OpenPhish to adapt to evolving phishing tactics.
Contributing
Contributions are welcome! Please follow these steps:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Commit your changes (git commit -m "Add new feature").
Push to the branch (git push origin feature-branch).
Open a pull request.
License
This project is licensed under the MIT License. See the  file for details.

Acknowledgements
Dataset: Kaggle Phishing URLs Dataset
Libraries: XGBoost, scikit-learn, pandas, matplotlib, seaborn
Course: DSC680, for providing the framework for this project