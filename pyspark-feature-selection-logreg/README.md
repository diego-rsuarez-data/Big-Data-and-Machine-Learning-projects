# Bank Telemarketing Campaign Prediction with PySpark

This project focuses on **predicting whether a client will subscribe to a term deposit** in a bank telemarketing campaign using **PySpark**.  
The main goal is to explore whether **feature selection improves model performance** and interpretability using a **Logistic Regression classifier**.

## Project Structure

**bank-deposit-spark/**  
- `data/` — Dataset in CSV format (`bank_92.csv`)  
- `notebooks/` — Jupyter notebooks with preprocessing, modeling, and evaluation  
- `results/` — Summary of model metrics and selected features  
- `requirements.txt` — Python dependencies  
- `README.md` — This file  

## Objective
- Build a logistic regression model for predicting term deposit subscription.  
- Preprocess the dataset, including handling the `pdays` feature (clients never contacted).  
- Encode categorical variables and assemble features using PySpark pipelines.  
- Evaluate **different feature selection strategies** and compare their impact on model performance.  
- Identify and interpret the most relevant features selected by the best-performing strategy.  

## Methodology

1. **Data Preprocessing:**  
   - Convert `pdays` into `contacted_before` and `days_since_last_contact`.  
   - Transform categorical variables with `StringIndexer` and `OneHotEncoder`.  
   - Assemble all features into a single vector column for MLlib.  

2. **Train/Validation Split:**  
   - 80% training / 20% validation to evaluate model generalization.  

3. **Feature Selection:**  
   - Applied via `UnivariateFeatureSelector` with multiple strategies (FPR, FWE, Percentile).  
   - Logistic Regression trained on each selected feature set.  

4. **Model Evaluation:**  
   - Metrics: Accuracy and Area Under the Curve (AUC)  
   - Comparison between no selection and the different feature selection strategies.  

5. **Feature Interpretation:**  
   - Extracted feature names from the selected feature sets.  
   - Identified key dimensions affecting subscriptions: engagement, past campaign history, financial stability, seasonality, and demographics.  

## Results
- Full results of model performance and feature selection are saved in the `results/` folder.  
- The FWE-based feature selection was the most informative strategy.  
- CSV files summarize metrics and the features selected by each strategy.  

## Dependencies

```text
pandas
numpy
pyspark>=3.5