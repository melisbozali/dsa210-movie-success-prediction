# DSA210 Project - Divorce Analysis

## Project Overview
This project analyzes the relationship between divorce probability and socio-economic factors such as age, education level, and income.

The goal is to understand whether these variables have a statistically significant effect on divorce outcomes.

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

- Divorce rate by age group
- Divorce rate by education level
- Divorce rate by income groups

Key observations:
- Divorce rates increase with age up to middle age
- Higher education levels tend to have lower divorce rates
- Lower income groups show higher divorce rates

---

## Hypothesis Testing

The following statistical tests were applied:

### 1. Age vs Divorce (t-test)
- Result: Significant difference (p < 0.05)

### 2. Education vs Divorce (Chi-Square Test)
- Result: Significant relationship (p < 0.05)

### 3. Income vs Divorce (Mann-Whitney U Test)
- Result: Significant difference (p < 0.05)

### 4. Young (≤25) vs Divorce (Chi-Square Test)
- Result: Significant relationship (p < 0.05)

---

## Findings

The analysis shows that divorce is significantly related to socio-economic factors:

- Age has a strong relationship with divorce
- Education level affects divorce probability
- Income has a negative relationship with divorce
- Younger individuals are more likely to be associated with divorce

Overall, socio-economic conditions play an important role in marital stability.

---

## Repository Structure├── eda.ipynb
├── README.md
├── requirements.txt
├── data/ (ignored)
