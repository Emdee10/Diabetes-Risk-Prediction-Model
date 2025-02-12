# Diabetes-Risk-Prediction-Model
![image](https://github.com/user-attachments/assets/a5d3b04a-6fc3-41a8-bbb7-7345f8d91182)

This project develops a machine learning model to predict diabetes onset, enabling early detection and preventive measures. Using predictive analytics, it enhances patient outcomes and optimizes healthcare resources. It includes EDA, data preprocessing, feature engineering, model training, testing, and performance evaluation in Python.
Diabetes Prediction Model


## Introduction
![image](https://github.com/user-attachments/assets/993ca5bc-0e41-40c7-9767-e64376f8ce3b)

Diabetes is a chronic disease affecting millions worldwide, leading to severe health complications if not detected early. This project leverages machine learning to predict the likelihood of diabetes onset, enabling timely interventions and preventive measures.

## Problem Statement

Early detection of diabetes remains a challenge due to limitations in traditional diagnostic methods. The goal is to develop a predictive model that can accurately assess diabetes risk using patient health data, improving early detection and medical decision-making.

# Project Objective

The objective of this project is to build a machine learning model that:

Predicts the likelihood of diabetes onset.

Provides insights into key factors contributing to diabetes risk.

Enhances early diagnosis, leading to better patient outcomes.

## Rationale of the Project

With the increasing prevalence of diabetes, early detection is crucial for managing health risks and reducing long-term complications. This project aims to empower healthcare providers with predictive analytics to facilitate proactive medical interventions, ultimately improving patient care and optimizing resource allocation.

## Problem Definition

This project seeks to answer the following key questions:

Can machine learning be used to predict diabetes risk with high accuracy?

What are the most important predictors of diabetes onset?

How can predictive analytics be integrated into healthcare decision-making?

## Methodology (Steps)

The project follows these steps:

Data Collection & Cleaning: Load and preprocess patient health data.

Exploratory Data Analysis (EDA): Visualize key relationships and identify patterns.

Feature Engineering: Encode categorical variables and select relevant features.

Model Selection & Training: Train multiple supervised learning models.

Model Evaluation: Assess model performance using accuracy, precision, recall, F1-score, and AUC-ROC.

Deployment Considerations: Discuss potential integration into healthcare systems.

## Exploratory Data Analysis (EDA)

Age and diabetes risk: Older adults and elderly individuals have a higher likelihood of diabetes.

Blood glucose levels: High glucose readings (>250 mg/dL) strongly indicate diabetes.

BMI and diabetes: Obesity (BMI >30) is a major risk factor.

HbA1c as an indicator: Higher HbA1c values (>6%) correlate with diabetes risk.

Smoking and diabetes: Smokers show a higher incidence of diabetes, but further analysis is needed.

Gender and diabetes: Diabetes cases are observed in both males and females, with a slightly higher count in females. However, the difference may be due to dataset imbalance rather than biological factors.

Correlation analysis:

Blood glucose level and HbA1c show the strongest correlation with diabetes, making them key predictors.

Age and BMI also have moderate correlation with diabetes risk.

Hypertension and heart disease show weaker correlations but may still contribute to diabetes risk.

## Model Performance Evaluation

The model is evaluated using the following metrics:

Accuracy: Measures overall correctness.

Precision: Assesses false positives.

Recall: Evaluates false negatives.

F1-Score: Balances precision and recall.

AUC-ROC: Determines the model’s ability to distinguish between diabetic and non-diabetic cases.

Key Findings:

XGBoost and Random Forest performed best in terms of precision, minimizing false positives, but had a limitation of high false negatives, which can be fatal in medical cases.

Decision Tree had the best recall, reducing false negatives and identifying more actual diabetic cases, but resulted in higher false positives, which can be costly to healthcare providers.

## Model Optimization & Final Model Selection

To optimize the strengths of these models, an Ensemble Method – Stacking Classifier was selected as the final model.The Stacking Classifier effectively combines Decision Tree, Random Forest, and XGBoost to improve both precision and recall, striking a balance between minimizing false positives and false negatives.

Final Model Performance – Stacking Classifier

Accuracy: 97.25% (same as XGBoost, but with better balance)

Precision: 95.83% (high confidence in positive predictions)

Recall: 70.55% (significantly better than XGBoost and Random Forest alone)

AUC-ROC: 85.13% (robust classification ability)

This improvement reduces both false positives and false negatives, making it the best choice for healthcare integration.

## Recommendation

Deploy the Stacking Classifier as the final predictive model in healthcare systems.

Use explainability tools like SHAP or LIME to help medical professionals interpret predictions.

Integrate the model into Electronic Health Record (EHR) systems for real-time diabetes risk assessment.

Conduct further validation with clinical trials to enhance reliability before full deployment.

## Conclusion

This project developed a robust diabetes prediction model for Stark Health Clinic, leveraging machine learning to enable early detection and targeted prevention. 
The stacking model improves accuracy, enhancing patient outcomes, reducing costs, and optimizing healthcare resources. 
Further refinements will ensure seamless integration into Stark Health’s system, strengthening its proactive diabetes management.



