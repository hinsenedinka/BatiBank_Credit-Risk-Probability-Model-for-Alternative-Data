# BatiBank_Credit-Risk-Probability-Model-for-Alternative-Data

## Abstract

This project aims to provide Credit scoring model to asses if a customer of an ecommerce platform  qualifies to utilize a buy-now-pay-later service. Using data from the ecommerce platform, after performing exploratory data analysis, feature engineering, model training to provide the likelyhood of customer defaulting and drive actionable insigths.

## Table of Contents

1. Abstract
2. Table of Content
3. Credit Scoring Business Understanding
4. Data Source
5. Methodology
6. Repository Structure
7. Results
8. Getting Started


## Credit Scoring Business Understanding

Under the Basel II Accord, a bank's ability to use internal models to calculate credit risk capital is contingent on those models being both interpretable and well-documented. This is because regulators require a transparent, verifiable, and auditable framework for risk measurement. An interpretable model, such as one with clear coefficients or logic, allows regulators to understand exactly how a risk score is derived from a customer's data, ensuring the model's logic is sound and free from bias, rather than operating as a "black box." Furthermore, the requirement for a well-documented process—from data sourcing and feature engineering to validation and monitoring—creates a crucial audit trail. This documentation is essential for independent validation, reproducibility, and ongoing supervisory review, transforming the model from a mere predictive tool into a core component of the bank's regulatory compliance and risk governance framework.

### The Necessity and Risk of Proxy Variables
When a direct "default" label is unavailable, creating a proxy variable becomes essential to operationalize a definition of the event and enable supervised machine learning. This proxy acts as a substitute for the true target, such as defining "default" as being 60 days past due on a payment. However, using a proxy introduces significant business risks. A model trained on a proxy may not accurately predict the true event, leading to misclassification and ineffective business actions. The relationship between the proxy and the actual outcome can also shift over time, causing model drift and degrading performance. Therefore, if the model's predictions don't translate to real-world business value, its reliability can be called into question, damaging stakeholder trust and inviting regulatory scrutiny. Continuous validation against actual outcomes is crucial to mitigate these inherent risks.

In a regulated financial context, model choice involves a key trade-off between predictive accuracy and interpretability. Simple, interpretable models like Logistic Regression with Weight of Evidence (WoE) are highly favored due to their transparent, auditable logic, which is crucial for regulatory compliance and explaining individual credit decisions. While they offer stability and ease of deployment, they may sacrifice predictive performance by failing to capture complex, non-linear relationships in the data. In contrast, complex, high-performance models like Gradient Boosting can achieve superior accuracy by identifying intricate feature interactions, but they suffer from a "black-box" nature. This lack of interpretability poses a major regulatory hurdle, as it is difficult to justify why a specific prediction was made. Therefore, in a highly regulated environment, interpretability and robust documentation often outweigh marginal gains in predictive accuracy, making simpler models a preferred choice for critical decisions like credit scoring, while complex models are better suited for internal alerting systems where auditability is less rigid.

## Data Source
Link: https://www.kaggle.com/datasets/atwine/xente-challenge

## Methodology
 * Data cleaning and preprocessing
 * Exploratory Data Analysis (EDA)
 * Feature Engineering
 * Proxy Target Variable Engineering
 * Model Training and Tracking
 * Model Deployment and Continuous Integration

## Repository Structure

├── .github/workflows/ci.yml   # For CI/CD

├── data/                     

│   ├── raw/                   # Raw data goes here 

│   └── processed/             # Processed data for training

├── notebooks/

│   └── 1.0-eda.ipynb          # Exploratory, one-off analysis

├── src/

│   ├── __init__.py

│   ├── data_processing.py     # Script for feature engineering

│   └── api/

│       ├── main.py           

│       └── pydantic_models.py 

├── tests/

│   └── test_data_processing.py 

├── Dockerfile

├── docker-compose.yml

├── requirements.txt

├── .gitignore

└── README.md



