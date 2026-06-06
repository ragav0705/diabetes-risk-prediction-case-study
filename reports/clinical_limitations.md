# Clinical Limitations: Diabetes Risk Prediction Project

## 1. Purpose of This Document

This document explains the clinical limitations of the diabetes risk prediction model.

Healthcare machine learning models require careful evaluation beyond accuracy. A model may perform well on a public dataset but still fail in real-world clinical practice.

---

## 2. Dataset Limitations

The Pima Indians Diabetes Dataset is useful for machine learning education, but it has several limitations:

- It is a small public dataset
- It represents a specific population group
- It may not generalize to broader Indian or global populations
- It does not include all clinically important diabetes risk factors
- It may not reflect current diagnostic practices
- It does not include laboratory assay variation
- It does not include healthcare access, lifestyle, medication, or comorbidity details

Because of these limitations, the model should not be considered clinically validated.

---

## 3. Missing Clinical Variables

Important clinical variables are not available in the dataset, such as:

- HbA1c
- Fasting plasma glucose status
- Random glucose context
- Oral glucose tolerance test result
- Family history details
- Medication history
- Comorbidities
- Lipid profile
- Blood pressure treatment status
- Lifestyle factors
- Diet and physical activity
- Socioeconomic factors

The absence of these variables limits the clinical usefulness of the model.

---

## 4. Screening Risk

If the model is considered as a screening prototype, false negatives are a major concern.

A false negative means the model predicts low risk when the patient may actually be high risk.

This could delay further clinical evaluation.

Therefore, sensitivity is important in this use case.

However, false positives are also important because they may lead to unnecessary follow-up testing, increased workload, and patient anxiety.

---

## 5. Threshold Limitations

The risk threshold used by the model is not clinically validated.

Threshold optimization based only on model performance metrics may not be appropriate for real healthcare use.

A real clinical threshold should consider:

- Clinical guidelines
- Disease prevalence
- Cost of false negatives
- Cost of false positives
- Screening workflow
- Physician review
- Patient safety
- Resource availability

---

## 6. Explainability Limitations

SHAP and feature importance methods help explain model behavior, but they do not prove causation.

For example, if glucose has high importance, this means glucose strongly influenced the model prediction. It does not mean the model has discovered a new clinical relationship.

Explainability outputs should be reviewed with clinical knowledge.

---

## 7. Bias and Generalizability

The model may perform differently across patient groups.

Potential subgroup concerns include:

- Age groups
- Sex
- Ethnicity
- Pregnancy status
- BMI categories
- Geographic populations
- Socioeconomic groups
- Patients with comorbidities

Subgroup performance analysis is required before real-world use.

---

## 8. Deployment Limitation

This model is not deployment-ready.

Before deployment, the following would be required:

- External validation
- Calibration testing
- Bias assessment
- Data privacy review
- Human-in-the-loop clinical workflow
- Monitoring for model drift
- Documentation of model version
- Institutional governance approval

---

## 9. Final Statement

This project is a healthcare ML portfolio project and educational prototype.

It should not be used for clinical diagnosis, treatment decisions, or direct patient care.