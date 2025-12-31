# Optimization-of-an-Artificial-Neural-Network-for-Marketing-Segmentation-Otomoto-
Otomoto has access to extensive customer demographic, subscription, and billing data but faces challenges in accurately segmenting customers for targeted marketing. This project recreates an ANN model and applies optimization algorithms to improve segmentation effectiveness, using customer churn as a proxy for actionable marketing segmentation.

# ANN Optimization for Marketing Segmentation (Otomoto)

## Overview
This project focuses on optimizing an Artificial Neural Network (ANN) to improve customer marketing segmentation at Otomoto. The goal is to enhance the identification of churn-prone customers and support more effective, data-driven marketing campaigns through the use of optimization algorithms.

Customer churn is used as a proxy for marketing segmentation, as customers likely to leave are prime targets for retention strategies.

---

## Business Context
Otomoto has access to rich customer data, including subscription details, service usage, and billing information. However, effectively segmenting customers for targeted marketing remains challenging. Artificial Neural Networks can learn complex, non-linear patterns in customer behavior and improve segmentation accuracy when properly optimized.

---

## Dataset
- **Dataset:** Teleconnect Customer Data  
- **File:** `teleconnect.csv`  
- **Records:** ~7,000 customers  
- **Target Variable:** `Churn`  
  - `Yes` → customer likely to churn  
  - `No` → customer likely to stay  

---

## Data Preprocessing
The following preprocessing steps were applied:
- Removed non-informative identifiers (`customerID`)
- Encoded churn labels into binary numerical values
- Converted billing fields to numeric format and handled missing values
- One-hot encoded categorical variables
- Standardized numerical features for stable ANN training

---

## Baseline ANN Model
A baseline feedforward ANN was implemented to represent the original marketing segmentation model. It consisted of:
- Two hidden layers with ReLU activation
- A sigmoid output layer for binary churn prediction

This model served as the reference point for optimization.

---

## Optimization Algorithms
Three optimization algorithms were evaluated:

- **Stochastic Gradient Descent (SGD)**
- **RMSprop**
- **Adam**

Each optimizer was applied using the same ANN architecture and training setup to ensure a fair comparison.

---

## Model Evaluation
Performance was evaluated on a test set using accuracy, precision, recall, and F1-score.

### Results Summary

| Optimizer | Accuracy | Precision | Recall | F1-score |
|----------|----------|-----------|--------|----------|
| SGD | 0.7996 | 0.6608 | 0.5053 | 0.5727 |
| RMSprop | 0.7967 | 0.6538 | 0.5000 | 0.5667 |
| Adam | **0.8010** | 0.6358 | **0.5882** | **0.6111** |

---

## Key Findings
- Accuracy was similar across all optimizers.
- SGD achieved higher precision but lower recall.
- Adam achieved the highest recall and F1-score, making it the most effective optimizer for identifying churn-prone customers.

---

## Marketing Impact
Higher recall enables Otomoto to identify more at-risk customers, allowing marketing teams to deploy targeted retention campaigns earlier and more effectively. Based on the results, Adam is recommended for retention-focused marketing segmentation.

---

## Recommendations
- Use Adam as the primary optimizer for the ANN.
- Apply decision-threshold tuning to further improve recall.
- Introduce class weighting to address churn imbalance.
- Expand segmentation into multi-tier customer risk categories.

---

## Repository Structure
