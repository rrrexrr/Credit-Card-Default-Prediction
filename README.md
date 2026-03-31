# Credit Card Default Prediction

This is a Personal Machine Learning Project that predicts whether a credit card client will default on payment in the following month using demographic, billing, and repayment information.

<div align="left">

**Focus:** Financial risk classification  
**Goal:** Build an end to end, reproducible modeling workflow  
**Best model:** Tuned Random Forest  
**Main takeaway:** Repayment behavior is much more predictive than simple demographic variables

</div>

---

## Project Snapshot

This project studies a classic credit risk problem: **Can we predict next month's default using client profile and recent financial behavior?**

Using the **Default of Credit Card Clients** dataset, I built a full classification workflow that includes:

- Data inspection and train/test splitting,
- Exploratory data analysis,
- Preprocessing pipelines,
- Baseline and benchmark models,
- Model comparison,
- Feature selection,
- Hyperparameter tuning, and
- Final test-set evaluation.

This notebook is designed to show not just the final result, but also the reasoning behind the modeling choices.

---

## Why This Project Matters

Default prediction is a practical business problem with clear real world value. A model that can better identify higher risk clients may help support:

- Earlier intervention,
- More informed lending decisions, and
- Stronger portfolio risk management.

This project also highlights an important modeling lesson: in an **imbalanced classification problem**, accuracy alone is not enough. Metrics such as **ROC-AUC, recall, and F1-score** provide a much more useful picture of performance.

---

## Dataset

**Dataset:** Default of Credit Card Clients  
**Source:** UCI Machine Learning Repository  
**Task:** Binary classification  
**Target variable:** `default payment next month`

The dataset contains information on **30,000 credit card clients**, including:

- Demographic features,
- Credit limit,
- Repayment status,
- Bill statement amounts, and
- Previous payment amounts.

**Citation:**  
Yeh, I. (2009). *Default of Credit Card Clients* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C55S3H

---

## Workflow

### 1. Data Preparation
- Loaded and inspected the dataset
- Split data into training and test sets using stratification
- Organized numeric and categorical features for modeling

### 2. Exploratory Data Analysis
- Examined class balance
- Compared key predictors such as age, credit limit, and repayment history
- Identified repayment variables as the strongest early signals of default risk

### 3. Preprocessing
- Imputed missing values where needed
- Scaled numeric features
- One-hot encoded categorical variables
- Combined transformations using `ColumnTransformer` pipelines

### 4. Modeling
Models explored in the notebook include:

- Dummy Classifier (baseline)
- Logistic Regression
- Decision Tree
- K-Nearest Neighbors
- Random Forest

### 5. Feature Selection
- Applied RFECV with logistic regression
- Evaluated whether a reduced feature set could preserve model performance

### 6. Hyperparameter Tuning
- Tuned major candidate models using cross-validation
- Used **ROC-AUC** as the primary selection metric

### 7. Final Evaluation
- Assessed the selected model on a held-out test set
- Compared validation and test performance
- Interpreted model behavior using feature importance

---

## Key Results

The strongest overall model in this project was the **tuned Random Forest**.

### Final Test Performance
- **Accuracy:** 0.8188
- **Precision:** 0.6824
- **Recall:** 0.3384
- **F1-score:** 0.4524
- **ROC-AUC:** 0.7792

### Interpretation
The final model performed consistently on validation and test data, which suggests that tuning did **not** lead to meaningful overfitting.

The most important predictors were mainly tied to:

- recent repayment status,
- payment amounts, and
- bill statement variables.

In particular, recent repayment behavior carried much more predictive signal than basic demographic information alone.


---


## What This Project Demonstrates

This project showcases several core machine learning skills:

- building a structured end to end classification workflow,
- using preprocessing pipelines correctly,
- comparing baseline, linear, and nonlinear models,
- tuning models with cross-validation,
- evaluating imbalanced classification problems with appropriate metrics, and
- combining predictive performance with interpretability.

---

## Limitations

Like most supervised learning projects, this analysis has some limitations:

- model performance depends on the available variables in the dataset,
- recall is still moderate, so many true default cases remain difficult to detect,
- the project focuses on predictive modeling rather than causal explanation.

These limitations also point naturally to future improvements.

---


## Author

**Ziming Ren (Rex)**  
Statistics student at UBC with an interest in data analysis, machine learning, and applied modeling.

---

## Notes

This repository is intended as a learning and portfolio project. The coding and main idea comes from one of my computer science course work. The emphasis is on a clear workflow, careful model comparison, and readable analysis rather than only chasing the highest possible metric.
