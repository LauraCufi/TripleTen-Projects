Churn Prediction for Telecom Operator Interconnect
This project aims to forecast client churn for the telecom operator Interconnect, allowing them to proactively offer promotional codes and special plans to retain clients identified as at risk of leaving. The data, collected by Interconnect’s marketing team, includes personal details, plan and contract information, and records of internet and phone services.

Project Structure
This repository consists of four key datasets and a comprehensive analysis pipeline:

contract.csv — Contract details
personal.csv — Client personal information
internet.csv — Internet service details
phone.csv — Telephone service details
Workflow Overview
The analysis and model-building process was divided into the following stages:

1. Data Exploration and Cleaning
Data Consolidation: All datasets were merged into a single, unified dataframe.
Missing Values: Missing entries in the TotalCharges column (representing ~0.15% of total data) were filled with the column's mean. Missing values in categorical columns were filled with the mode.
Data Formatting: Categorical data was encoded into binary (1 or 0) for model compatibility.
2. Exploratory Data Analysis (EDA)
Analyzed target column EndDate to identify a class imbalance: active clients were labeled "1," while churned clients were labeled "0."
3. Preprocessing and Feature Selection
Applied label encoding to binary columns.
Addressed class imbalance using the upsampling technique, conducting analyses both with and without upsampling to compare outcomes.
4. Machine Learning Model Training
Trained three models: Decision Trees, Random Forest, and Logistic Regression, with and without upsampled data.
Initial findings:
Random Forest: Achieved a perfect AUC-ROC score (1.00) without upsampling, suggesting potential overfitting.
Decision Trees: Scored an AUC-ROC of 0.87.
Logistic Regression: Maintained a steady AUC-ROC of 0.83.
Hyperparameter Tuning: Retrained the Random Forest model with GridSearchCV to improve generalization, resulting in the best performance:
AUC-ROC: 0.91
Accuracy: 83.76%
Conclusion
This project successfully developed a robust churn prediction model for Interconnect, identifying key factors contributing to client retention. The tuned Random Forest model provides actionable insights with a high AUC-ROC, supporting targeted retention strategies.

Contact
For any inquiries, please reach out via [LinkedIn](https://www.linkedin.com/in/lauracufino/) or lauralilicg@gmail.com
