# Customer Churn Prediction Using Machine Learning and SHAP Explainability

## 1. Introduction

Customer churn refers to the loss of customers who discontinue using a company's services. For telecom companies, churn directly impacts revenue and customer lifetime value. This project aims to build a predictive model to identify customers likely to churn and to explain the model’s decisions using SHAP (SHapley Additive exPlanations). The goal is not only to achieve good predictive performance but also to ensure transparency and interpretability.

---

## 2. Objective

The primary objectives of this project are:

- To build a churn prediction model using machine learning techniques.
- To understand key drivers of churn using SHAP explainability.
- To generate actionable business insights from the predictions.
- To evaluate model performance using appropriate metrics.

---

## 3. Dataset Description

The project uses the Telco Customer Churn dataset.  
The target variable is `Churn` (Yes/No).

The dataset includes the following feature categories:

- Customer demographics (gender, senior citizen, dependents)
- Account information (tenure, contract type, payment methods)
- Services subscribed (internet, phone, streaming, tech support)
- Billing details (monthly charges, total charges)

The dataset is stored in:

data/Telco-Customer-Churn.csv


---

## 4. Methodology

### 4.1 Data Preprocessing

- Handling missing values  
- Encoding categorical variables  
- Scaling numerical features  
- Splitting the data into training and testing sets  
- Optional: Balancing classes (if required)

### 4.2 Model Training

The following machine learning models were explored:

- Logistic Regression  
- Random Forest  
- XGBoost  
- LightGBM  

LightGBM was selected as the final model due to its strong performance and faster training time.

The final trained model is saved as:

best_model.pkl


### 4.3 Model Evaluation

The model performance was evaluated based on:

- Accuracy  
- Precision  
- Recall  
- F1 Score  
- ROC-AUC  

Detailed evaluation metrics are available in:

Plots/oof_metrics.csv


---

## 5. SHAP Explainability

SHAP was used to understand both global and local behavior of the model.

### 5.1 Global Feature Importance

The SHAP summary plots show the most important features contributing to churn predictions.

Files:

Plots/shap_summary_bar.png
Plots/shap_summary_dot.png


Key influential features include:

- Contract type  
- Tenure  
- Monthly charges  
- Internet service  
- Tech support  

### 5.2 SHAP Dependence Analysis

Dependence plots illustrate how individual features influence the model output.

Files:

Plots/shap_dependence_Contract.png
Plots/shap_dependence_MonthlyCharges.png
Plots/shap_dependence_tenure.png


Insights:

- Month-to-month contract leads to higher churn.
- Higher monthly charges are associated with higher churn.
- Customers with shorter tenure are more likely to churn.

### 5.3 Local Explanations

Local SHAP values provide explanations for individual customers.  
Positive SHAP values indicate factors driving the prediction toward churn,  
while negative values reduce the likelihood of churn.

---

## 6. Key Insights

From the SHAP analysis and model behavior:

- Customers on month-to-month contracts are at the highest risk.
- Higher monthly charges significantly increase churn probability.
- Long-term customers (higher tenure) are more stable.
- Lack of technical support increases the risk of churn.
- Fiber optic internet customers show higher churn due to service issues.

These insights can help businesses design targeted retention strategies.

---

## 7. Conclusion

The project successfully built a machine learning model that predicts customer churn effectively. Using SHAP, the model's predictions were made interpretable at both global and local levels. The interpretability helps stakeholders understand key churn drivers and supports decision-making for customer retention.

This project combines predictive modeling and explainability to provide meaningful insights and practical recommendations for telecom companies.

---

