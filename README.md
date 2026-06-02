# Wildfire Ignition Risk Prediction (Colorado)

## Overview

This project models wildfire ignition risk across Colorado using climate, spatial, and machine learning techniques.

Instead of predicting wildfire events directly, the problem is framed as a **risk-ranking task**, where geographic locations are prioritized based on wildfire risk.

The objective is to identify high-risk areas that account for a large proportion of wildfire events and support decision-making for monitoring and resource allocation.

---

## Data Sources

- MODIS FIRMS – satellite-based wildfire detections  
- gridMET – daily climate data (temperature, precipitation)  
- NLCD – vegetation / fuel data  
- Road network data – proxy for human activity  

**Time Range:** 2018–2023  
**Resolution:** Daily grid-level observations  

---

## Project Pipeline

1. Data Preparation  
   - Subset climate data for Colorado  
   - Process and align spatial wildfire data  

2. Label Generation  
   - Generate daily wildfire occurrence labels  
   - Validate label quality  

3. Feature Engineering  
   - Temporal features (lag, rolling precipitation)  
   - Seasonal features (day-of-year)  
   - Spatial features (fuel presence, distance to roads)  

4. Modeling  
   - Logistic Regression (baseline)  
   - Random Forest  
   - Gradient Boosting  
   - XGBoost  

5. Evaluation  
   - ROC-AUC (ranking performance)  
   - Risk-based evaluation (top-k fire capture)  

6. Dashboard  
   - Interactive visualization of wildfire risk  
   - Highlights high-risk regions over time  

---

## Notebooks

- **01_gridmet_data_subsetting.ipynb**  
  Prepares climate data for Colorado region  

- **02_fire_label_generation.ipynb**  
  Generates wildfire occurrence labels from MODIS data  

- **02_fire_label_validation.ipynb**  
  Validates and debugs wildfire labels  

- **03_feature_engineering_road_distance.ipynb**  
  Computes distance-to-road feature  

- **04_feature_engineering_vegetation.ipynb**  
  Extracts vegetation / fuel features  

- **05_feature_engineering_temporal_base.ipynb**  
  Creates lag and rolling climate features  

- **06_feature_engineering_full_dataset.ipynb**  
  Combines temporal and spatial features into final dataset  

- **07_modeling_and_dashboard_preparation.ipynb**  
  Trains models, evaluates performance, and prepares dashboard data  

---

## Key Results

- Tree-based models outperform linear models  
- XGBoost achieves highest ROC-AUC (~0.71)  
- Top 20% high-risk locations capture over 50% of wildfire events  
- Demonstrates strong effectiveness of risk-ranking approach  

---


The final model outputs are transformed into a filtered dataset containing top-risk locations.

Steps:
- Generate risk scores using trained model
- Select top N high-risk locations per day
- Assign risk tiers (Top 5%, 10%, 20%)
- Export dataset for visualization

This dataset is used in the interactive dashboard.


**Live Demo:**  
https://meek-fairy-c16886.netlify.app/

---

## Technologies Used

- Python (Pandas, NumPy)
- GeoPandas / Rasterio
- Scikit-learn
- XGBoost
- Matplotlib / Seaborn

---

## Project Objective

Identify high-risk wildfire regions and support decision-making using data-driven risk ranking instead of traditional classification.
