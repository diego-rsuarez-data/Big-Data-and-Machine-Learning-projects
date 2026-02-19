# Bank Deposit Prediction

This project focuses on **predicting whether a bank customer will subscribe to a term deposit** using machine learning techniques.  
The goal is to create a predictive model based on customer demographic, financial, and interaction data, helping the bank identify clients more likely to accept the product.

## Project Structure

bank-deposit-prediction/
├─ data/ # Original dataset(s)
├─ notebooks/ # Jupyter notebooks with all analyses and models
├─ requirements.txt # Python dependencies
└─ README.md # This file

## Objective
- Build a predictive model for term deposit subscription.
- Apply preprocessing: handling missing values, encoding categorical variables, removing constants.
- Compare multiple ML algorithms (KNN, Decision Trees, Random Forest, Gradient Boosting, XGBoost, CatBoost).
- Hyperparameter tuning with GridSearch, RandomSearch, and Optuna.
- Calibrate probabilities and evaluate with confidence intervals.
- Interpret model decisions using **SHAP**.

## Methodology

1. **Exploratory Data Analysis (EDA):**  
   - Analyze number of features, instances, missing values, categorical vs numeric variables, feature distributions.  
   - Handle special features like `pdays`.

2. **Train/Test Split:**  
   - Outer evaluation: holdout set for final model assessment.  
   - Inner evaluation: used for hyperparameter optimization (HPO) and algorithm selection.

3. **Modeling:**  
   - **Basic models:** KNN, Decision Trees  
   - **Advanced models:** Random Forest, Gradient Boosting (LightGBM, XGBoost, CatBoost), Extra Trees  
   - **Hyperparameter Optimization:** GridSearchCV, RandomizedSearchCV, Optuna  
   - **Dummy baseline model** for comparison

4. **Probability Calibration:**  
   - Assess and improve predicted probabilities with scikit-learn calibration methods.

5. **Interpretability:**  
   - Use **SHAP** to explain feature contributions to model predictions.

## Results
- Final model selected based on inner evaluation performance.
- Predictions made on the competition dataset.
- Model saved in `.pkl` format.
- Performance metrics and confidence intervals reported in the notebook.

## Dependencies

```text
numpy
pandas
matplotlib
scikit-learn
xgboost
lightgbm
catboost
optuna
shap
joblib
statsmodels
