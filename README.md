# Deloitte Machine Learning Challenge: 
  # Predict Loan Defaulters

[Deloitte Machine Learning Challenge](https://machinehack.com/hackathons/deloitte_presents_machine_learning_challenge_predict_loan_defaulters/overview)

## Overview

This repository contains the solution to the **Deloitte Machine Learning Challenge**, an online hackathon organized in collaboration with MachineHack. The challenge aimed to predict loan defaulters based on various financial attributes, using a dataset provided by MachineHack.

## Problem Statement

Banks incur significant losses when customers default on loans. To mitigate this, the challenge focused on predicting whether a person would default on a loan using attributes such as loan amount, funded amount, interest rate, employment duration, and more.

## Dataset

The dataset comprises:

- **Training Data**: 67,463 rows × 35 columns
- **Test Data**: 28,913 rows × 34 columns

### Features Include:

- `Loan Amount`: Amount applied for the loan
- `Funded Amount`: Amount funded by investors
- `Interest Rate`: Interest rate on the loan
- `Employment Duration`: Duration of employment
- `Home Ownership`: Ownership status of the home
- `Loan Status`: Target variable indicating loan default (1 = Defaulter, 0 = Non-Defaulter)

*For a complete list of features, refer to the dataset description in the repository.*

## Evaluation Metric

The submissions were evaluated using the **Log Loss** metric. The evaluation was conducted in two stages:

1. **Stage-1**: Based on the private leaderboard using 100% of the provided test dataset.
2. **Stage-2**: Included multiple-choice questions on SQL, data engineering, and regression.

## Solution Approach

### 1. Data Preprocessing

- Checked and confirmed no missing values.
- Applied log transformations to stabilize numeric feature variance.
- Categorical encoding and normalization.

### 2. Feature Engineering

- Engineered new features like:
  - Sum of `Recoveries` and `Collection Recovery Fee`
  - Sum of `Total Collection Amount` and `Total Received Late Fee`
- Frequency encoding of categorical variables inside the cross-validation loop to avoid leakage.

### 3. Modeling

- Used **XGBoost** for training the model.
- Hyperparameter tuning using **Optuna**.
- 5-fold cross-validation used to ensure model generalization.

### 4. Interpretability

- Used **SHAP** (SHapley Additive exPlanations) for model interpretation and to analyze feature importance.

## Installation
To replicate the environment and run the notebook:

```bash
git clone https://github.com/DwaipayanDutta/Deloitte-Machine-Learning-Challenge.git
cd Deloitte-Machine-Learning-Challenge
pip install -r requirements.txt
```
## Usage
Run the Jupyter notebook to explore the implementation:

```bash
jupyter notebook Deloitte_Machine_Learning_Challenge.ipynb
```
## Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Optuna
- SHAP
- Matplotlib, Seaborn

## 📁 Repository Structure
```bash
├── Code/
│ └── deloitte-machine-learning.ipynb # Main Jupyter Notebook with full solution
├── Dataset/
│ └── train.csv # Training dataset
│ └── test.csv # Test dataset
└── README.md # This file
```



