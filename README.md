# IS-6812: MSBA Practice Project

## Table of Contents
- [Summary of Business Problem and Project Objective](#summary-of-business-problem-and-project-objective)
 	+ [Business Problem Statement](#business-problem-statement)
	+ [Project Objective](#project-objective)
- [Group 4 Solution to the Business Problem](#group-4-solution-to-the-business-problem)
- [Individual Contribution to the Project](#individual-contribution-to-the-project)
- [The Business Value of the Solution](#the-business-value-of-the-solution)
- [Difficulties Encountered](#difficulties-encountered)
- [Project Learnings](#project-learnings)

## Individual Notebooks
| Notebook Title  | About | Link |
| :---: | :---: | :---: |
| Random Sampling of Home Credit Default Risk Files | Speaker - GDG & Women Techmakers - Machine Learning #3 | 18.10.2017 | ([Home Credit Default Risk EDA.Rmd](https://github.com/thaitlia/IS-6812/blob/b99bb5fd72137b7be76c951ba2d335152e1b6280/Final%20Presentation%20Modeling.Rmd)) |
| Soft introduction into MSE based Linear Regression (part 2 of 'What this Machine Learning is all about?' talk)  | Azimo Lunch & Learn | 16.11.2017 | [Link](https://speakerdeck.com/f1sherkk/soft-introduction-to-mse-based-linear-regression) |
| Advantages of Batch Normalization in Deep Learning | PyData Warsaw, Let’s meet to talk about AI in Bialystok #2 | 10.04.2018, 01.06.2018 | [Link](https://www.youtube.com/watch?v=9mI-viU9U0E) |

## Summary of Business Problem and Project Objective
### Business Problem Statement
Home Credit uses a variety of alternative data to predict a client’s likelihood of repayment. Although their current statistical models and machine learning methods are capable of making these predictions, the purpose of collaborating with Kaggle is to create a more robust and accurate prediction model to determine client repayment abilities – particularly with the unbanked population. This specific population usually does not have a typical credit score, preventing them from having access to the capital the general population has.

### Project Objective
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
The greatest difficulty was the amount of transactional data given. We learned early on that taking a sample from the overall population was needed if we wanted R Studio to be able to run the model and give predictions in a timely manner. However, it was a challenge deciding how big the sample size should be, but we ultimately decided 100,000 as a sample size was enough to get a general sense within our performance metrics. Additionally, the missing values were a big discussion topic - how much missing data could elicit deleting the predictor itself and would it matter? Given how many predictors there were, there was also discusssion on multicollinearity and which predictors was a better representation for others. 

## Project Learnings
This was discussed in one of our feedback sessions, but for some reason, it didn't occur to us that we didn't have to use a logistic regression model - RandomForest is a type of supervised machine learning algorithm for both classification and regression problems. It would have been sufficient to have just used that, rather than use it along with logistic regression. With that, we should have honed in on that model and played more with the hyperparameters to see if that increased our performance metrics. 

This project was a great representation of real world data science - the data given will never be as perfect as those in built-in R dataframes like mtcars. Missing values are a constant problem and deciding how to deal with them are nuances that are built the more you practice data science. I learned that, as outlined within the CRISP-DM cycle, new discoveries in the modeling led us back to re-evaluate our initial exploratory data analysis, EDA, and fine tune the predictors and decide whether we did need them or not or if they needed re-adjustment after our transformations such as replacement of NA's. 
