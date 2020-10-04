# Evaluation of Credit Risk

# using Machine Learning

## Prepared by:

## Mostofa Ahsan

## 3rd October 2020


# Contents

- Business problem and data understanding
- Train and test data distribution comparison
- Exploratory Data Analysis
    - Categorical, missing values, outlier detection
    - Data Visualization
    - EDA Questions
- Machine Learning pipeline
- Model Interpretability
    - Predictions and Definition of credit worthiness learned by ML model
- Comprehensive guide to elaborate selection criteria


## Business problem: Credit worthiness Evaluation

- **Credit Risk:** Risk of witnessing defaults on a debt that

###### may arise from a borrower failing to make required

###### payments.

- **Business Objective:** To learn from the association

###### between the traits and attributes of different

###### borrowers in history and their repayment status i.e.

###### whether it resulted in Good Risk or Bad Risk

- **Target Variable** : Good (class 1, creditworthy) vs Bad

###### (class 0, not creditworthy) Risk

- **Data* Description:** 1000 records with 10 features
- The dataset is divided into 90%-10%:
    - **Train -** 900
    - **Test -** 100
    
    
    ![Credit_risk_1](https://user-images.githubusercontent.com/34641108/95004702-5dbf4380-05b4-11eb-845c-d2d50231a18e.JPG)
    
    * The data downloaded from the link did not have column headers, hence found discrepancies in column names and their values. This is a trimmed version of German Credit Risk data found by web search


### Generalization

### Power: train and test

### distribution similarity

- One of the most critical assumption in ML data modelling is that **train and test dataset
belong to similar distribution** , as is evident from graphs above. Note that the train data is
used as a reference to **estimate** the future credit worthiness of customers, hence the ML
solution is probabilistic one and not guaranteed based on past data. This emphasizes **the
property of generalization of ML solution**

```
KS statistic is a numeric measure to check the hypothesis of whether the distributions of 2
dataset is same. For e.g. KS statistic > p value implies same distribution
```
Blue colour histogram is from Train data and Green

colour is from Test data, the histogram plots from

two distribution are sharing significant overlap with

each other implying that there is no drift between

the two datasets and that they are drawn from

same distribution.
![Credit_risk_distribution](https://user-images.githubusercontent.com/34641108/95004721-b5f64580-05b4-11eb-80b8-66120c9f42f0.JPG)



## Exploratory Data Analysis```
#### 1) Missing Value Treatment

![Missing_Values](https://user-images.githubusercontent.com/34641108/95004761-42a10380-05b5-11eb-88d4-0972302c2a3a.JPG)

#### 2) Categorical Value Treatment

![image](https://user-images.githubusercontent.com/34641108/95004766-59dff100-05b5-11eb-8c7f-0320a7acdc95.png)


#### 3) Outlier analysis

![image](https://user-images.githubusercontent.com/34641108/95004776-6fedb180-05b5-11eb-9a5b-9ed0ec10ba0a.png)

The cut off value and corresponding number of instances falling out of 3 sigma are shown in the table to the right:
As these values look legitimate in the context of credit risk modelling, I am not treating them as outliers
```

## EDA Questions

![image](https://user-images.githubusercontent.com/34641108/95004822-ec809000-05b5-11eb-9c14-69e26d31d5e0.png)



