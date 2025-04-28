# IS-6812: MSBA Practice Project

## Table of contents
- [Summary of Business Problem and Project Objective](#summary-of-business-problem-and-project-objective)
 	+ [Business Problem Statement](#business-problem-statement)
	+ [Analytics Approach](#analytics-approach)
- [Group 4 Solution to the Business Problem](#group-4-solution-to-the-business-problem)
- [Individual Contribution to the Project](#individual-contribution-to-the-project)
- [The Business Value of the Solution](#the-business-value-of-the-solution)
- [Difficulties Encountered](#difficulties-encountered)
- [Project Learnings](#project-learnings)

## Summary of Business Problem and Project Objective
### Business Problem Statement
Home Credit uses a variety of alternative data to predict a client’s likelihood of repayment. Although their current statistical models and machine learning methods are capable of making these predictions, the purpose of collaborating with Kaggle is to create a more robust and accurate prediction model to determine client repayment abilities – particularly with the unbanked population. This specific population usually does not have a typical credit score, preventing them from having access to the capital the general population has.

### Analytics Approach
Home Credit provides several transaction files describing a client’s financial history/background, as well as an application train and test set of data. The train set and additional files will be used to create a model for the target variable, TARGET – a binary response variable describing whether a client will have payment difficulties or not. The test set will be used to estimate the performance of the prediction model with cross-validation. 

## Group 4 Solution to the Business Problem
Our model was able to predict with a roughly 92% accuracy on both the train and test set data. We were able to identify key predictors in the data for prediction, narrowing it down to EXT_SOURCE_1, EXT_SOURCE_2, and EXT_SOURCE_3 as well as supporting transactional predictors such as DAYS_BIRTH and DAYS_REGISTRATION to help support the model. Additionally, the ROC-AUC performance metric when submitted to Kaggle, the collaborative partner on this project, showed a value of 0.65183, meaning that the model does do better than just randomly guessing which clients will have repayment difficulties.

Our recommended solution then, would be to streamline the transactional data collection process within Home Credit, making it so that client's would not have to fill out as much paperwork given the key predictors identified in the modeling. This allows faster turnaround for both client's and the business. Along with that, we would apply our model for these new applications, identifying the clients who may default and giving Home Credit the opportunity to mitigate the risk by taking a closer look at the applicant and creating a repayment plan better suited for them. 

## Individual Contribution to the Project
My partner, Tina, and I initally started the modeling assignment where she tackled RandomForst modeling while I tackled xgBoosting. However, the results I recieved from xgBoosting were not interpretable, thus that pathway was scrapped and I worked on supporting the RandomForest modeling by taking the key predictors and trying them in various logistic regression models. I also cross-validated each iteration of the various models with different combinations of predictors, decided and formulated the performance metrics such as the ROC-AUC curve, and wrote a majority of the Modeling Assignment. In order to get the cross-validation to work successfully, after discussion with Tina, instead of proportionally filling missing values (NA's), I went and readjusted our script to fill NA's with either the mode or median. The final presentation was a combination of both Tina and I in terms of writing, layout, and structure. 

## The Business Value of the Solution
Let’s say we increased the sample size to 100,000 random clients that came to Home Credit seeking a loan. Based on the application data that we received, hypothetically, that would mean that Home Credit has credited $59.8 billion dollars in total. However, out of those 100,000 random clients that were credited, 8,039 of those clients were marked as a TARGET variable of 1, meaning they defaulted on their payments. That in turn causes a loss of roughly $4.46 billion dollars, ultimately resulting in a loss of 7.46%. How do you recuperate that loss, or better yet, how do you prevent it from happening in the first place?

Well, with our model, if we were to accurately predict 92% of those 1000,000 clients, whether they would default or not based on predictors ahead of time, then within that 92%, we would’ve been able to predict 7,395 potential defaulters. That total credit amount is summed to be roughly $4.1 billion dollars for those clients - but in this hypothetical, since we were able to have hindsight, Home Credit would’ve been able to address these potentially risky repayment plans, thus saving the company $4.1 billion dollars. That’s a 6.85% decrease from what would be baseline, dropping loss down to 0.61%.

Being able to accurately predict how capable a client is able to repay a loan allows Home Credit to confidently back them and ensure they are given loans with a principal, maturity, and timeline best suited for them. 

## Difficulties Encountered
I would say the greatest difficulty was the amount of transactional data given. We learned early on that taking a sample from the overall population was needed if we wanted R Studio to be able to run the model and give predictions in a timely manner. 

## Project Learnings
This was discussed in one of our 
