# Evaluation of Credit Risk using Machine Learning

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
```
The cut off value and corresponding number of instances falling out of 3 sigma are shown in the table to the right:
As these values look legitimate in the context of credit risk modelling, I am not treating them as outliers
```

## EDA Questions


![image](https://user-images.githubusercontent.com/34641108/95004886-be4f8000-05b6-11eb-98c9-c37812fe82e4.png)

## EDA Questions -- Continued

##### Q3: Are young people more credit worthy?

```
As evident in the chart, the proportion of Bad with respect to Good
shows a downward trend as the Age increases, hence we conclude that
aged people default lesser number of times which in turn says, young
people have more tendency to default.

Dividing Age variable into following 3 brackets:

```

![image](https://user-images.githubusercontent.com/34641108/95004844-3a959380-05b6-11eb-85cc-98b71636180a.png)
![image](https://user-images.githubusercontent.com/34641108/95004850-4da86380-05b6-11eb-975c-d974d298e56c.png)
![image](https://user-images.githubusercontent.com/34641108/95004855-60229d00-05b6-11eb-8387-daf2ebef77da.png)


- Rationale behind creating such Age bins:
    - Age < 30: Could comprise of Loan seeking, affluent spenders
    - 30<Age<45: Generally consists of married people seeking financial
       security for family, or as an investment vehicle
    - Age>45: Averse to seeking loans, in general (could have made this to
       Age 50, but sample size would have gone smaller)


## Machine Learning Pipeline

![image](https://user-images.githubusercontent.com/34641108/95004876-9cee9400-05b6-11eb-99ae-65aa1b114c46.png)

## Prediction and Definition of credit worthiness learned from

![image](https://user-images.githubusercontent.com/34641108/95004897-d9ba8b00-05b6-11eb-8bfd-597499962ca4.png)



## Model Selection Criteria
- F score is generally used as evaluation metric when there is no preference between Recall and Precision
    - **2PR/(P+R),** where
    - P: Precision: focus on reducing False Positives (FN)
    - R: Recall: focus on reducing False Negatives (FN)
- Relevance of importance of Recall vs Precision in our example:
    - As per the given report, **there is a cost on classifying the customer as good when they are bad** , i.e.

##### predicting Good Risk (class 1, positive class) when it is False i.e. False Positives (FP) draw heavy

##### penalty based on our business objective

- Precision = TP/(TP+FP), so our goal is to prioritize Precision which in turn will reduce the FP
- **Had the objective been to give penalty on predicting bad when they are good i.e. based on ML**

##### recommendations, we are refraining from lending, we would have lost business.

- In that case, the focus would be on False Negatives i.e. you are predicting Bad Risk (class 0, negative

##### class) while the customer was in Good Risk category. So, we predicted negative which went wrong

##### implying lesser FN, which in turn would lead to more weight on Recall (TP/TP+FN)

![image](https://user-images.githubusercontent.com/34641108/95004932-839a1780-05b7-11eb-9d75-a3aad340fdab.png)

