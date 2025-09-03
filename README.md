# Waze Churn Analysis

This repository contains a Power BI dashboard screenshot and Python code for analyzing user churn in the Waze dataset, combining predictive modeling with interactive visualizations.

## Overview

- **Dataset**: `waze_dataset.csv` contains 14,999 rows and 13 columns, including user metrics like `activity_days`, `driven_km_drives`, `n_days_after_onboarding`, and `label` (retained/churned).
- **Objective**: Predict user churn and identify key drivers using machine learning, with insights visualized in a Power BI dashboard.
- **Key Findings**: 
  - Low `activity_days` and `driven_km_drives` are strong predictors of churn.
  - Retained users show higher engagement with favorite navigation routes.
  - iPhone and Android users exhibit similar churn rates, with iPhone users slightly more prevalent.
  - Engagement trends vary by device type over time.

## Python Analysis

The Python code performs the following:

1. **Data Preprocessing**:
   - Loaded `waze_dataset.csv` and dropped 700 rows with missing `label` values.
   - Encoded `label` as 0 (retained) and 1 (churned).
   - Encoded `device` as 1 (iPhone) and 0 (Android).
   - Scaled numeric features using `StandardScaler`.

2. **Modeling**:
   - Built Logistic Regression, Naïve Bayes, and Voting Ensemble models using scikit-learn.
   - Achieved ~80% accuracy with Logistic Regression, identifying `activity_days` and `driven_km_drives` as top predictors.
   - Evaluated performance with `classification_report` and `confusion_matrix`.

3. **Output**:
   - Saved cleaned data as `cleaned_waze_dataset.csv` for Power BI use.

The code is structured to handle the dataset's imbalanced nature and provides actionable insights for retention strategies.

<img width="1321" height="751" alt="image" src="https://github.com/user-attachments/assets/eb353556-d147-4f2f-ac4b-1e9e634bae70" />

## Power BI Dashboard

The dashboard visualizes the analysis with three interactive components :

- **Engagement Trend by Retention Status** (Line Chart): Shows average `activity_days` over `n_days_after_onboarding`, with "retained" and "churned" labels at endpoints.
- **Device Distribution by Churn Status** (Pie Chart): Displays the proportion of iPhone vs. Android users by churn status.
- **Average Activity Days Trend by Device Type** (Area Chart): Illustrates how iPhone and Android users’ activity trends diverge over time.

## Files

- `waze_dataset.csv`: Raw dataset.
- `cleaned_waze_dataset.csv`: Preprocessed data after Python cleaning.
- `code.ipynb`: Jupyter Notebook with Python analysis and modeling.
- `dashboard.png`: Screenshot of the Power BI dashboard.

## Instructions

1. **Clone the Repository**:
   - Run `git clone https://github.com/yourusername/Waze-Churn-Analysis.git` in your terminal.
2. **Explore the Code**:
   - Open `code.ipynb` in Jupyter Notebook to review the analysis, preprocessing, and modeling steps.
3. **View the Dashboard**:
   - Check `dashboard.png` for a static view of the Power BI dashboard.
4. **Reproduce Results**:
   - Install required Python libraries via `pip install -r requirements.txt`.

## Recommendations

Based on the analysis:
- Boost early engagement with onboarding tutorials and rewards for `activity_days` > 10.
- Enhance navigation features to increase `driven_km_drives`.
- Target low-engagement users within 30 days of onboarding.

## Acknowledgments

- Dataset provided by Kaggle (https://www.kaggle.com/datasets/mostafamohammednouh/waze-synthetic-user-churn-data).
- Built with Python, scikit-learn, and Power BI.
