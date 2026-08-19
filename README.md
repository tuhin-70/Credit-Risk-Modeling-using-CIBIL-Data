# Credit Risk Modeling using CIBIL Data

This project focuses on building an end-to-end credit risk modeling workflow using CIBIL bureau data. The workflow covers bureau data preprocessing, target construction, feature engineering, Out-of-Time (OOT) feature preparation, machine learning model development, and model evaluation.

## Project Overview

The objective is to develop a model to identify customers who may experience **60+ Days Past Due (DPD) within a 9-month period**.

The project works with bureau-level information such as:

- Tradeline data
- Inquiry data
- Payment history
- Customer reference information

The workflow is implemented using **PySpark** for large-scale data processing and machine learning models for credit risk prediction.

## Workflow

### 1. Feature Engineering

- Read and preprocess Tradeline, Inquiry, and reference data.
- Handle date fields and invalid records.
- Apply business and historical lookback filters.
- Process payment history and delinquency-related information.
- Create customer-level features using joins, window functions, and aggregations.

### 2. Target Construction

- Build the `user_ever60_9m` target.
- Identify whether a customer experienced 60+ DPD within the defined 9-month window.
- Apply the required eligibility and data-quality filters.

### 3. OOT Feature Engineering

- Prepare features for the Out-of-Time (OOT) population.
- Apply the same feature engineering logic to unseen data.
- Maintain the same reference-date-based methodology used for model development.

### 4. Model Development & Evaluation

- Prepare the final modeling dataset.
- Train and compare machine learning models.
- Evaluate model performance using appropriate classification metrics.
- Assess model performance on unseen data.

## Notebooks

| Notebook | Description |
|---|---|
| `01_Feature_Engineering_Development.ipynb` | Bureau data preprocessing and feature engineering |
| `02_Target_Construction.ipynb` | Target population filtering and target construction |
| `03_Feature_Engineering_OOT.ipynb` | Feature engineering for the Out-of-Time population |
| `04_Model_Development_and_Evaluation.ipynb` | Model training, tuning, prediction, and evaluation |

## Machine Learning

The modeling workflow includes:

- Decision Tree
- Random Forest
- XGBoost

Model performance is evaluated using:

- ROC-AUC
- LogLoss
- KS
- Precision
- Recall
- F1-score

## Feature Engineering

The feature engineering process includes customer-level variables derived from bureau information, such as:

- Trade counts
- Balance and sanctioned amount
- Product-level features
- Secured and unsecured trade features
- DPD and delinquency-related features
- Vintage and account history
- Inquiry-based features
- Payment history trends
- Ratio and rate-based features

Lookback windows are used to capture recent as well as historical customer behaviour.

## Technology Stack

- Python
- PySpark
- Pandas
- Scikit-learn
- XGBoost
- Jupyter Notebook

## Repository Structure

```text
Credit-Risk-Modeling-using-CIBIL-Data/
│
├── 01_Feature_Engineering_Development.ipynb
├── 02_Target_Construction.ipynb
├── 03_Feature_Engineering_OOT.ipynb
├── 04_Model_Development_and_Evaluation.ipynb
└── README.md
