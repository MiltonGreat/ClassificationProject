# Classification Project
Classification Project
Telco Customer Churn Prediction

A. Project Overview

This project focuses on a classification problem. The goal is to analyze and predict customer churn for a telecommunications company. The dataset contains various demographic and service-related information about 7043 customers, including their churn status, satisfaction score, churn score, and customer lifetime value (CLTV).

B. Data Cleaning and Preparation

•	Identified and Removed Redundant Columns: Checked for unique CustomerID to confirm its uniqueness. Identified Count column as redundant since only had one unique value.
•	Geographical Data Cleaning: Dropped City, lat_lon, Latitude, Longitude, Country, and State columns as redundant or had only one unique value (e.g., all entries in Country were the same).
•	Customer Demographics: Evaluated columns like Gender, Senior Citizen, Partner, and Dependents for relevance, deciding to drop Gender to avoid bias in interpretation.
•	Service-Related Columns: Assessed and retained service-related columns like Phone Service, Internet Service, and their add-on services (Multiple Lines, Online Security, etc.).
•	Payment Information: Considered dropping columns like Paperless Billing and Payment Method due to variability in customer choice but noted their potential indicative power.
•	Charges Data: Kept Monthly Charges and Total Charges as important features. Identified and handled missing values in Total Charges, replacing blank spaces (' ') with 0.
•	Target Variable: Evaluated Churn Label and Churn Value, noting they encode the same information and decided to keep one. Checked the distribution of the target variable.
•	Derived Dataset: Created a smaller DataFrame (churn_v1) with selected relevant features. Encoded binary categorical variables (Yes/No) as 1/0.
•	Data Type Conversion: Converted Total Charges to numeric after handling missing values.
• Baseline Visualization: Visualized the distribution of the target variable (Churn Value).
•	Correlation Analysis: Computed and visualized correlations between numeric variables and the target variable.

B. Exploratory Data Analysis (EDA) 

•	Distribution of Target Variable: Examined the distribution of the Churn Value using a count plot to understand the balance of the target variable.
•	Correlation Analysis: Computed correlations between numerical features and the Churn Value using the .corr() method. Visualized the correlations with a heatmap to identify which features are most strongly associated with churn.
•	Visualization of Important Features: Plotted histograms and box plots for key numerical features (Churn Score, Tenure Months, Monthly Charges, and Total Charges) to understand their distributions and relationships with the target variable.
•	Feature Distributions and Relationships: Plotted the distribution of Churn Score for customers who churned vs. those who did not using seaborn's kdeplot. Examined the distribution of Tenure Months with histograms and kdeplots to see if there are differences between customers who churned and those who didn't. Plotted Monthly Charges and Total Charges distributions and analyzed their relationships with churn using histograms and kdeplots.
•	Categorical Feature Analysis: Created count plots for categorical features like Senior Citizen, Partner, Dependents, Phone Service, Internet Service, and other service-related features to observe their distributions and potential relationships with churn. Evaluated features related to the services customers have subscribed to and their impact on churn.
•	Joint Distributions: Used scatter plots and pair plots to examine the joint distribution of pairs of numerical features and their relationships with churn.
•	Outlier Detection: Utilized box plots to detect potential outliers in numerical features such as Monthly Charges and Total Charges.

C. Feature Engineering

•	Mapping Categorical Variables: Converted binary categorical features (Senior Citizen, Partner, Dependents, Phone Service, Paperless Billing, Churn Value) from Yes/No to 1/0 or True/False values for easier processing by machine learning algorithms.
•	One-Hot Encoding for Non-Binary Categorical Variables: Applied one-hot encoding to non-binary categorical features (Multiple Lines, Internet Service, Online Security, Online Backup, Device Protection, Tech Support, Streaming TV, Streaming Movies, Contract, Payment Method) to convert them into a format suitable for machine learning models.
•	Normalization of Numerical Features: Normalized numerical features (Monthly Charges, Total Charges, Tenure Months) to ensure they have similar scales, which helps improve the performance of machine learning algorithms.

D. Feature selection:

Throughout the modeling process, different combinations of features were selected and tested. The feature selection process in the code provided involves the use of Recursive Feature Elimination (RFE) with a Random Forest Classifier.

E. Modeling

Three classification models are compared:

•	Logistic Regression
•	Random Forest Classifier
•	Support Vector Classifier (SVC)

A final pipeline was created that includes:

•	Custom transformers for service-related features
•	Preprocessing steps (scaling, encoding)
•	The chosen model (in this case, Logistic Regression)

F. Validation Scheme

Cross-validation is used to evaluate the performance of the models. The dataset is split into training and test sets, and cross-validation is applied to the training set to ensure robust performance evaluation.

E. Evaluation

Logistic Regression was the final model chosen. Model performance is evaluated using the following metrics:

•	Confusion Matrix    
•	Accuracy
•	Precision
•	Recall
•	F1 Score
•	ROC-AUC
•	Cross-Validation

Logistic Regression provides the best scores on accuracy, precision, recall, and F1 score based on our need, and had a good AUC, indicating its effectiveness in predicting churn.

F. Conclusion

The analysis and modeling steps successfully identify important features and predict customer churn. The final model provides insights into the factors contributing to churn and can be used to make strategic decisions for customer retention.

Source: https://community.ibm.com/community/user/businessanalytics/blogs/steven-macko/2019/07/11/telco-customer-churn-1113
