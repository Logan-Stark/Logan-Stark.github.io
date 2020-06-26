---
layout: post
title: Where are the Gamers
subtitle: What Region of the world has the highest concentration of video game players and what are they playing?
tags: [Video Games]
comments: true
---

![Gamers](https://images.unsplash.com/photo-1542751371-adc38448a05e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=500&q=60){:.mx-auto.d-block :}

  In this post we will be exploring the dataset 'Video Game Sales' from Kaggle.com. Using this data set I will try to find what region of the world has the highest concentration of video game players, as well as, what kind of video games are they playing? Our dataset gives us the number of video game sales for the top-selling 16000 video games by region. The 3 major regions that are used when looking at the sale of Video games are North America, Europe, Japan, and Other. The region of Other in this data set pertains to the rest of the world. Since the sales in Other are much smaller than the other three we will not use it in our analysis. To get an initial look into our data, I made a line graph plotting the top 100 selling video games by their sales in each region.

## North America, Europe, and Japan sales of the top 100 Video games

{% include top-100-sales (1).html %}

By looking at this graph we can start to get an idea of what kind of trends exist between the three regions. We can see that the line representing North America, on average, rises above both Europe and Japan in units sold. There is a similar trend between Europe's sales rising above that of Japan. However, since this is only the data from 100 games these trends may not be true for the entire data set. That being said we can form a hypothesis that North America has the highest number of sales.

To Gather more information I plotted a bar graph showing the number of sales by genre of the video game. I then grouped the data by region sales to help us further explore the trend in which the region has the highest sales.

## Genre by the total number of Regional sales

{% include Regions-by-Genre (1).html %}

The bar graph shows a similar trend in regional sales. We can see that North America does indeed have the highest number of sales, followed by Europe and Japan. We are also now able to see what kind of games each region enjoys playing the most. For the most part, it would seem that gamers in North America and Europe prefer to play action, shooter, and sports games. Japan, however, seems to avoid shooter games. Japan's most played genre of game is Role-playing.  While this may mean that more people are buying video games in North America it doesn't mean they have the highest concentration. This is because the size and population of these regions differ dramatically. For instance, the population of North America (579 Million) is roughly 5 times greater than that of Japan (126.5 Million). To Show the true concentration of gamers I have standardized the data by population and replotted our line graph below.


## Standardized (North America, Europe, and Japan sales of the top 100 Video games)

{% include Std-top-100-sales (1).html %}

With our new standardized data, we see a different pattern emerge in our data. Japan is now shown to have the highest sales per person on average. Europe also now has the lowest number of sales. This is because instead of looking at sales in units, we are now looking at the sales per person based on population size. This means that Japan might hold the highest concentration of video game players. To confirm this we can use our newly standardized data and look at total sales by genre again. 

## Standardized (Genre by the total number of regional sales)

{% include Std-Regions-by-Genre (1).html %}

Japan is now, even more, the most concentrated source of gamers. We can also see some differences in the trends between genre and region. Role-playing games are now much more pronounced as Japan's first choice of a video game. Platform games also still seem to be liked by most regions. More importantly, Japan is now the most concentrated source of gamers. While North America and Europe may outsell Japan, they also have a much more diluted pool of gamers. 

I hope this information has been helpful to you. 



