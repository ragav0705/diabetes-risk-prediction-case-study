# Model Card: Diabetes Risk Prediction Model

## 1. Model Overview

This project builds a machine learning prototype for diabetes risk prediction using structured clinical parameters from the Pima Indians Diabetes Dataset.

The model is designed as an educational healthcare machine learning project to demonstrate classification, threshold optimization, model evaluation, and explainability.

This model is not intended for clinical diagnosis, treatment decisions, or direct patient care.

---

## 2. Intended Use

The intended use of this model is:

- Educational demonstration of healthcare machine learning workflow
- Diabetes risk prediction prototype
- Comparison of baseline and ensemble ML models
- Demonstration of sensitivity, specificity, ROC-AUC, MCC, and explainability
- Portfolio project for healthcare analytics and clinical data science learning

---

## 3. Not Intended Use

This model should not be used for:

- Clinical diagnosis of diabetes
- Treatment planning
- Replacing physician or clinician judgment
- Direct patient-facing decision-making
- Automated clinical decision support
- Deployment in hospital, laboratory, or public health systems without external validation

---

## 4. Dataset

Dataset used:

- Pima Indians Diabetes Dataset

Features:

- Pregnancies
- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI
- Diabetes Pedigree Function
- Age

Target variable:

- Diabetes outcome

---

## 5. Model Type

Models evaluated:

- Logistic Regression
- Random Forest Classifier

The Logistic Regression model was used as an interpretable baseline.

The Random Forest model was used to evaluate whether a non-linear ensemble model could improve predictive performance.

---

## 6. Performance Metrics

The model was evaluated using clinically relevant classification metrics:

- ROC-AUC
- Accuracy
- Sensitivity / Recall
- Specificity
- Precision
- F1-score
- Matthews Correlation Coefficient
- Cohen’s Kappa
- Confusion Matrix

In healthcare screening, sensitivity is important because false negatives may delay further clinical evaluation.

Specificity is also important because excessive false positives can increase unnecessary follow-up testing and patient anxiety.

---

## 7. Explainability

Explainability methods used:

- Feature importance
- SHAP global explanation
- SHAP patient-level explanation

Explainability was included to understand which clinical variables influenced model predictions.

Important clinical predictors included:

- Glucose
- BMI
- Age
- Insulin

These findings are consistent with known diabetes risk factors, but they should not be interpreted as causal conclusions.

---

## 8. Data Leakage Prevention

To reduce data leakage risk:

- The dataset was split into training and test sets before preprocessing
- Imputation was fitted only on training data
- Scaling was fitted only on training data
- Scikit-learn pipelines were used where applicable
- The target variable was not used for imputing missing feature values

Any preprocessing step that uses the target variable to modify input features should be avoided because it can artificially inflate model performance.

---

## 9. Clinical Risks

Potential clinical risks include:

- False negatives: high-risk patients may be missed
- False positives: low-risk patients may be incorrectly flagged
- Dataset bias due to population-specific data
- Poor generalization to other ethnic, geographic, or clinical populations
- Risk threshold not clinically validated
- Model probability may not be well calibrated
- Missing real-world clinical variables such as HbA1c, fasting status, medication history, and comorbidities

---

## 10. Limitations

This project has important limitations:

- Small dataset size
- Public benchmark dataset
- Population-specific data
- No external validation
- No prospective clinical validation
- No calibration assessment yet
- No subgroup fairness analysis yet
- No integration with real laboratory information systems
- Not validated on Indian diagnostic laboratory data

---

## 11. Governance Requirements Before Deployment

Before any real-world clinical or laboratory use, the model would require:

- External validation on representative patient data
- Clinical review by qualified healthcare professionals
- Bias and subgroup performance analysis
- Calibration testing
- Data privacy and security review
- Model monitoring plan
- Version control
- Audit trail
- Regulatory and institutional approval
- Clear human-in-the-loop workflow

---

## 12. Final Clinical Statement

This model is a healthcare machine learning prototype for educational and portfolio purposes only.

It should not be used for diagnosis, treatment, or independent clinical decision-making.