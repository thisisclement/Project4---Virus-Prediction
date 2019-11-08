# Project4---Virus-Prediction

#### Refer to 'proj4_eda' notebook for data cleaning and exploratory analysis
#### Refer to 'proj4_cba' notebook for cost benefit analysis of spraying to minimize the threat of the West Nile Virus

## 1. Introduction

## Introduction
The objective of this project is to predict the presence of the West Nile Virus in the city of Chicago and to conduct a cost benefit analysis of spraying insecticide as a counter-measure.

## Data
##### 4 sets of data are provided:
1) Weather records (2,944 rows) from 2007-05-01 to 2014-10-31<br>
2) Spray records (14,835 rows) from 2011-08-29 to 2013-09-05<br>
3) Training records (10,506 rows) from 2007-05-29 to 2013-09-26<br>
4) Testing records (116,293 rows) from 2008-06-11 to 2014-10-02<br>
## Project Submission
The submission comprises 2 jupyter notebooks:<br>
1) Project Presentation<br>
2) proj4_eda.ipynb (Data cleaning and EDA)<br>
3) proj4_model.ipynb (Modelling)<br>
## Data Cleaning/Preprocessing and EDA
##### Cleaning
1) Removal of duplicates rows or rows with too many missing values<br>
2) Imputing of Weather data collected from Station 2<br>
##### Preprocessing
1) For each row in Train & Test data, determine which is the nearest weather station (Station 1 / Station 2)<br>
2) Merging of Train & Test data with weather data from nearest weather stations (Station 1 / Station 2)<br>
3) Generation of additional features<br>
##### EDA
1) Correlation between weather features and Number of Culex Mosquitoes trapped, WNV presence<br>
2) Time series analysis between Number of Culex Mosquitoes trapped and extent of WNV presence<br>
3) Multicollinearity between weather features<br>
4) Evaluation of the effect of spraying on WNV presence<br>
## Models
##### Further Feature Engineering & Selection
1) Creation of a long-lat column<br>
2) Dummied<br>
3) Top 40 correlated feature selected<br>
4) Train-test-split on train.csv, while test.csv was maintained<br>
5) Polynomial with degree 2 and standard scalar<br>
6) Oversampling using Synthetic Minority Over-Sampling Technique (SMOTE)<br>
##### Find best performing model using GridSearch on classification models:
1) LogisticRegression()<br>
2) KNeighborsClassifier()<br>
3) DecisionTreeClassifier()<br>
4) RandomForestClassifier(n_estimators=100)<br>
5) ExtraTreesClassifier(n_estimators=100)<br>
6) GradientBoostingClassifier(n_estimators=100)<br>
7) AdaBoostClassifier(n_estimators=100)<br>
## Cost-Benefit Analysis
1) Effectiveness of spraying is estimated at about 50%<br>
2) Costs of spraying based on insecticide product Zenivex®E4<br>
3) Determine projected cost of insecticide to be used<br>
## Conclusions and Recommendations
We conclude that spraying should be carried out to suppress the number of Culex mosquitoes, and that public should be educated to take preventive measures to minimize the inadvertent breeding of mosquitoes in general.<br>
We also recommend the following:<br>
1) Study migratory patterns of WNV-infected birds<br>
2) Study interactions between WNV-infected birds and Culex mosquitoes<br>
3) Regression analysis to predict the number of Culex mosquitoes








__Problem Statement:__ 
<br>Given a post from either of two subreddits, I would like to understand, using machine learning, whether it is possible to identify which subreddit it belongs to.

__Choice of Subreddit:__ 
<br>The two subreddits I would like to explore in this project are __r/nosleep__ and __r/randomactsofkindness (abbrev: r/raok)__:

- Nosleep is a subreddit for realistic horror stories.
- Randomactsofkindness is a subreddit for non-fictional stories on inspiration and kindness occurences. 

<br> The narrative, story-based nature of both subreddits present an interesting classification challenge, despite little overlaps in the topic.

## 2. Executive Summary

Posts from both subreddits are scraped using API, analyzed, cleaned, processed and ran through several classification models (e.g. Logistic Regression, KNearestNeighbor, Decision Tree Classifier). 

The model that performed the best came from a __Logistic Regression with Count Vectorizer__, at a classification prediction accuracy rate of __99%__. 

The high accuracy rates are unsurprising for two reasons:
- Both posts engage in topics that have very little overlap, leading to distinct classification identifiers from both posts;
- r/nosleep is fictional, while r/raok is non-fiction, further distincting the language that is used in both subreddits.

While the model performed best for this two subreddits, it can be further stress-tested in situations where:
- A 3rd subreddit is introduced;
- Two subreddits with more topical overlap are used
