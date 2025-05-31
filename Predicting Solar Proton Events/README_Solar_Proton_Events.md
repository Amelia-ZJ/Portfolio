# Solar Proton Event Prediction with Big Data Ecosystem

## Overview
This project uses a full-scale big data pipeline to process and analyze solar proton event data from NOAA, enabling prediction of solar flare intensity (Max PFU). By leveraging Dockerized tools such as NiFi, HDFS, Hive, Spark MLlib, and HBase, we designed an architecture that mimics real-time ingestion, transformation, model training, and storage of predictive insights. Our model helps improve scientific forecasting of high-impact solar events that threaten Earth’s technology infrastructure.

## Table of Contents
- [Requirements](#requirements)
- [Data Source](#data-source)
- [Pipeline Architecture](#pipeline-architecture)
- [Modeling](#modeling)
- [Results](#results)
- [Challenges](#challenges)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [References](#references)

## Requirements
Docker containers running:
- Apache NiFi
- HDFS
- Hive
- Spark
- HBase
Python packages (in all containers):
- numpy
- happybase
- pyspark

## Data Source
- **Provider**: NOAA Space Weather Prediction Center  
- **Date Range**: May 1976 – September 2024  
- **Records**: Over 300 events  
- **GitHub Source**: [CSV File](https://raw.githubusercontent.com/Amelia-ZJ/DSC650/refs/heads/main/solar_proton_events_cleaned.csv)  
- **Key Features**: Date, time, location (lat/lon), PFU magnitude, duration, class, sun impact  

## Pipeline Architecture

### 1. NiFi (Data Ingestion)
- Pulls data from GitHub using `InvokeHTTP`
- Writes data into HDFS using `PutHDFS`

### 2. HDFS (Storage)
- Stores raw CSV data
- Renamed to `solar_events.csv` for schema clarity

### 3. Hive (Query Engine)
- Table `solar_events` created for SQL querying
- Used for missing value checks and schema exploration

### 4. Spark (ETL + Machine Learning)
- **Cleaning**: Converted strings to numeric, dropped duplicates, handled nulls
- **EDA**: Correlation matrix, outlier detection
- **Modeling**: Decision Tree Regression via Spark MLlib

### 5. HBase (Output Storage)
- Stored performance metrics and feature importance
- Enabled persistence of model evaluation results

## Modeling

- **Algorithm**: Decision Tree Regression (PySpark MLlib)
- **Target**: `Max PFU` (solar flare intensity)
- **Features**: Latitude, year, longitude, region, time of day

**Model Evaluation:**
- RMSE: 50.23  
- R²: 0.75  
- MAE: 35.67

**Top Predictors:**
- `latdegrees`: 0.466  
- `year`: 0.334  
- `logdegrees`: 0.091  
- `region`: 0.045  
- `month`: 0.025  

## Challenges
- NiFi start-up errors (`JAVA_HOME not set`)
- Hive classpath conflicts
- Correlation matrix anomalies (e.g., `maxday` with R = 9.9)
- PySpark version limitations

## Conclusion
We successfully created an end-to-end pipeline to ingest, clean, analyze, and predict solar proton event severity using big data tools. The Decision Tree model achieved reasonable accuracy (R² = 0.75), with latitude emerging as the most important predictor. This project demonstrates the value of real-time prediction systems in space weather forecasting.

## Future Work
- Integrate live data feed (e.g., NASA or NOAA APIs)
- Add smoothing and GridSearchCV to reduce prediction error
- Implement real-time model retraining and dashboard visualization
- Explore additional models (e.g., XGBoost, Random Forest Regressor)

## References
1. NOAA SWPC – [Solar Proton Events Data](https://www.ngdc.noaa.gov/stp/space-weather/interplanetary-data/solar-proton-events/SEP%20page%20code.html)  
2. Abduallah, Y. et al. (2023). *Operational prediction of solar flares using a transformer-based framework.* Scientific Reports.  
3. Daglis, I. et al. (2004). *Effects of space weather on technology infrastructure.* Space Weather 2.
