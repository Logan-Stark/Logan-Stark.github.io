---
layout: post
title: Predicting Success
subtitle: Can we use machine learning to predict how successful a movie will be?
tags: [Movies]
comments: true
---

![Movies](https://cdn.pixabay.com/photo/2017/11/24/10/43/admission-2974645_960_720.jpg){:.mx-auto.d-block :}

## Introduction

  One of the things I have missed the most during quarantine is going out to the movies. Since all the theatres are closed its made me think, "what makes a movie successful?" There are hundreds of thousands of different movies that have been produced over the years. some of these movies break box office records while others will go unheard of. The goal of this post is to make a predictive model for movie success and explain important features.
 
## Data exploration and target selection
  
  We will be using data gathered from the Movies.Meta dataset on kaggle.com. This data contains many different features such as revenue, Facebook likes, actors, and duration. For my model, I decided to create a new feature called [success] to serve as our target. [success] will help us gauge how successful a given movie is by taking the gross revenue made and dividing it by the budget. By doing this we receive a number that shows us how much money was made with respect to the money already spent on the budget. For instance, if a movie's success is less than 1 we know the movie spent more than it made. We can then make our target binary by assigning any movie that has a success of less than 1 to unsuccessful and any greater than 1 successful.
  
## Data leakage

![Leak](https://cdn.pixabay.com/photo/2017/06/18/03/43/tap-2414460_960_720.jpg){:.mx-auto.d-block :}

  Because we engineered our binary target [success] from existing features we are now exposed to data leakage. Data leakage is when the answers we are trying to predict are accidentally leaked to our models. This causes our model to cheat and get a much higher accuracy then it should. This will lead to a bad predictive model. In our case, if we leave the features [gross, budget] in our training data our model will overfit. To fix this problem I drop both of these features from our dataset.  
  
## Baseline model
  
  Using our new target we can make a baseline model for our future models to compete against. We can make our baseline model by computing the value counts of our target and graphing it. In our graph 1 represents successful while 0 represents unsuccessful. Our graph shows an almost 50/50 split in movie success. Since the majority class is 1 our baseline to beat in our models will be 52% 
  
![image](/assets/img/Baseline2.png){:class="img-responsive"}

## Machine learning

  After removing features with high cardinality and missing values I split my data into a training, validation, and testing set. I used these sets to fit 4 different models
and test their accuracy. The classifiers I used to train these models were LogisticRegressionClassifier, RandomForestClassifier, and XGBClassifier. Each of these classifiers is unique in their own way.

**Logistic Regression** is a Linear Classification model. Logistic regression models use a sigmoidal function. With this function, it tries to find the probabilities of the target classes.

**RandomForestClassifier** is whats known as a tree ensemble method. The model resembles a tree by branching down an origin until it arrives at a given conclusion. This would be an example of one tree. This model also uses what is known as bagging. Bagging is where our model runs multiple trees at once in parallel. It then makes a decision based on the collective conclusions of all the trees.

**XGBClassifier** is also a tree ensemble method. However, unlike the RandomForestCLassifier, XGBClassifiers run trees sequentially not in parallel. What this means is rather than taking the average of multiple trees, the XGBClassifier will create a weak model and expose it to trees one at a time. The model tries to improve from each tree it is introduced to until it becomes a strong model for prediction.

  
## Feature importance

  Since we know that the XGBClassifier model performs the best, we can dive deeper and try to see what features it sees as the most important. By using the tool known ELFI5 we can list the features of our model by importance in descending order. We can see that num_user_voted, title_year, and duration are the 3 most important features our model looks at. 

![image](/assets/img/Screenshot (37).png){:class="img-responsive"}

  Using PDP plots we can see how our model looks at the values of each feature. In the case of num_user_voted, we can see that the higher the value is for this feature, the more likely the movie is to be successful. This means the more people who were willing to go online and vote for the movie, the more likely the movie is to be successful.
  
![image](/assets/img/PDP_num_user_vote.png){:class="img-responsive"}

  When we look at the PDP plot of duration we see the opposite situation. The longer the duration of a movie, the higher the chance that the model will classify the movie as unsuccessful. This could signal that people prefer movies to run right around the 90 minutes mark.

![image](/assets/img/PDP_duration.png){:class="img-responsive"}

  Another way we can see how our features impact our model is with a Shaply plot. With a Shaply plot, we can measure the pressure each feature exhibits on a single row. Below you can see the red bar consists of features pushing our model to classify the movie as successful. Meanwhile, the blue bar shows features pushing our model to classify the movie as unsuccessful.
  
![image](/assets/img/working_Shap.png){:class="img-responsive"}
 
## Conclusion

  Looking back at our results, we found that our XGBClassifier model was our most accurate model. We were able to build a model capable of predicting movie success with a 74.2 test accuracy. Diving deeper, we also saw what areas contribute the most to a movie being successful. We can see how having many people willing to review a movie online can boost success. While runtime can negatively affect your movie if you let it go on too long.
