# DA5401 A8: Ensemble Learning for Bike Sharing Demand Forecasting

## Student Details
| Detail | Value |
|--------|--------|
| Name | Anumita |
| Roll Number | BE22B004 |

---

## Objective
Apply Bagging, Boosting, and Stacking to forecast the hourly bike rental count (cnt) using the Bike Sharing Demand dataset.  
Goal: achieve lower RMSE than single regression models by reducing variance and bias.

---

## Methodology

### 1. Data Preprocessing
- Removed: instant, dteday, casual, registered
- One-Hot Encoding: season, weathersit, mnth, hr, weekday
- Baseline models:
  - Linear Regression
  - Decision Tree Regressor (max_depth = 6)
  Linear Regression provided the best baseline RMSE.

### 2. Ensemble Models
- Bagging Regressor:
  - 50 Decision Trees (max_depth = 6)
  - Reduces variance
- Gradient Boosting Regressor:
  - Sequential error correction
  - Reduces bias
- Stacking Regressor:
  - Level-0: KNN, Bagging, Gradient Boosting
  - Level-1: Ridge Regression
  - Combines diverse learners for optimal performance

---

## Results (Replace placeholders with your actual RMSEs)

| Model | Goal | RMSE |
|--------|--------|---------|
| Linear Regression (Baseline) | Baseline | 100.46 |
| Bagging Regressor | Reduce Variance | 113.50 |
| Gradient Boosting Regressor | Reduce Bias | 79.40 |
| Stacking Regressor | Optimal Performance | 69.04 |

---

## Conclusion
The Stacking Regressor achieved the lowest RMSE.  
Reasons:
1. Combines low-bias (Boosting) and low-variance (Bagging) models.  
2. Uses diverse model families (distance-based, tree-based, linear).  
3. Ridge meta-learner optimally weights their predictions.

---

## Visualization Summary
- Baseline (Linear Regression) underfits and misses demand peaks.
- Gradient Boosting captures cyclical patterns better.
- Stacking predictions track actual demand most closely.

---

## How to Run

### Requirements
Python 3.8+  
Libraries:
- pandas
- numpy
- scikit-learn
- matplotlib

### Dataset
Download hour.csv from the UCI Bike Sharing Dataset:
https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset  

---
