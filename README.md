# Portfolio
Collection of past work/projects

This Portfolio will contain a collection of 10 projects created throughout a Data Science Masters Program.

--------
Phishing Link Identifier

Machine learning model to detect phishing URLs using XGBoost, achieving high accuracy (99.5%) on a balanced dataset of over 200,000 URLs. This was done by engineering 48 features, such as "suspicious keywords" and the presence of "s" at the end of "http". Python code was written to enable real-world deployment in a browser extension to enhance cybersecurity.

--------
Airport Customer Satisfaction

Examines the surge in U.S. airport complaints since 2020, focusing on Orlando International Airport (MCO), where CLEAR’s Expedited Passenger Screening Program has driven dissatisfaction, unlike at airports like Dallas Love Field. Using Department of Transportation data, it proposes to MCO Board Members via PowerPoint that decommissioning CLEAR could cut complaints, boost morale, and raise profits, despite some unfiled complaint data gaps.

--------
Predicting Costa Rican Household Poverty Levels

Using Gradient Boosting (XGBoost) for predicting poverty levels in Costa Rica, chosen for its ability to handle mixed feature types and non-linear relationships, despite being less interpretable. Initial testing yielded a strong performance (MAE: 0.1156, QWK: 0.8960), with minor misclassification issues for poverty levels 2 and 3. Using GridSearchCV with 5-fold cross-validation, the model improved (MAE: 0.0842, QWK: 0.9241), though recall for poverty level 2 declined slightly. The final model, with optimized parameters, shows promise for aiding poverty reduction programs by predicting household poverty based on factors like family size and education, though further refinement is needed to enhance accuracy for at-risk levels before integration into Costa Rica’s welfare system.

--------
Loan Application Outcomes

Evaluating of loan application outcomes (approved/denied). Initial KNN modeling (K=5) achieved 70% training accuracy, improving to 75% with K=4 via GridSearchCV and 5-fold cross-validation, though test accuracy was 67%. Expanding GridSearchCV to include Logistic Regression and Random Forest revealed Logistic Regression as the best model (83% accuracy) with L1 penalty, liblinear solver, and tuned C, excelling due to the dataset’s structured, binary, and numeric nature, while KNN struggled with binary feature distances and Random Forest overfit the small dataset.

--------
Movie Review Sentiment Analysis

Sentiment analysis of movie reviews. N = 25,000. TF-IDF vectorization is applied to transform the text, and two models are tested: Logistic Regression (88% test accuracy) and Support Vector Machine (SVM, 87.5% accuracy). Performance metrics, including accuracy, precision, recall, F1-score, confusion matrices, and ROC curves, are evaluated, with Logistic Regression slightly outperforming SVM due to better recall, making it the preferred model for this binary sentiment classification task.

--------
Shelter Dog Adoptability

Analyzing dog adoptability traits, exploring factors influencing adoption speed and reduce shelter euthanizations. Findings show no significant correlation between adoption speed and age (r=0.15) or neutered status (r=-0.19), but a box plot of the top 20 breeds reveals potential patterns—e.g., slower adoptions for Mixed Breeds versus faster for Shih Tzus—offering a starting point for further investigation into breed-specific adoptability factors.

--------
Predicting Solar Proton Events

Leveraging NiFi, HDFS, Hive, Spark, Spark MLlib, and HBase—to process and predict solar flare magnitudes (Max PFU) using NOAA Space Weather Prediction Center data from 1976 to 2024. Solar flares, massive solar radiation bursts, can disrupt Earth’s technology, making accurate, real-time forecasts vital for risk management. The pipeline ingests data via NiFi from a GitHub-hosted CSV, stores it in HDFS, processes it with Hive and PySpark (cleaning, transforming features like latitude), and trains a Decision Tree Regression model in Spark MLlib, achieving an R² of 0.75 and RMSE of 50.23, with latitude as the top predictor. Performance metrics are stored in HBase, demonstrating a scalable framework for real-time solar flare prediction.

--------
Pedestrian Deaths & SUVs

Exploring the link between rising U.S. pedestrian deaths and increasing SUV sales. Building on a 2004 study showing SUVs are over twice as deadly to pedestrians as cars, EDA confirms SUV sales strongly correlate with deaths, outpacing cell phone subscriptions in regression models. The study missed deeper analysis of handheld device bans and lacked data on death causes (e.g., distracted driving). Assumptions about passenger car sales were disproven, and data inconsistencies posed challenges.

--------
TBD

--------
TBD
