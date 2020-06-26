---
layout: post
title: Where are the Gamers
subtitle: What Region of the world has the highest concentration of video game players and what are they playing?
tags: [Video Games]
comments: true
---

![Gamers](https://images.unsplash.com/photo-1542751371-adc38448a05e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=500&q=60){:.mx-auto.d-block :}

  In this post we will be exploring the dataset 'Video Game Sales' from Kaggle.com. Using this data set I will try to find what region of the world has the highest concentration of video game players, as well as, what kind of video games are they playing? Our dataset gives us the number of video game sales for the top selling 16000 video games by region. The 3 major regions that are used when looking at the sale of Video games are North America, Europe, Japan, and Other. The region of Other in this data set pertains to the rest of the world. Since the sales in Other are much smaller than the other three we will not use it in our analysis. In order to get a an initial look into our data, I made a line graph plotting the top 100 selling video games by their sales in each region.

## North America, Eruope, and Japan sales of the top 100 Video games

{% include index.html %}

By looking at this graph we can start to get an idea of what kind of trends exist between the three regions. we can see that the line representing North America, on average, rises above both Europe and Japan in units sold. There is a similar trend between with europes sales rising above that of japan. However, since this is only the data from 100 games these trends may not be true for the entire data set. that being said we can form a hypothesis that North America has the highest number of sales.

to Gather more information I plotted a bar graph showing the number of sales by genre of Video game. i then grouped the data by region sales to help us further explore the trendof witch region has the highest sales.

## Genre by total number of Regional sales

The bar graph shows a similar trend in regional sales. we can see that North America does indeed have the highest number of sales, followed by Europe and Japan. we are also now able to see what kind of games each region enjoys playing the most. the the most part it would seem that gamers in North America and Europe prefer to play action, shooter, and sports games. Japan however,seems to avoid shooter games. they Japnas most played genre of game is Role-playing.  While this may mean that more people are buying video games in North america it doesn't mean they have the highest concentration. This is because the size and population of these regions differ dramatically. for instance the population of North ameraca (579 Million) is roughly 5 times greater than that of Japan(126.5 Million). in order to Show the true concentration of gamers I have standardized the data by population and replotted our line graph below.

## Total number of sales of North America, Eruope, and Japan.

By looking at this simple Funnel plot we can see that North America does indeed have the highest number of sales, followed by Europe and Japan. While this may mean that more people are buying video games in North america it doesn't mean they have the highest concentration. This is because the size and population of these regions differ dramatically. for instance the population of North ameraca (579 Million) is roughly 5 times greater than that of Japan(126.5 Million). in order to Show the true concentration of gamers I have standardized the data by population and replotted our line graph below.

## Standardized (North America, Eruope, and Japan sales of the top 100 Video games)

As you can see this has dramatically changed tthe trends we saw in our first line graph. Japan is now shown to have the highest sales per person on average. Europe also now has the lowest number of sales
