# Diabetes-Risk-Prediction-Model
![image](https://github.com/user-attachments/assets/a5d3b04a-6fc3-41a8-bbb7-7345f8d91182)

This project develops a machine learning model to predict diabetes onset, enabling early detection and preventive measures. Using predictive analytics, it enhances patient outcomes and optimizes healthcare resources. It includes EDA, data preprocessing, feature engineering, model training, testing, and performance evaluation in Python.
Diabetes Prediction Model


## Introduction
![image](https://github.com/user-attachments/assets/993ca5bc-0e41-40c7-9767-e64376f8ce3b)

Diabetes, a chronic disease affecting millions worldwide, can lead to severe health complications if not detected early. Stark Health Clinic, a leading healthcare provider, leverages technology and predictive modeling to enhance its operations. By integrating machine learning into its systems, the clinic identifies diseases early, thereby improving patient outcomes and resource allocation. In line with this commitment, our project utilizes machine learning to predict the likelihood of diabetes onset, enabling timely interventions and preventive measures.


## Problem Statement

Early detection of diabetes remains a challenge due to limitations in traditional diagnostic methods. The goal is to develop a predictive model that can accurately assess diabetes risk using patient health data, improving early detection and medical decision-making.

## Project Objective

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


## Data Collection & Cleaning
Load and preprocess patient health data.
![mssg val vis](https://github.com/user-attachments/assets/55430f64-1680-46f0-8976-2547954ee77c)

## Exploratory Data Analysis (EDA): Visualize key relationships and identify patterns.
### Key insight
Age Group: Older adults (above 65) have a higher proportion of diabetes cases.
![age group by target vis](https://github.com/user-attachments/assets/2e015873-f42c-4c7a-9be3-5f5efb9cc8af)

BMI: Higher BMI correlates with diabetes risk.

Blood Glucose & HbA1c: Elevated levels strongly link to diabetes.
![blood glucose boxplot](https://github.com/user-attachments/assets/4490f47e-53ff-4b38-8acc-a9a20529eeb2)
![HbA1c boxplot](https://github.com/user-attachments/assets/e604d35d-3de1-42b0-a627-4f59d7a20400)
![bmi boxplot](https://github.com/user-attachments/assets/e30ee802-fecf-4fe7-a0ef-f34160f97672)

Smoking: Former smokers show a slightly higher diabetes risk than current smokers.
![smoking his by target vis](https://github.com/user-attachments/assets/189b3e7f-3c8e-4084-8036-03e6cbbe379b)

Hypertension & Heart Disease: Both conditions increase diabetes risk.
![hypertension](https://github.com/user-attachments/assets/9f89a771-2959-4ff1-98f8-c1ad5fd8907d)
![Heart disease ](https://github.com/user-attachments/assets/7fd7c6e7-f0e8-4a5e-98d4-21ae858158dd)

Gender and diabetes: Diabetes cases are observed in both males and females, with a slightly higher count in females. However, the difference may be due to dataset imbalance rather than biological factors.
![gender by target vis](https://github.com/user-attachments/assets/d08b96dc-5110-4a55-a79c-f2e95cd6b998)

### Correlation analysis:

Blood glucose level and HbA1c show the strongest correlation with diabetes, making them key predictors.

Age and BMI also have moderate correlation with diabetes risk.

Hypertension and heart disease show weaker correlations but may still contribute to diabetes risk.
![numerical corr vis](https://github.com/user-attachments/assets/de81b795-9c3e-4d4b-bd17-cbc9cb69bbb6)

## Data Balancing with SMOTE
### The Challenge: Imbalanced Data
Original data had a majority of non-diabetes cases.
![target before sampling](https://github.com/user-attachments/assets/ce6e59d7-2481-44e2-9cea-b2b74a90e381)

Imbalance skews model learning would be bias to the majority class.

The Solution: To treat the class imbalance, SMOTE is applied. The dataset was more balanced by oversampling the minority class (diabetic cases), ensuring models received enough examples to learn meaningful patterns.
![target after SMOTE](https://github.com/user-attachments/assets/2c07929a-2fe8-48f4-9ea2-89269e782a7a)

After applying SMOTE, the class distribution became much more balanced, improving models' ability to detect diabetic cases (increased recall across all models).

## Model Performance Evaluation
### Models Evaluated After SMOTE
The model is evaluated using the following metrics:

Accuracy: Measures overall correctness.

Precision: Assesses false positives.

Recall: Evaluates false negatives.

F1-Score: Balances precision and recall.

AUC-ROC: Determines the model’s ability to distinguish between diabetic and non-diabetic cases.

Key Findings:

XGB Classifier achieved the highest accuracy (97.11%) and precision (93.60%), meaning it is excellent at correctly identifying non-diabetic cases, but it missed a notable proportion of actual diabetic patients (lower recall).
![3](https://github.com/user-attachments/assets/9f11cc90-05d0-42ea-9f9b-fc72d5db4821)


Random Forest provided a strong balance between precision (81.81%) and recall (72.42%), making it reliable for both identifying diabetics and minimizing false positives.
![2](https://github.com/user-attachments/assets/0f3b0196-a19e-421d-90bc-e94c84dbd98d)

Decision Tree excelled in recall (74.59%), detecting more diabetic cases than others, but at the cost of precision (67.44%), meaning more false alarms.
![4](https://github.com/user-attachments/assets/08e58d95-f19f-466b-8b4e-840af94bba21)

SGD Classifier had the highest recall (82.85%), meaning it detected the most diabetic cases, but it suffered from poor precision (47.64%), leading to too many false positives.
![1](https://github.com/user-attachments/assets/10711b9a-4b5a-4841-973a-5b9c1e6d67a9)


![smt accuracy](https://github.com/user-attachments/assets/7fc872cb-0f42-4f95-8f7c-49b812bc4dfc)

![smt precision](https://github.com/user-attachments/assets/7f7e0217-5edc-46dc-aa51-0c28bf0a7feb)

![smt recall](https://github.com/user-attachments/assets/2caf6bc4-1864-4c07-9a65-0dc8d9cf1c25)

![smt aucroc](https://github.com/user-attachments/assets/7633ee10-9f85-4324-a452-ef2921e819ce)



## Model Optimization & Final Model Selection

To optimize the strengths of these models, an Ensemble Method – Stacking Classifier was selected as the final model.The Stacking Classifier effectively combines Decision Tree, Random Forest, and XGBoost to improve both precision and recall, striking a balance between minimizing false positives and false negatives.

![eval](https://github.com/user-attachments/assets/551eca3a-250d-4dbf-872b-c83d93c8ff2a)

#### Final Model: Stacking Classifier

Base Models: Decision Tree, Random Forest, XGBoost

Meta Model: Logistic Regression

Performance:

Accuracy: 96.59%

Precision: 83.09%

Recall: 75.35%

F1-score: 79.03%

AUC-ROC: 86.96%

Stacking Classifier (combining Decision Tree, Random Forest, and XGB) offered the best overall balance — high accuracy (96.59%), strong precision (83.09%), and improved recall (75.35%). It’s the recommended model for deployment.

![5](https://github.com/user-attachments/assets/390f7737-73c0-4342-93b1-8b07f8886dcf)

This improvement reduces both false positives and false negatives, making it the best choice for healthcare integration.

## Recommendation

Deploy the Stacking Classifier as the final predictive model in healthcare systems.

Regularly update the data with model for risk prediction

Integrate the model into Electronic Health Record (EHR) systems for real-time diabetes risk assessment.

Conduct further validation with clinical trials to enhance reliability before full deployment.

## Conclusion

This project developed a robust, balanced and highly accurate diabetes prediction model for Stark Health Clinic, leveraging machine learning to enable early detection and targeted prevention. 
The stacking classifier improves accuracy and achieve high predictive power, enhancing patient outcomes, reducing costs, and optimizing healthcare resources. 
Further refinements will ensure seamless integration into Stark Health’s system, strengthening its proactive diabetes management.



