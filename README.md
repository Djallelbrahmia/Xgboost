# Churn Prediction with XGBoost

## Project Overview

This project involves building a **Churn Prediction Model** using **XGBoost**, a powerful machine learning algorithm for classification tasks. The goal of the model is to predict which customers are most likely to churn (leave a service or subscription), allowing businesses to take proactive measures to retain valuable customers.

The dataset used for this project contains customer data with several features, including demographic information, service usage patterns, and customer service interactions. The data is highly **imbalanced**, with fewer churn cases compared to non-churn cases. To address this, the model was carefully tuned for optimal performance in detecting the minority class (churn), prioritizing recall and precision over general accuracy.

## Key Features

- **Modeling Approach**: 
  - **XGBoost Classifier** was chosen due to its efficiency, handling of missing data, and ability to handle imbalanced datasets.
  - **Hyperparameter Tuning**: Employed **GridSearchCV** to find the best combination of parameters, ensuring the model was well-tuned for high performance.
  - **Threshold Adjustment**: The decision threshold was increased to 0.75 to maximize the detection of churn, reducing false negatives.
  
- **Evaluation Metrics**:
  - **Accuracy**: 85.1%
  - **Precision**: 70.9%
  - **Recall**: 78.8%
  - **F1-Score**: 74.7%
  - **ROC AUC**: 0.89

The model was optimized to maximize churn detection (recall) while minimizing false negatives, critical for identifying at-risk customers.

## Data Preprocessing

- **Handling Missing Values**: Missing data in the `TotalCharges` column was replaced with `0`, and then the column was converted to a numeric type.
- **Categorical Encoding**: Categorical variables were transformed into numerical features using **One-Hot Encoding** to allow them to be used by the XGBoost model.
- **Data Splitting**: The data was split into **training** and **testing** sets, with stratified sampling to maintain the balance of the target variable (Churn).

## Challenges

The primary challenge in this project was dealing with **imbalanced data**. With significantly fewer churn cases than non-churn cases, the model had to be tuned carefully to ensure that it effectively predicted the minority class (churn) while maintaining a good balance with precision and recall.

## Installation

To run this project, clone the repository and install the necessary dependencies:

```bash
git clone https://github.com/your-username/churn-prediction-xgboost.git
cd churn-prediction-xgboost
pip install -r requirements.txt
