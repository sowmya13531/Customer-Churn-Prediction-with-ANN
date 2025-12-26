## Customer Churn Prediction With Artificial Neural Network 🛃

## Overview 🔍
Customer churn prediction is the process of identifying customers who are likely to leave a business. In this project, we analyze a telecom dataset to predict whether a customer will churn or not. The goal is to build a deep learning model and evaluate its performance using metrics such as Precision, Recall, and F1-score.

## Dataset

The dataset customer_churn.csv contains 7043 rows and 21 columns. Some important columns:

### Column Name	Description

- customerID	Unique customer identifier (dropped during analysis)
- gender	Customer gender (Male/Female)
- SeniorCitizen	1 if the customer is a senior citizen, 0 otherwise
- Partner	1 if the customer has a partner, 0 otherwise
- Dependents	1 if the customer has dependents, 0 otherwise
- tenure	Number of months the customer has stayed with the company
- PhoneService	1 if the customer has phone service, 0 otherwise
- MultipleLines	1 if the customer has multiple phone lines, 0 otherwise
- InternetService	Type of internet service (DSL, Fiber optic, No)
- Contract	Contract type (Month-to-month, One year, Two year)
- PaymentMethod	Payment method (Electronic check, Mailed check, etc.)
- MonthlyCharges	Customer's monthly charges
- TotalCharges	Total amount charged to the customer
- Churn	Target variable (1 = Yes, 0 = No)

## Steps

### 1. Data Cleaning

- Dropped the customerID column as it is not useful for prediction.
- Converted TotalCharges from string to numeric, and removed rows with empty values.


### 2. Data Visualization

- Visualized tenure and monthly charges for churned vs non-churned customers.

### Observed trends:

- Customers with low tenure are more likely to churn.
- Customers with high monthly charges are more likely to churn.

### 3. Data Transformation

- Replaced "No internet service" and "No phone service" with "No" for simplification.
- Converted categorical Yes/No columns into binary values (1/0).
- Converted gender to numeric (Female=1, Male=0).
- Applied one-hot encoding to categorical columns (InternetService, Contract, PaymentMethod).
- Scaled numeric columns (tenure, MonthlyCharges, TotalCharges) to [0,1] using MinMaxScaler.


### 4. Train-Test Split

- Separated features (X) and target (y).
- Split the dataset into training (80%) and testing (20%) sets using stratified sampling to preserve class distribution.

- Observed class imbalance:
Non-churned: 5163
Churned: 1869
Ratio ≈ 2.76 (Non-churned : Churned)


## Libraries Used
- pandas – Data manipulation
- numpy – Numerical operations
- matplotlib – Visualization
- scikit-learn – Preprocessing, train-test split, scaling
- tensorflow/keras – Deep learning model building (future step)

### Insights
- Data cleaning and proper transformation are critical before feeding the data into a neural network.
- Class imbalance can strongly affect model performance; metrics like F1-score are preferred.
- Features like tenure, monthly charges, and contract type are strong indicators of churn.

## How to Run

1. Clone the repository
```git bash
git clone https://github.com/sowmya13531/Customer-Churn-Prediction-with-ANN.git
cd Customer-Churn-Prediction-with-ANN
```

*Download the colab notebook.Run it locally.*
