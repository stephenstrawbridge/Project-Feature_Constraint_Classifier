# Project 4 - Hackathon - Good, Fast, Cheap
- Max Bosse
- Aziz Maredia
- Stephen Strawbridge
- Mike Winder

## Problem Statement

Make the best possible predictions of income greater than 50k, using 20 or fewer features.

## Data
Data was not restricted to the cheap sample. It is described in the following data dictionary:

|Feature|Type|Source|Description|
|---|---|---|---|
|age|int| large_train_sample.csv | Age of the individual | 
|workclass|float| large_train_sample.csv | Imputed mean of the workclass catagory | 
|fnlwgt|int| large_train_sample.csv | Estimated number of people this entry represents |
|education-num|int| large_train_sample.csv | A number to represent level of education | 
|marital-status|float| large_train_sample.csv | Imputed mean of the marital-status catagory | 
|occupation|float| large_train_sample.csv | Imputed mean of the occupation catagory | 
|relationship|float| large_train_sample.csv | Imputed mean of the relationship catagory | 
|sex|int| large_train_sample.csv | Binary representation of sex | 
|hours-per-week|int| large_train_sample.csv | Number of hours worked per week |
|native-country|float| large_train_sample.csv | Imputed mean of the native-country catagory |
|capital-gain|int| large_train_sample.csv | The capital gains of the individual |
|capital-loss|int| large_train_sample.csv | The capital losses of the individual |
|net_capital|int| large_train_sample.csv | The combined capital gains and losses |

## Analysis

The primary challenge that we faced durnign this project was to find an alternative to using dummy variables for our catagorical data. We overcame this difficulty by converting our catagorical data into numerical data that represented the probability a value in that catagory had an income over 50k.

![Figure: Marital Status Income](marital_status_income.png)

This figure shows an example of the values we imputed for the marital status catagory. It shows that the married catagories were more likely to have an income over 50k than the other catagories. The same process was applied to the other catagorical columns.

In addition we examined the correlation of several other engineered features. Features we explored included squared age, education-num and net_capital, and recatagorizing the education numbers. None of these additional features improved our model accuracy.

Once the data was fully numeric we created several models. Each model was examined to fine tune the hyper parameters.

- AdaBoost
- Random Forest
- Bagging Classifier
- Logistic Regression
- Decision Tree
- Support Vector Machine
- K Nearest Neighbors


## Conclusions

Our best performing model was the AdaBoost Model which had an train accuracy score of 0.8725 and a test accuracy score of 0.8694.

Our best fit (least overfit) model was the Logistic Regression which had a train accuracy score of 0.8368 and a test accuracy score of 0.8368.

## Next Steps

1. Continue optimizing hyperparameters on models test or try new models
2. Gather more data to improve predicitive power
3. Test other categorical variables (e.g. marital status, occupation) as dummies rather than imputing probabilites
4. Try testing numeric columns as dumified categorical variables. For example, turning values in the hours column to 'Part-time', 'Full-time', etc.
5. Test out variables as interaction terms and polynomial features.