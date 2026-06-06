# Healthcare Machine Learning Analytics

## Overview

This repository contains healthcare machine learning projects focused on diabetes risk prediction using clinical healthcare datasets.

The project demonstrates end-to-end machine learning workflow including data preprocessing, model development, explainable AI (XAI), threshold optimization, and clinical risk prediction.

---

# Project Objectives

* Predict diabetes risk using clinical healthcare parameters
* Compare traditional and ensemble machine learning algorithms
* Evaluate model performance using clinically relevant metrics
* Improve model interpretability through Explainable AI (SHAP)
* Develop a patient-level risk prediction engine
* Support healthcare decision-making through predictive analytics

---

# Dataset

**Dataset:** Pima Indians Diabetes Dataset

Clinical variables used:

* Pregnancies
* Glucose
* Blood Pressure
* Skin Thickness
* Insulin
* BMI
* Diabetes Pedigree Function
* Age

**Target Variable:**

* Outcome (Diabetes: Yes / No)

---

# Project Modules

## 1. Logistic Regression for Diabetes Prediction

### Objective

Evaluate Logistic Regression performance for diabetes risk prediction using healthcare clinical parameters.

### Key Features

* Missing value handling
* Median imputation
* Feature scaling
* Pipeline preprocessing
* Threshold optimization
* Sensitivity and specificity analysis
* Clinical performance evaluation

### Performance

* ROC AUC: ~0.80
* MCC: ~0.58
* Good sensitivity for diabetes screening

---

## 2. Random Forest Classification for Diabetes Prediction

### Objective

Compare ensemble learning performance against Logistic Regression models.

### Key Features

* Random Forest Classification
* Pipeline preprocessing
* Cross-validation analysis
* Threshold optimization
* Feature importance analysis
* Clinical risk prediction

### Performance

* ROC AUC: ~0.94
* MCC: ~0.75
* Improved predictive performance over Logistic Regression

---

## 3. SHAP Explainable AI (XAI)

### Objective

Improve transparency and interpretability of machine learning predictions.

### Features

* SHAP Summary Plot
* SHAP Beeswarm Plot
* Global Feature Importance
* Local Patient-Level Explanation
* Clinical interpretation support

### Benefits

* Identifies the most influential clinical variables
* Explains model predictions
* Supports healthcare decision-making
* Enhances model trustworthiness

---

## 4. Diabetes Risk Prediction Engine

### Objective

Generate patient-level diabetes risk predictions using trained machine learning models.

### Input Parameters

* Glucose
* Blood Pressure
* BMI
* Insulin (Optional)

### Output

* Risk Probability
* Risk Percentage
* Prediction Status
* Risk Category
* Clinical Interpretation

### Risk Categories

| Risk Probability | Category      |
| ---------------- | ------------- |
| < 0.25           | Low Risk      |
| 0.25 – 0.50      | Moderate Risk |
| > 0.50           | High Risk     |

### Example Output

| Parameter       | Value         |
| --------------- | ------------- |
| Glucose         | 124           |
| Blood Pressure  | 70            |
| BMI             | 31.2          |
| Risk Percentage | 33.12%        |
| Prediction      | At Risk       |
| Risk Category   | Moderate Risk |

---

## 5. Prediction Logging System

### Features

* Automatic prediction history tracking
* CSV export
* Excel export
* Timestamp recording
* Prediction audit trail

Generated Files:

* diabetes_prediction_history.csv
* diabetes_prediction_history.xlsx

---

# Model Evaluation Metrics

The project evaluates models using:

* ROC AUC
* F1 Score
* Sensitivity
* Specificity
* Matthews Correlation Coefficient (MCC)
* Cohen Kappa
* Confusion Matrix
* Classification Report

---

# Technologies Used

* Python
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* SHAP
* OpenPyXL
* Jupyter Notebook

---

# Repository Structure

```text
datasets/
models/
notebooks/
outputs/
reports/
scripts/
```

---

# Healthcare Analytics Focus

This repository is part of ongoing work in:

* Healthcare Analytics
* Clinical Laboratory Intelligence Systems
* Predictive Healthcare Modeling
* Explainable AI in Healthcare
* Clinical Decision Support Systems
* Operational Healthcare Analytics

---

# Future Enhancements

* Streamlit Web Application
* XGBoost Implementation
* Patient PDF Reports
* Model Monitoring Dashboard
* Multi-Disease Risk Prediction
* Clinical Risk Stratification Engine

## Clinical Safety and Validation Documentation

This project includes additional healthcare ML documentation to describe model risks, clinical limitations, and validation requirements.

- [Model Card](reports/model_card.md)
- [Clinical Limitations](reports/clinical_limitations.md)
- [Validation Summary](reports/validation_summary.md)

This model is an educational healthcare ML prototype and is not intended for clinical diagnosis, treatment, or direct patient care.

# Clinical Use Statement: For educational demonstration only. Not intended for diagnosis, treatment, or independent clinical decision-making.

---

# Author

## Dr. P. Ragavendran

Clinical Laboratory Operations
Healthcare Analytics
Clinical Intelligence Systems
Machine Learning in Healthcare
