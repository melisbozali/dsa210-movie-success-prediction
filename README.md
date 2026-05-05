# DSA210 Project - Divorce Analysis

## Project Overview
This project originally aimed to predict movie success, but it was later updated to analyze divorce patterns using IPUMS US Census data.

This project analyzes the relationship between divorce probability and socio-economic factors such as age, education level, and income. The goal is to understand whether these variables have a statistically significant effect on divorce outcomes.

---

## Data Source
The dataset was obtained from **IPUMS USA (ACS 2023 sample)**.

Selected variables:
- AGE (Age)
- MARST (Marital Status)
- EDUC (Education Level)
- INCWAGE (Income)

---

## Data Preparation
The dataset was cleaned and transformed before analysis:

- Invalid or unclear marital statuses were removed
- A binary variable `divorced` was created:
  - 1 → divorced or separated
  - 0 → not divorced

- A binary variable `young` was created:
  - 1 → age ≤ 25
  - 0 → age > 25

- Individuals with zero income were excluded from income analysis

---

## Exploratory Data Analysis (EDA)
Several visualizations were created to explore patterns:

- Distribution plots of age, education, and employment status
- Correlation matrix between key variables
- Boxplot of age vs divorce

Key observations:
- Divorce rates increase with age up to middle age
- Higher education levels tend to have lower divorce rates
- Lower income groups show higher divorce rates
- No single variable fully explains divorce, suggesting multiple interacting factors

---

## Machine Learning Models

The following models were implemented:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Decision Tree
- Random Forest

To address class imbalance, `class_weight = balanced` was used where applicable.

---

## Model Results

- KNN achieved high accuracy but very low recall, failing to identify divorced individuals effectively
- Logistic Regression provided balanced but moderate performance
- Decision Tree improved recall significantly
- Random Forest achieved the highest recall and performed best overall

Random Forest was selected as the best model due to its ability to detect the minority class.

---

## Confounding Variables

One limitation of this analysis is the presence of confounding variables.

Age, education, and income are interrelated:
- Older individuals may have different education levels
- Income is often influenced by education and employment
- These relationships make it difficult to isolate individual effects

Therefore, some observed relationships may be indirect rather than causal.

---

## Findings

The analysis shows that divorce is significantly related to socio-economic factors:

- Age has a strong relationship with divorce
- Education level affects divorce probability
- Income has a negative relationship with divorce
- Younger individuals show different divorce patterns

Overall, socio-economic conditions play an important role in marital stability.

---

## Repository Structure
├── eda.ipynb
├── ml_analysis.ipynb
├── README.md
├── requirements.txt
├── data/ (ignored)
