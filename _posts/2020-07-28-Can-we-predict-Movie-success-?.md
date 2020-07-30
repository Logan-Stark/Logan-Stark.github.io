---
layout: post
title: Predicting Success
subtitle: Can we use machine learning to predict how successful a movie will be?
tags: [Movies]
comments: true
---

Insert image of movie related thing.

## Introduction

  One of the things i have missed the most during quarantine is going out to the movies. Since all the theatres are closed its made me think "what makes a movie successful?". There are hundreds of thousands of different movies that have been produced over the years. some of these movies break box office records while while others will go unheard of. The goal of this post is to make a predictive model for movie success and explain important features.
  
## Data exploration and Target selection
  
  We will be using data gathered from the Movies.Meta dataset on kaggle.com. This data contains many different features sucha as revenue, facebook likes, actors, and duration. for my model i decided to create a new feature called [success] to serve as our target. [success] will help us gauge how successful a given movie is by taking the gross revenue made and dividing it by the budget. by doing this we recieve a number that shows how much money was made in realtion to the money already spent on the budget. for instance if a movies success is less than 1 we know the movie spent more than it made. we can then make our target binary by assigning any movie that has a succes of less than 1 to unsuccessful and any gretaer than 1 successful.
  
## Baseline Model
  
  Using our new target we can make a baseline model for our future models to compete against. we can make our baseline model by computing the value counts of of our target and graphing it. in our graph 1 represents successful while 0 represents unsuccessful. our graph shows an almost 50/50 split in movie success. since the majority class is 1 our baseline to beat in our models will be 52% 
  
## Engineered models

  After removing features with High cardinality and missing values i split my data into a training, validation, and testing set. I Used these sets to fit 4 different models
and test their accuracy. the classifiers i used to train these models were Logistic regression, RandomForestClaassifier, and XGBClassifier. Each of these classfiers is unique in their own way.

**Logistic Regression** is a Linear Classification model. Logistic regression models use a sigmoidal function. with this function it tries to find the probabilities of the target classes.

**RandomForestClassifier** is whats known as a tree ensemble method. the model resembles a tree by branching down an origin until it arrives at a givin conclusion. this would be an example of one tree. this model also uses what is known as bagging. bagging is where our model runs multiple trees at once in parralel. it then makes a decision based off the collective conclusions of all the trees

**XGBClassifier** is also a tree ensemble method. However, unlike the RandomForestCLassifier, XGBClassifiers run trees sequentually not in parallel. what this means is rather than taking the average of multiple trees, the XGBClassifier will creat a weak model and expose it to trees one at a time. the model trys to improve from each tree it is introduced to until it becomes a strong model for prediction.

  
## Feature importance

  Since we know that the XGBClassifier model performs the best, we can dive deeper and try to see what features it sees as the most important. by using the tool known ELFI5 we are able to list the features of our model by inportance in descending order. Wen can see that num_user_voted, title_year, and duration are the 3 most important features our model looks at. 

Insert graph

  Using PDP plots we can see how our model looks at the values of each feature. in the case of num_user_voted we can see that higher the value is for this feature, the more likely the movie is to be successful. this means the more people who were willing to to go online and vote for the movie, the more likely the movie is to be successful.
  
Insert graph

  When we look at the PDP plot of duration we see the opposite situation. The longer the duration of a movie, the higher the chance that the model will classify the movie as unsuccessful. this could signal that people prefer movies to run right around the 90 minutes mark.
