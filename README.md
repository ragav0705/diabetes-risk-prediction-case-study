# Healthcare Machine Learning Analytics

## Overview

This repository contains healthcare machine learning projects focused on diabetes risk prediction using the Pima Indians Diabetes Dataset.

The project demonstrates an end-to-end healthcare ML workflow: data cleaning, preprocessing, model training, model comparison, threshold optimization, explainable AI using SHAP, patient-level diabetes risk prediction, and prediction-history logging.

> **Clinical Safety Statement:** This project is an educational healthcare ML prototype. It is not intended for diagnosis, treatment, or independent clinical decision-making.

---

## Project Objectives

- Predict diabetes risk using clinical healthcare parameters
- Compare Logistic Regression and Random Forest classification models
- Apply preprocessing pipelines for missing-value handling and feature scaling
- Evaluate model performance using clinically relevant metrics
- Optimize classification threshold for diabetes-risk screening
- Use SHAP explainability to support model interpretation
- Build a patient-level diabetes risk prediction function
- Maintain prediction history using CSV and Excel outputs

---

## Dataset

**Dataset:** Pima Indians Diabetes Dataset

### Input Variables

- Pregnancies
- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI
- Diabetes Pedigree Function
- Age

### Target Variable

- Outcome  
  - `0` = No diabetes
  - `1` = Diabetes

### Data Cleaning Approach

In the notebooks, clinically invalid zero values are treated as missing values for selected variables:

- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI

Missing values are handled using median imputation. Pipeline-based notebooks use `SimpleImputer` and `StandardScaler` inside a `ColumnTransformer`.

---

## Notebook Modules

### 1. Logistic Regression Diabetes Prediction

**Notebook:** `Logistic_Regression_Diabetes.ipynb`

#### Purpose

To evaluate Logistic Regression for diabetes-risk prediction using both non-pipeline and pipeline-based approaches.

#### Main Steps

- Load Pima Indians Diabetes Dataset
- Remove duplicate records
- Replace invalid zero values with missing values
- Apply median imputation
- Apply feature scaling using `StandardScaler`
- Train Logistic Regression model
- Generate predicted probability
- Identify best threshold using F1 score
- Evaluate model using clinical classification metrics
- Save summary tables and plots to the `outputs/` folder

#### Generated Outputs

- `logistic_regression_summary.csv`
- `logistic_confusion_matrix_without_pipeline.png`
- `logistic_confusion_matrix_with_pipeline.png`
- `logistic_classification_report_without_pipeline.png`
- `logistic_classification_report_with_pipeline.png`

---

### 2. Random Forest Classifier

**Notebook:** `Random_forest_classifier.ipynb`

#### Purpose

To compare Random Forest performance against Logistic Regression and build a stronger diabetes-risk prediction model.

#### Main Steps

- Train Random Forest without pipeline
- Train Random Forest with preprocessing pipeline
- Use `StratifiedKFold` cross-validation
- Calculate ROC AUC and F1 cross-validation scores
- Optimize classification threshold using precision-recall results
- Evaluate sensitivity, specificity, MCC, balanced accuracy, and Cohen Kappa
- Generate feature-importance outputs
- Save confusion matrices and classification report images
- Build SHAP explainability outputs
- Build patient-level diabetes risk prediction function
- Save prediction history in CSV and Excel format

#### Generated Outputs

- `random_forest_without_pipeline_summary.csv`
- `random_forest_with_pipeline_summary.csv`
- `random_forest_without_pipeline_feature_importance.csv`
- `random_forest_with_pipeline_feature_importance.csv`
- `confusion_matrix_without_pipeline.png`
- `confusion_matrix_with_pipeline.png`
- `classification_report_without_pipeline.png`
- `classification_report_with_pipeline.png`
- `shap_explainability_summary.csv`
- `shap_beeswarm_plot.png`
- `shap_bar_plot.png`
- `diabetes_prediction_history.csv`
- `diabetes_prediction_history.xlsx`

---

### 3. Random Forest Threshold Optimization

**Notebook:** `Random_forest_classifier_model_improvement.ipynb`

#### Purpose

To test multiple probability thresholds and identify a clinically useful cutoff for diabetes-risk classification.

#### Main Steps

- Train Random Forest pipeline model
- Calculate predicted probabilities
- Test thresholds from `0.10` to `0.90`
- Calculate sensitivity, specificity, precision, F1 score, MCC, Youden Index, false positives, and false negatives
- Identify the best threshold using Youden Index
- Save threshold optimization results

#### Generated Outputs

- `random_forest_threshold_output.csv`
- `threshold_optimization_results.png`
- `best_threshold_youden_index.png`

---

## Diabetes Risk Prediction Engine

The Random Forest notebook includes a patient-level prediction function:

```python
predict_diabetes_risk(
    age,
    glucose,
    blood_pressure,
    bmi,
    insulin=None,
    pregnancies=None,
    skin_thickness=None,
    diabetes_pedigree_function=None,
    threshold=0.25
)
```

### Required Inputs

- Age
- Glucose
- Blood Pressure
- BMI

### Optional Inputs

- Insulin
- Pregnancies
- Skin Thickness
- Diabetes Pedigree Function

When optional values are not provided, the function uses the dataset median value.

### Prediction Output

- Age
- Glucose
- Blood Pressure
- BMI
- Insulin status
- Risk Probability
- Risk Percentage
- Threshold Used
- Prediction
- Risk Category
- Advice / Interpretation

### Risk Category Logic Used in Notebook

| Risk Probability | Category |
|---:|---|
| `< 0.25` | Normal / Low Risk |
| `0.25 – < 0.40` | Prediabetic / Moderate Risk |
| `>= 0.40` | Diabetic / High Risk |

### Example Input Used in Notebook

```python
result = predict_diabetes_risk(
    age=39,
    glucose=128,
    blood_pressure=70,
    bmi=24,
    insulin=None
)
```

---

## Model Evaluation Metrics

The notebooks evaluate model performance using:

- Confusion Matrix
- Classification Report
- ROC AUC
- F1 Score
- Sensitivity / Recall
- Specificity
- Precision
- Balanced Accuracy
- Matthews Correlation Coefficient (MCC)
- Cohen Kappa
- Youden Index
- False Positives
- False Negatives

---

## Explainable AI

SHAP explainability is implemented in the Random Forest notebook.

### SHAP Outputs

- SHAP debug summary
- Random Forest transformed feature importance
- SHAP original feature importance
- Constant transformed feature check
- SHAP beeswarm plot
- SHAP bar plot

### Purpose

SHAP is used to understand which clinical variables contribute most strongly to the model's diabetes-risk prediction.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib
- SHAP
- OpenPyXL
- Jupyter Notebook

---

## Suggested Repository Structure

```text
diabetes-risk-prediction-analysis/
│
├── datasets/
│   └── diabetes_pima_indian.csv
│
├── notebooks/
│   ├── Logistic_Regression_Diabetes.ipynb
│   ├── Random_forest_classifier.ipynb
│   └── Random_forest_classifier_model_improvement.ipynb
│
├── outputs/
│   ├── model summaries
│   ├── confusion matrix images
│   ├── classification report images
│   ├── feature importance files
│   ├── SHAP outputs
│   └── prediction history files
│
├── reports/
│   ├── model_card.md
│   ├── clinical_limitations.md
│   └── validation_summary.md
│
└── README.md
```

---

## Current Project Status

Completed:

- Logistic Regression model
- Random Forest model
- Pipeline preprocessing
- Threshold optimization
- Feature importance analysis
- SHAP explainability
- Patient-level risk prediction function
- Prediction-history logging

Planned / Future Enhancements:

- XGBoost classifier
- Streamlit web application
- PDF patient risk reports
- Model monitoring dashboard
- Multi-disease prediction engine
- External validation using additional datasets
- Model calibration analysis

---

## Clinical Limitations

This project should not be used as a standalone clinical decision system.

Important limitations:

- The dataset is limited and may not represent all populations.
- The model predicts statistical risk, not confirmed diagnosis.
- Clinical diagnosis requires medical history, symptoms, laboratory confirmation, and physician interpretation.
- Thresholds must be validated before real clinical use.
- External validation is required before deployment in any healthcare environment.

---

## Author

**Dr. P. Ragavendran**

Clinical Laboratory Operations  
Healthcare Analytics  
Clinical Intelligence Systems  
Machine Learning in Healthcare
