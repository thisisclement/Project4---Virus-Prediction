# Project4---Virus-Prediction

#### Refer to 'proj4_eda' notebook for data cleaning and exploratory analysis
#### Refer to 'proj4_modelling' notebok for data modelling, model selection and evaluation
#### Refer to 'proj4_cba' notebook for the cost benefit analysis of spraying in Chicago to minimize the threat of the West Nile Virus

## Introduction
The West Nile Virus is a single-stranded RNA virus that causes West Nile fever found commonly in the hotter regions of Africa, Europe, the Middle East, North America and West Asia. It is a member of the family Flaviviridae, specifically from the genus Flavivirus, which also contains the Zika virus, dengue virus, and yellow fever virus. Transmitted primarily by the Culex species of mosquitoes, it is maintained in nature in a cycle involving transmission between birds and mosquitoes.

At the time the competition, there was a recent eipdemic of the virus in Chicago, and the Department of public Health had set up a surveillance and control system, to learn about and combat the epidemic.

__Problem Statement:__ 
<br> To establish a model that support the eradication of the West Nile Virus in Chicago, by detecting and suppressing the population of Culex mosquitoes in a cost effective and sustainable manner.

## Executive Summary
Data provided (train.csv, test.csv) was analyzed, cleaned, processed and ran through several classification models (e.g. Logistic Regression, KNearestNeighbor, Decision Tree Classifier). 

The model that performed the best came from a __AdaBoost Classifier__, with a parameter of 0.73 for learning rate. 

It is recommended that the city of Chicago continues its spray routine, in order to suppress the number of Culex mosquitoes, and that the public should be educated to take preventive measures to minimize the inadvertent breeding of mosquitoes. 

<br>
We also recommend the following:<br>
1) Study migratory patterns of WNV-infected birds<br>
2) Study interactions between WNV-infected birds and Culex mosquitoes<br>
3) Regression analysis to predict the number of Culex mosquitoes

---------------------------------------

## Data
##### 4 sets of data are provided:
1) Weather records (2,944 rows) from 2007-05-01 to 2014-10-31<br>
2) Spray records (14,835 rows) from 2011-08-29 to 2013-09-05<br>
3) Training records (10,506 rows) from 2007-05-29 to 2013-09-26<br>
4) Testing records (116,293 rows) from 2008-06-11 to 2014-10-02<br>
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
