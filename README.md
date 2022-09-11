# Predicting Mortgage Approvals from Government Data

June, 2019

## Executive Summary

This report presents an analysis of data with regards to mortgage approvals from a given dataset, adapted from the Federal Financial Institutions Examination Council's (FFIEC). The analysis is  based on 500,000 observations of mortgage data with 21 features and 1 Label, each containing  specific characteristics of HMDA-reported loan application, which covers one particular year. After exploring the data by calculating summary and descriptive statistics, and by creating  visualizations of the data, several potential relationships between mortgage features and the status of an application were identified. After data exploration, data cleaning and some transformations were performed on the features after which a predictive model to classify mortgage loan application into two categories: accepted and not accepted was created. After performing the analysis, the author presents the following conclusions: 

While many factors can help indicate whether a mortgage loan approval gets accepted or not, significant features found in this analysis were:

1. Applicants Income: The income of most applicants is between 0 to 100, 000 dollars.
2. Loan Amount: An integer variable that represents the size of the requested loan in thousands of dollars. The amount of loan requested by most applications is below 400,000 dollars.
3. Loan Purpose: Indicates whether the purpose of the loan or application was for home purchase, home improvement, or refinancing.
4. Number of Family units.

### Exploratory Data Analysis

More details about data exploration and analysis can be found [here](Grace_Ufeoshi_Project_Report.pdf). The full code to the data exploration can also be found [here](MortageApprovalPrediction.ipynb)

### Classification of Mortgage Application Based on Acceptance

Based on the analysis of the mortgage application data, a predictive model to classify mortgage applications into two categories: application accepted (meaning the loan was originated) or denied was created. During the model development, the following were taken into  consideration:

1. Dealing with missing values using the mean and median
2. Z-score normalization was done for the features with normal distribution while min-max normalization was done for features with irregular distribution.
3. Feature selection was done using chi-square feature scoring method

The model was created in Microsoft Azure ML using the Two-Class Boosted Decision Trees algorithm and trained with 70% of the data. Testing the model with the remaining 30% of the data yielded the following results. Validation was further done with 100% of the test data provided.

* True Positives: 58050
* True Negatives: 47428
* False Positives: 27274
* False Negatives: 1724

This translates into the following standard performance metrics for classification: 
    * Accuracy: 71.2% 
    * Precision: 68% 
    * Recall: 77.1% 
    * F1 Score: 72.3%

### Conclusion

This analysis has shown that the mortgage applications can be confidently predicted from its  characteristics. In particular, the applicant’s income, loan amount, loan purpose, and  ffiecmedian_family_income has a significant effect on the acceptance or denial of a mortgage application

*ps: This is part of the required projects undertook to earn the Microsoft Professional Program in Data Science Certificate.*