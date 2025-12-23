Customer Churn Prediction Project
Project Motivation

Customer churn is a major concern for subscription-based businesses. Predicting which customers are likely to leave allows companies to take proactive measures and improve customer retention.

Overview

This is an end-to-end Customer Churn Prediction project using Python and Pandas. The project includes:

Data cleaning and preprocessing

Exploratory Data Analysis (EDA) with multiple visualizations

Building and evaluating a Logistic Regression model

Identifying top features impacting churn

Saving the trained model for future use

Dataset

Source: Telco Customer Churn dataset

Number of Rows: 7043

Number of Columns: 21

Target Column: Churn (Yes = 1, No = 0)

Churn Distribution:

No: 5174 (~73.5%)

Yes: 1869 (~26.5%)

Libraries Used
pandas, numpy, matplotlib, seaborn, scikit-learn, joblib

Steps Followed

Data Loading & Cleaning

Loaded CSV dataset in Colab

Converted TotalCharges from object → numeric

Filled missing values with median

Exploratory Data Analysis (EDA)

Churn distribution (Bar & Pie charts)

Gender, SeniorCitizen, Contract, PaymentMethod vs Churn

Tenure, MonthlyCharges, TotalCharges analysis

Correlation analysis and scatter plots

Data Preparation

Dropped customerID

One-hot encoded categorical variables

Split dataset into training (80%) and test (20%) sets

Modeling

Built Logistic Regression model

Predicted churn on test set

Evaluated using accuracy, confusion matrix, and classification report

Feature Importance

Top churn drivers identified:

Contract: Month-to-month (most positive impact)

High Monthly Charges

Short Tenure

Model Saving

Model saved as churn_model.pkl for future use

Key Insights

Customers on month-to-month contracts have highest churn (~44%)

Senior citizens tend to churn more than non-senior customers

Customers with higher monthly charges are more likely to churn

Short-tenure customers are at higher churn risk

Visualizations
![Churn Distribution](visuals/churn_distribution.png)
![Tenure vs Churn](visuals/tenure_vs_churn.png)
![Monthly Charges vs Churn](visuals/monthlycharges_vs_churn.png)
![Contract Type vs Churn](visuals/contract_vs_churn.png)
![Payment Method vs Churn](visuals/paymentmethod_vs_churn.png)

Model Performance

Accuracy: 80–82% (Logistic Regression)

Confusion Matrix: Correctly predicts most loyal and churned customers

Classification Report:

Precision & recall balanced for Churn = 1 (minority class)

Folder Structure
Customer_Churn_Prediction/
├── data/                 # Dataset CSV
├── notebooks/            # Python/Colab notebook
├── visuals/              # Charts and plots
├── model/                # Saved churn_model.pkl
└── README.md             # Project documentation

How to Run

Open Customer_Churn_Prediction.ipynb in Google Colab

Upload dataset from data/ folder

Run all cells sequentially

Visualizations and model will be generated

Future Work / Improvements

Test with other ML algorithms (Random Forest, XGBoost)

Hyperparameter tuning for better accuracy

Build a web app/dashboard for real-time churn prediction

Explore additional features like customer service calls, complaints, or payment delays
