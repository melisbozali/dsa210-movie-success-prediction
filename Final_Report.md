# Divorce Analysis Using IPUMS USA Data

## Motivation

I chose this project because divorce is both a personal and social topic. It is not only about individual relationships, but also connected with age, education, income, employment, and other socio-economic conditions. I wanted to understand whether large-scale census data can show patterns related to divorce status.

My main goal was not to say that one variable directly causes divorce. Instead, I wanted to use data science methods to explore which variables are related to divorce and whether these variables can be used to build a predictive model.

## Data Source

The data was collected from IPUMS USA, which provides census and American Community Survey microdata. I used an IPUMS extract that includes individual-level demographic and socio-economic variables.

The main variables used in the project include marital status, age, sex, education, employment status, wage income, and other available socio-economic variables such as poverty ratio and work hours when they exist in the extract.

The target variable was created from marital status:

- `divorced = 1` for divorced or separated individuals
- `divorced = 0` for other previously married individuals

I removed never-married individuals from the analysis because they cannot be divorced. This makes the comparison more meaningful.

## Data Analysis

The project has two main parts: exploratory data analysis and machine learning.

In the exploratory data analysis, I first cleaned the data and created the target variable. Then I examined the distribution of divorce status and compared divorce rates across age groups, education levels, income groups, and employment status. I also used a correlation heatmap to understand the relationships between numeric variables.

In the machine learning part, I used both original IPUMS variables and engineered features. The engineered features include log income, income groups, age groups, high education indicator, employment indicator, age squared, and interaction features such as age-income and education-income interactions. These additions make the model more detailed than using only basic variables.

I compared multiple classification models:

- Logistic Regression
- KNN
- Decision Tree
- Random Forest
- Gradient Boosting

Since the target variable is imbalanced, I did not rely only on accuracy. I also used precision, recall, F1 score, ROC-AUC, confusion matrices, and ROC curves. Logistic Regression used `class_weight="balanced"` to handle class imbalance.

## Findings

The exploratory analysis showed that divorce status is related to multiple variables. Age is an important factor because divorce rates are not the same across all age groups. Income and education also show visible differences across divorce status, although these relationships should not be interpreted as direct causality.

The machine learning results show that divorce is difficult to predict perfectly from census variables alone. This is expected because divorce depends on many personal and relationship-level factors that are not included in census data. However, the models were still useful for finding patterns.

Tree-based models such as Random Forest and Gradient Boosting were useful because they can capture non-linear relationships. Random Forest also helped show feature importance, which made the model easier to interpret. The most useful predictors generally came from age, income, education, employment, and engineered interaction features.

Overall, the project shows that census data can reveal meaningful patterns about divorce, but it cannot fully explain such a complex life outcome by itself.

## Limitations and Future Work

The biggest limitation is that the data is observational. This means the project cannot prove that one factor causes divorce. It can only show relationships and predictive patterns.

Another limitation is that many important personal factors are not included in the dataset. For example, the data does not include relationship quality, family conflict, cultural expectations, religion, or detailed household history. These factors could be important for understanding divorce more deeply.

The machine learning section uses a sample of the full dataset to reduce computational cost and make the notebook easier to run on standard hardware. Future work could train the models on the full dataset with more computing power. It could also include more IPUMS variables, compare different years, or analyze differences across states, gender groups, or education levels in more detail.

In the future, I would also like to test more advanced models and add stronger explanations using SHAP values or other interpretability tools. This would make it easier to understand how each variable affects model predictions.

## AI Assistance Note

AI tools were used for help with code organization, debugging suggestions, and wording support. The project topic, dataset, analysis decisions, notebook execution, and final interpretation were checked and completed by me.
