# EV Price Prediction with Advanced ML (Freelance Project)

**Author:** Muhammad Abdullah Jami  
**Role:** Freelance Data Scientist & Researcher  

---

## Table of Contents

1. [Introduction](#introduction)  
2. [Project Highlights](#project-highlights)  
3. [Abstract](#abstract)  
4. [Data & Features](#data--features)  
5. [Methodology](#methodology)  
6. [Model Evaluation](#model-evaluation)  
7. [Selected Model & Results](#selected-model--results)  
8. [How to Reproduce](#how-to-reproduce)  
9. [Project Structure](#project-structure)  
10. [Future Work](#future-work)  

---

## Introduction

This was a freelance engagement in which I gathered EV data, engineered features, trained and tuned multiple regression models, and authored the accompanying research summary. My goal was to deliver a turnkey solution that forecasts electric-vehicle prices with high accuracy.

---

## Project Highlights

- **Scope:** End-to-end price prediction pipeline for EVs  
- **Models Tested:** Linear Regression, Random Forest, XGBoost, SVR  
- **Hyperparameter Tuning:** Grid/Random search to optimize each model  
- **Metrics Used:** MAE, MSE, RMSE, R²  
- **Outcome:** XGBoost achieved R² = 0.90 & RMSE ≈ 8,986  

---

## Abstract

Growing environmental concerns are driving up EV adoption—and market prices are fluctuating rapidly. I trained four machine-learning regressors on user-provided EV attributes (e.g., battery size, range, brand) and compared performance. XGBoost emerged as the top performer (R² 0.90), while Random Forest offered the most stable results (R² 0.86–0.88). This turnkey freelance deliverable includes code, model artifacts, and a concise research paper documenting methods and findings.

---

## Data & Features

- **Source:** Client-provided CSV of EV listings  
- **Key Features:**  
  - Battery capacity (kWh)  
  - Range (km)  
  - Brand & Model (one-hot encoded)  
  - Power (kW)  
  - Year, Body type, Drivetrain, etc.  
- **Preprocessing:**  
  - Missing-value handling  
  - Categorical encoding  
  - Standard scaling of numeric columns  

---

## Methodology

1. **Exploratory Data Analysis**  
2. **Feature Engineering & Cleaning**  
3. **Train/Test Split**  
4. **Model Training & Tuning**  
   - **Linear Regression**  
   - **Random Forest Regressor**  
   - **XGBoost Regressor**  
   - **Support Vector Regression**  
5. **Performance Comparison**  
6. **Final Model Selection**  

---

## Model Evaluation

| Model                     | MAE      | MSE          | RMSE     | R² Score |
|---------------------------|----------|--------------|----------|----------|
| **Random Forest (best)**  | 4,865.43 | 60,615,169.17| 7,785.57 | 0.8764   |
| **XGBoost (best)**        | 5,282.66 | 80,744,404.57| 8,985.79 | 0.9000   |
| **Linear Regression**     | 8,373.08 |120,169,585.87|10,962.19 | 0.7550   |
| **SVR**                   |16,831.60 |491,494,574.28|22,169.68 | –0.002   |

---

## Selected Model & Results

- **Winner:** XGBoost (R² 0.90, RMSE ≈ 8,986)  
- **Example Prediction:**  
  - **Actual Price:** £35,683.85  
  - **Predicted Price:** £31,923.83  

I packaged the trained model, preprocessing pipeline, and inference script so the client can drop in new EV feature files and get instant price estimates.

---

## How to Reproduce

```bash
git clone https://github.com/Muhammad-Abdullah-Jami/EV_Price_Prediction.git
cd EV_Price_Prediction
pip install -r requirements.txt

# Train and evaluate all models
python src/train_models.py --data data/ev_data.csv

# Run predictions with the chosen model
python src/predict.py \
  --model xgboost \
  --input data/new_ev_features.csv \
  --output results/predicted_prices.csv
