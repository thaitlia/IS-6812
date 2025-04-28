# IS-6812: MSBA Practice Project

## Summary of Business Problem and Project Objective
### Business Problem Statement
Home Credit uses a variety of alternative data to predict a client’s likelihood of repayment. Although their current statistical models and machine learning methods are capable of making these predictions, the purpose of collaborating with Kaggle is to create a more robust and accurate prediction model to determine client repayment abilities – particularly with the unbanked population. 

### Benefit of a Solution
Being able to accurately predict how capable a client is able to repay a loan allows Home Credit to confidently back them and ensure they are given loans with a principal, maturity, and timeline best suited for them.

### Analytics Approach
Home Credit provides several transaction files describing a client’s financial history/background, as well as an application train and test set of data. The train set and additional files will be used to create a model for the target variable, TARGET – a binary response variable describing whether a client will have payment difficulties or not. The test set will be used to estimate the performance of the prediction model with cross-validation. 

## Group 4: "Hello World"'s Solution to the Business Problem
Our model was able to predict with a roughly 92% accuracy on both the train and test set data. We were able to identify key predictors in the data for prediction, narrowing it down to EXT_SOURCE_1, EXT_SOURCE_2, and EXT_SOURCE_3 as well as supporting transactional predictors such as DAYS_BIRTH and DAYS_REGISTRATION to help support the model. Additionally, the ROC-AUC performance metric when submitted to Kaggle, the collaborative partner on this project, showed a value of 0.65183, meaning that the model does do better than just randomly guessing which clients will have repayment difficulties.

Our solution then, would 

### Individual Contribution to the Project

### The Business Value of the Solution

### Difficulties Encountered

### Project Learnings
