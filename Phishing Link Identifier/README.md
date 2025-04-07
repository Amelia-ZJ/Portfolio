# Phishing Link Identifier
  

## Overview
Machine learning model to detect phishing URLs using XGBoost, achieving high accuracy (99.5%) on a balanced dataset of over 200,000 URLs. This was done by engineering 48 features, such as "suspicious keywords" and the presence of "s" at the end of "http". Python code was written to enable real-world deployment in a browser extension to enhance cybersecurity.phishing patterns such as suspicious keywords and typosquatting, achieving an accuracy of over 0.99. This project aims to enhance cybersecurity by enabling real-time phishing detection, with potential deployment as a browser extension.

## Table of Contents
- [Requirements](#Requirements)
- [Dataset](#Dataset)
- [Results](#Results)
- [Challenges](#Challenges)
- [Limitations](#Limitations)
- [Future Work](#future-work)
- [License](#License)
- [Acknowledgements](#Acknowledgements)

## Requirements
- pandas
- numpy
- scikit-learn
- xgboost
- matplotlib
- seaborn


## Dataset
- Download the dataset from Kaggle and place it in the data/ directory as url_data.csv.
- The dataset contains 450,176 URLs labeled as "legitimate" or "phishing".

	- Structural Features: num_dots, num_slashes, total_length
	- Content-Based Features: has_suspicious_keywords, num_special_chars
	 -Domain Features: has_punycode, min_levenshtein_distance
	 -Statistical Features: entropy, vowel_to_consonant_ratio
	 -Key features like has_suspicious_keywords (highest importance) effectively identify phishing patterns such as deceptive keywords and typosquatting.

- Run the Feature Extraction functions to obtain the 43 features of each URL for Model Training.
- The main script (train_model.py) extracts 43 features, balances the dataset, trains the XGBoost model, and evaluates its performance.

## Results
Model Performance:
- XGBoost achieved an accuracy of 0.995, slightly outperforming Logistic Regression (accuracy 0.9888, AUC-ROC 0.9975).

| Model                 | Accuracy | Precision | Recall | F1-Score | AUC-ROC |
|-----------------------|----------|-----------|--------|----------|---------|
| Logistic Regression   | 0.99     | 1         | 0.98   | 0.99     | 1       |
| 5CV Logistic Regression | 0.99   | 1         | 0.98   | 0.99     | 1       |
| XGBoost               | 1        | 1         | 0.99   | 1        | 1       |

- Feature Importance (Gain-Based) -> Top features: has_suspicious_keywords and has_https.
- Generate a feature importance plots.

Sample Prediction:
- Test URL classified as "Phishing" with 100% probability, validating real-world applicability.

## Challenges
- Initial concern over indistinct phishing patterns; mitigated by extensive feature engineering.
- Imbalanced dataset (77% legitimate) required undersampling, reducing sample size for 200,000.
- Undefined suspicious_keywords list risked incomplete detection.

## Limitations
- Dataset limited to 200,000 URLs after balancing and may miss emerging phishing tactics.
- Lacks contextual features (e.g., web traffic, WHOIS data).
- Hardcoded list of known domains for min_levenshtein_distance may not scale.
- Risk of overfitting to features like has_suspicious_keywords.

## Future Work
- Validate the model on real-world datasets like PhishTank to improve generalization.
- Incorporate contextual features (e.g., domain age, redirect count) for better accuracy.
- Deploy as a browser extension with optimized feature extraction for real-time use.
- Retrain every 3–6 months using sources like OpenPhish to adapt to evolving phishing tactics.

## License
This project is licensed under the MIT License.

## Acknowledgements
Dataset: Kaggle Phishing URLs Dataset
Libraries: XGBoost, scikit-learn, pandas, matplotlib, seaborn