# Project4---Virus-Prediction

#### Refer to <notebook name> notebook for data cleaning, analysis and modelling
#### Refer to 'Reddit Scrapping' notebook for Praw's Reddit API Wrapper

## 1. Introduction

Reddit is an America-based social news aggregation, web content rating, and discussion website. Registered members submit content to the site in the form of links, text posts, and images, which are then voted up or down by other members. Subreddits are forums dedicated to specific topics (e.g. football, Avengers movie, food) within Reddit. <br>
<br>Given the open nature of the forums, topics are rarely moderated, unless deemed to be flouting Reddit's usage policy, and can have high level of overlaps (e.g. Machine Learning and Artificial Intelligence).

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
