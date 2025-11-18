# Telco Customer Churn Prediction with SHAP Explainability

This project builds a machine learning model to predict customer churn and explains the predictions using SHAP (SHapley Additive exPlanations). The goal is to achieve both high predictive accuracy and deep interpretability to understand why customers are likely to churn.

---

## 1. Project Overview

Customer churn is a major challenge for telecom companies.  
This project focuses on:

- Training a churn prediction model using the Telco Customer Churn dataset
- Identifying the key factors influencing churn
- Using SHAP to explain predictions at both global and local levels
- Generating insights that can support business decisions and customer retention strategies

---

## 2. Repository Structure

📁 telco-churn-shap-analysis/
│
├── 📁 Plots/
│ ├── shap_summary_bar.png
│ ├── shap_summary_dot.png
│ ├── shap_dependence_Contract.png
│ ├── shap_dependence_MonthlyCharges.png
│ ├── shap_dependence_tenure.png
│ ├── gini_gain_importances.csv
│ ├── shap_global_importance.csv
│ └── oof_metrics.csv
│
├── 📁 data/
│ └── Telco-Customer-Churn.csv
│
├── churn_shap_telco.ipynb
├── best_model.pkl
├── requirements.txt
├── report.md
└── README.md
---

## 3. Dataset Description

Dataset used: **Telco Customer Churn**  
Target variable: **Churn** (Yes/No)

Features include:

- Customer demographics  
- Contract and billing information  
- Internet and phone services  
- Usage metrics and tenure  
- Monthly and total charges  

---

## 4. Methodology

### 4.1 Data Preprocessing
- Handling missing values  
- Label encoding categorical variables  
- Scaling numerical features  
- Train-test splitting  
- Optional class balancing  

### 4.2 Model Training
Machine learning models considered:

- Logistic Regression  
- Random Forest  
- XGBoost  
- LightGBM (Selected as best model)

The final trained model is saved as:

best_model.pkl


### 4.3 Model Evaluation
Model performance is evaluated using:

- Accuracy  
- Precision  
- Recall  
- F1 Score  
- ROC-AUC  

Detailed metrics are available in:

Plots/oof_metrics.csv


---

## 5. SHAP Explainability

SHAP is used to interpret how each feature contributes to the prediction.

### 5.1 Global Explanations

Global importance plots show which features are most responsible for churn predictions.

Files:
Plots/shap_summary_bar.png
Plots/shap_summary_dot.png
Plots/shap_global_importance.csv


### 5.2 Dependence Analysis

Dependence plots highlight how individual features interact with the model output.

Files:
Plots/shap_dependence_Contract.png
Plots/shap_dependence_MonthlyCharges.png
Plots/shap_dependence_tenure.png


### 5.3 Local Explanations

SHAP values are also used to explain individual customer predictions, helping identify specific churn drivers.

---

## 6. Key Insights

- Month-to-month contract customers show the highest churn probability  
- Higher monthly charges significantly increase churn risk  
- Customers with low tenure are more likely to leave  
- Lack of tech support and unreliable internet services contribute to churn  

---

## 7. How to Run the Project

### Step 1: Clone the repository
```bash
git clone https://github.com/your-username/telco-churn-shap-analysis.git
cd telco-churn-shap-analysis

Step 2: Install dependencies
pip install -r requirements.txt

Step 3: Open and run the Jupyter Notebook
jupyter notebook churn_shap_telco.ipynb

