# Loan Portfolio Risk Analysis

## Project Background

Credit risk assessment plays an important role in lending decisions. Understanding borrower characteristics can help financial institutions identify high-risk applicants and reduce potential loan defaults.

In this project, I performed an **Exploratory Data Analysis (EDA)** using **Microsoft Excel** to analyze the relationship between borrower financial characteristics and loan status, with the goal of identifying borrower profiles that have the highest probability of default.

**Business Problem**

> Which borrower profiles have the highest probability of default?

---

## Quick Links

- 📄 [Excel Workbook](loan-risk-analysis.xlsx)
- 📊 [Analysis Preview](analysis-preview.png)
- 📁 [Lending Club Loan Dataset](https://www.kaggle.com/datasets/utkarshx27/lending-club-loan-dataset)

---

## Dataset Overview

The dataset is based on the **Lending Club Loan Dataset**, obtained from Kaggle. It contains approximately **10,000 loan records** and **55 variables**, where each row represents a single borrower.

This analysis focuses on the following variables:

- Annual Income
- Debt-to-Income Ratio (DTI)
- Credit Grade
- Loan Amount
- Loan Status

To support the analysis, several derived features were created:

- Loan Risk (Good / Risky)
- Income Segment
- DTI Segment
- Loan Amount Segment

---

## Data Preparation

Before the analysis, the dataset was cleaned by:

- Removing duplicate records
- Removing blank rows
- Removing invalid income values
- Removing missing DTI values

Since all data quality issues accounted for **less than 1%** of the dataset, their impact on the analysis was minimal.

---

## Tools

- Microsoft Excel
- Pivot Table
- Conditional Formatting
- Data Visualization

---

## Business Questions

This analysis aims to answer the following questions:

- Are lower-income borrowers more likely to default?
- Does a higher Debt-to-Income (DTI) ratio increase default risk?
- Which credit grade has the highest default rate?
- Are larger loan amounts associated with higher risk?

---

## Analysis Preview

![Loan Portfolio Risk Analysis](analysis-preview.png)

---

## Key Findings

- **98.22%** of loans were classified as **Good**, while **1.78%** were classified as **Risky**.
- Borrowers in the **Low Income** segment had the highest default rate.
- **Credit Grade** was the strongest indicator of loan risk, with **Grade F** showing the highest default rate (**10.53%**).
- Borrowers with **Large Loans** had a higher default rate than those with small or medium loans.
- **Debt-to-Income (DTI)** did not show a consistent relationship with default risk in this dataset.
- The highest-risk borrower profile was **Grade F + Low Income**, with a default rate of **12.50%**.

---

## Recommendations

Based on the analysis, the following actions are recommended:

- Apply stricter credit evaluations for borrowers with lower credit grades.
- Perform additional assessments for large loan applications.
- Use **Credit Grade** as the primary indicator during credit risk evaluation.
- Consider combining **Credit Grade**, **Income**, and **Loan Amount** when developing a credit scoring model.
