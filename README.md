# 🧠 Deloitte Machine Learning Challenge: Predict Loan Defaulters

🔗 [Visit Challenge on MachineHack](https://machinehack.com/hackathons/deloitte_presents_machine_learning_challenge_predict_loan_defaulters/overview)

---

## 📌 Overview

This repository contains my solution for the **Deloitte Machine Learning Challenge**, hosted on **MachineHack**. The objective was to predict **loan defaulters** using various financial and personal attributes.  

Banks lose substantial amounts due to loan defaults, and this challenge aims to help mitigate such risks using **machine learning**.

---

## 🧾 Problem Statement

🏦 **Goal:** Predict if a person will default on a loan based on features such as:
- Loan amount
- Funded amount
- Interest rate
- Employment duration
- Home ownership
- ... and more

🎯 **Target Variable:** `Loan Status`  
- `1` → Defaulter  
- `0` → Non-Defaulter

---

## 📊 Dataset

- **Training Set:** `67,463 rows × 35 columns`  
- **Test Set:** `28,913 rows × 34 columns`

### 🧷 Sample Features:
- `Loan Amount` – Requested loan amount  
- `Funded Amount` – Amount funded  
- `Interest Rate` – Percentage interest  
- `Employment Duration` – Length of employment  
- `Home Ownership` – Rented / Owned / Mortgage  
- `Loan Status` – Target label

🔍 *Full feature list available in the dataset files.*

---

## 🧮 Evaluation Metric

📉 **Log Loss** was used to evaluate model performance.  
The competition involved two stages:

1. **Stage 1:** Private leaderboard using 100% of test data.
2. **Stage 2:** Multiple-choice questions on SQL, regression, and data engineering.

---

## 🛠️ Solution Approach

### 1️⃣ Data Preprocessing
- Verified absence of missing values.
- Applied **log transformations** to reduce skewness.
- Normalized numeric features.
- Encoded categorical variables.

### 2️⃣ Feature Engineering
- Created new features:
  - `Recoveries + Collection Recovery Fee`
  - `Total Collection Amount + Total Received Late Fee`
- Applied **frequency encoding** within CV loops to avoid leakage.

### 3️⃣ Modeling
- Utilized **XGBoost** for robust prediction.
- Conducted hyperparameter tuning via **Optuna**.
- Applied **5-Fold Cross-Validation** for generalization.

### 4️⃣ Model Interpretation
- Leveraged **SHAP (SHapley Additive exPlanations)** to understand feature importance.

---

## ⚙️ Installation

Clone the repo and install dependencies:

```bash
git clone https://github.com/DwaipayanDutta/Deloitte-Machine-Learning-Challenge.git
cd Deloitte-Machine-Learning-Challenge
pip install -r requirements.txt

```
## Technologies Used
- `Python`
- `Pandas, NumPy`
- `Scikit-learn`
- `XGBoost`
- `Optuna`
- `SHAP`
- `Matplotlib, Seaborn`

## 📁 Repository Structure
```bash
├── Code/
│ └── deloitte-machine-learning.ipynb # Main Jupyter Notebook with full solution
├── Dataset/
│ └── train.csv # Training dataset
│ └── test.csv # Test dataset
└── README.md # This file
```



