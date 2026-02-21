# Predictive Modeling of Sales Dynamics

## Overview

This project develops a predictive modeling framework to forecast **Sales** and analyze their relationship with the available features, with particular focus on investment-related variables.

The objective is twofold:
- Build an accurate predictive model.
- Provide interpretability and insights about the drivers of Sales.


## Project Structure

- `data/` — Dataset in CSV format (`Real_Dataset_HW2`)  
- `notebook/` — RMarkdown notebooks (also exported to HTML in `report/`)  
- `report/` — HTML reports generated from notebooks (`Predictive_Modeling_of_Sales_Dynamics.html`)   
- `requirements.txt` — Python dependencies  
- `README.md` — Project description and instructions

## Methodology

### 1. Data Preprocessing
- Missing value handling
- Outlier inspection
- Feature scaling (when required)
- Encoding categorical variables (if applicable)

### 2. Exploratory Data Analysis
- Distribution analysis
- Correlation analysis
- Investment variable inspection
- Temporal patterns (if present)

### 3. Feature Engineering
- Interaction terms
- Derived investment ratios
- Transformations for skewed variables
- Feature selection (when relevant)

### 4. Model Development
- Train/validation split
- Baseline regression model
- Advanced machine learning models
- Cross-validation
- Hyperparameter tuning

### 5. Model Evaluation
- Mean Absolute Error (MAE)
- R² Score
- Residual analysis
- Model comparison

### 6. Model Interpretability
- Feature importance analysis
- Investment variable impact assessment
- Visual explanation of model behavior


## Output

The project produces:

1. A fully documented Jupyter Notebook containing:
   - All preprocessing steps
   - Modeling procedures
   - Evaluation metrics
   - Interpretability analysis

2. A compiled HTML report.

3. A CSV file with predictions for the test dataset.



