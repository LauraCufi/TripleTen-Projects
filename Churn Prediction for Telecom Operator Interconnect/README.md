# Churn Prediction for Telecom Operator Interconnect

## Project Overview

This project aims to forecast client churn for the telecom operator **Interconnect**, enabling proactive customer retention strategies through promotional offers and specialized plans for clients at risk of leaving. The analysis uses data provided by Interconnect's marketing team, which includes client demographics, contract details, and service usage.

## Datasets

The following datasets were used in the analysis:

- **contract.csv** — Contract information
- **personal.csv** — Client personal data
- **internet.csv** — Details on internet services
- **phone.csv** — Details on phone services

## Workflow

### 1. Data Exploration and Cleaning

- **Data Consolidation**: Merged all datasets into a single dataframe.
- **Handling Missing Values**: 
  - Missing values in `TotalCharges` were filled with the column mean (representing ~0.15% of total data).
  - Categorical columns were filled with the mode.
- **Data Formatting**: Encoded categorical data to binary values (1/0) for model compatibility.

### 2. Exploratory Data Analysis (EDA)

- Examined the target column `EndDate` to identify class imbalance, where "1" denotes active clients and "0" denotes churned clients.

### 3. Preprocessing and Feature Selection

- **Label Encoding**: Applied to binary columns.
- **Handling Class Imbalance**: Upsampling was applied, with analyses conducted both with and without upsampling for performance comparison.

### 4. Model Training and Evaluation

- Trained three models: **Decision Tree**, **Random Forest**, and **Logistic Regression**.
- Initial results:
  - **Random Forest** achieved a perfect AUC-ROC score (1.00) without upsampling, likely due to overfitting.
  - **Decision Tree** had an AUC-ROC of 0.87.
  - **Logistic Regression** maintained an AUC-ROC of 0.83.
- **Hyperparameter Tuning**: The Random Forest model was retrained using GridSearchCV to mitigate overfitting, resulting in improved performance:
  - **AUC-ROC**: 0.91
  - **Accuracy**: 83.76%

## Results and Conclusion

This analysis produced a reliable churn prediction model for **Interconnect**, highlighting significant factors contributing to client retention. The tuned Random Forest model offers strong predictive capabilities, supporting data-driven retention strategies with a high AUC-ROC score.

## Contact

For questions or collaboration, please connect via [LinkedIn](#) or email.


