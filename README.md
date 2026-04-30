# Wildfire Ignition Risk Prediction (Colorado)

This repository contains the complete code, analysis, visualizations, and final report for my Data Science Practicum project.

Wildfires are a major environmental and public safety concern in Colorado, where ignition events are strongly influenced by climate and weather conditions. Predicting the exact time and location of wildfire ignitions is extremely difficult because these events are rare and depend on complex environmental factors. Instead of focusing on exact prediction, this project treats wildfire ignition as a **risk‑ranking problem**, with the goal of identifying locations that are relatively more prone to ignition under certain climate conditions.

The objective of this project is to use climate data and machine learning models to rank locations in Colorado by wildfire ignition risk in a way that is practical, interpretable, and able to generalize to unseen future data.

---

## Project Summary
- **Study area:** Colorado  
- **Time period:** 2018–2023  
- **Problem type:** Rare‑event risk ranking  
- **Approach:** Climate‑based machine learning models  
- **Outcome:** High‑risk locations identified by the model capture a disproportionate share of wildfire ignitions  

This project emphasizes decision support rather than exact prediction, which better aligns with real‑world wildfire monitoring and resource prioritization.

---

## Data Sources
The project uses publicly available datasets that are commonly used in wildfire and climate research:

- **NASA MODIS FIRMS**  
  Satellite‑detected wildfire ignition locations derived from thermal anomaly observations.  
  Data access details are described in `Data/README.md`.

- **gridMET Climate Data**  
  Daily gridded climate variables including precipitation and temperature at high spatial resolution.  
  Data access details are described in `Data/README.md`.

Due to data size constraints, raw datasets are not stored directly in this repository.

---

## Methods Overview
The project follows a structured data science workflow designed to handle large datasets and extreme class imbalance:

- Data acquisition and preprocessing (`Notebooks/01_data_acquisition_and_eda.ipynb`)  
- Exploratory data analysis to examine rarity, seasonality, and climate relationships  
- Feature engineering, including lagged precipitation, rolling precipitation sums, and seasonal indicators (`Notebooks/02_feature_engineering.ipynb`)  
- Model training using Logistic Regression, Gradient Boosting, Random Forest, and XGBoost (`Notebooks/Model_Training_And_Evaluation.ipynb`)  
- Evaluation using risk‑ranking metrics on an unseen test year (2023)  

Models were trained on data from 2018–2022 and evaluated on 2023 to assess temporal generalization.

---

Wildfire-Ignition-Risk-Practicum/
│
├── data/                     
│   └── README.md             
│
├── notebooks/                
│   ├── 01_data_acquisition_eda.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_modeling.ipynb
│
├── src/                      
│   └── README.md
│
├── figures/                 
│   ├── gradient_boosting.png
│   ├── high_risk_locations.png
│   └── README.md
│
├── report/                  
│   ├── wildfire_risk.tex
│   ├── references.bib
│   └── README.md
│
├── requirements.txt          
├── README.md               
