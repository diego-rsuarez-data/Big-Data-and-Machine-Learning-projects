# Bank Telemarketing Campaign Prediction with PySpark

This project focuses on **predicting whether a client will subscribe to a term deposit** in a bank telemarketing campaign using **PySpark**.  
The main goal is to explore **feature selection strategies** and their impact on model performance and interpretability using a **Logistic Regression classifier**.

## Project Structure

**bank-deposit-spark/**  
- `data/` — Dataset in CSV format (`bank_92.csv`)  
- `notebooks/` — Jupyter notebooks with preprocessing, modeling, and evaluation (also exported to HTML)  
- `requirements.txt` — Python dependencies  
- `README.md` — This file  

## Objective
- Build a logistic regression model for predicting term deposit subscription.  
- Preprocess the dataset, including handling the `pdays` feature (clients never contacted).  
- Encode categorical variables and assemble features using PySpark pipelines.  
- Evaluate **different feature selection strategies** (FPR, FWE, Percentile) to assess their effect on model performance.  
- Identify and interpret the most relevant features selected by the best-performing strategy.  

## Methodology

1. **Data Preprocessing:**  
   - Transform `pdays` into `contacted_before` and `days_since_last_contact`.  
   - Convert categorical variables into numerical representations using `StringIndexer` and `OneHotEncoder`.  
   - Assemble all features into a single vector column (`features`) for MLlib.

2. **Train/Validation Split:**  
   - 80% training / 20% validation to evaluate model generalization.

3. **Feature Selection:**  
   - Applied via `UnivariateFeatureSelector` using multiple strategies (FPR, FWE, Percentile).  
   - Logistic Regression models trained on each selected feature set.

4. **Model Evaluation:**  
   - Metrics: Accuracy and Area Under the Curve (AUC).  
   - Comparison between no selection and the different feature selection strategies.

5. **Feature Interpretation:**  
   - Extracted original feature names from the selected indices.  
   - Identified key dimensions influencing subscription behavior: call engagement, past campaign history, financial indicators, seasonality, and demographics.

## Dependencies

```text
pandas
numpy
pyspark>=3.5