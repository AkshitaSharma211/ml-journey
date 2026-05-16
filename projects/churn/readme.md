# Customer Churn Prediction

## Problem
Predict which telecom customers will cancel their subscription.

## Dataset
7043 customers, 31 features after encoding.

## Key Finding
Dataset was imbalanced (73% no churn, 27% churn).
Used class_weight='balanced' to improve recall from 0.56 to 0.79.

## Results
| Model | Accuracy | Recall |
|---|---|---|
| LR Default | 80.4% | 0.56 |
| LR Balanced | 75% | 0.79 |
| LR GridSearch | 74% | 0.79 |

## Best Model
Logistic Regression with class_weight='balanced'
Recall = 0.79 → catches 79% of actual churners