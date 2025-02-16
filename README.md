# M -L-Project
Created by Ramesh Koozhampalliyalil 
Car Price Prediction  This repository contains a Python script (`car_price_prediction.py`) that implements and compares several machine learning regression models to predict car prices using the `CarPrice_Assignment.csv` dataset.
 Car Price Prediction

This repository contains a Python script (`car_price_prediction.py`) that implements and compares several machine learning regression models to predict car prices using the `CarPrice_Assignment.csv` dataset.

## Table of Contents

1. [Loading and Preprocessing](#loading-and-preprocessing)
2. [Model Implementation](#model-implementation)
3. [Model Evaluation](#model-evaluation)
4. [Feature Importance Analysis](#feature-importance-analysis)
5. [Hyperparameter Tuning](#hyperparameter-tuning)
6. [Dataset](#dataset)
7. [Requirements](#requirements)
8. [How to Run](#how-to-run)

## 1. Loading and Preprocessing

The script begins by loading the `CarPrice_Assignment.csv` dataset using pandas.  The following preprocessing steps are performed:

* **Missing Value Handling:** Missing values in numerical columns are imputed using the mean, and in categorical columns using the mode.  *(Note: This imputation strategy can be adjusted as needed.)*
* **One-Hot Encoding:** Categorical features are converted to numerical representations using one-hot encoding with `pd.get_dummies()`. The `drop_first=True` argument is used to prevent multicollinearity.
* **Feature Scaling:** Numerical features are standardized using `StandardScaler` to have zero mean and unit variance. This is crucial for algorithms like SVR and Gradient Boosting.

## 2. Model Implementation

The following five regression algorithms are implemented using scikit-learn:

1. Linear Regression
2. Decision Tree Regressor
3. Random Forest Regressor
4. Gradient Boosting Regressor
5. Support Vector Regressor

## 3. Model Evaluation

The performance of each model is evaluated using the following metrics:

* R-squared (R²)
* Mean Squared Error (MSE)
* Mean Absolute Error (MAE)

The script prints these metrics for each model and identifies the best-performing model based on the highest R-squared value.

## 4. Feature Importance Analysis

The script performs feature importance analysis to identify the most significant variables affecting car prices.  This is done using the `feature_importances_` attribute for tree-based models (Random Forest, Gradient Boosting).  If the best model is a linear model, feature importance is calculated based on the absolute values of the coefficients. A plot of the top 10 features is displayed.

## 5. Hyperparameter Tuning

Hyperparameter tuning is performed using `GridSearchCV` to optimize the parameters of the best-performing model (Random Forest or Gradient Boosting, or SVR). The script prints the best parameters found by the grid search and the R-squared score after tuning, comparing it with the original R-squared.

## 6. Dataset

The `CarPrice_Assignment.csv` dataset contains information about cars, including their features and prices.  It is assumed to be present in the same directory as the script.  You can download it from [Kaggle](https://www.kaggle.com/datasets/hellbuoy/car-price-prediction).  *(Note: Please replace this with the actual link if different.)*

## 7. Requirements

The script requires the following Python libraries:

* pandas
* numpy
* scikit-learn
* matplotlib
* seaborn
