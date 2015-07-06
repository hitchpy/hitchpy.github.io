---
layout: post
title: "Some thoughts on my Kaggle experiences"
date: 2015-07-05
comments: true
---

It really has been a while since my last blog post! Anyway, since I participated in the [BCI Kaggle competition](https://www.kaggle.com/c/inria-bci-challenge) with several my classmates, I entered a few more([Rain](https://www.kaggle.com/c/how-much-did-it-rain), [Robot Detaction](https://www.kaggle.com/c/facebook-recruiting-iv-human-or-bot), [Virus Prediction](https://www.kaggle.com/c/predict-west-nile-virus) and [CrowdFlower Search results relevance](https://www.kaggle.com/c/crowdflower-search-relevance)). Trust me, it is not easy at the beginning. Not knowing what to do, and the vast amount of time needed for each competition probably will put a lot of people off. Here, I will share my own experiences so far from participating in all these competitions. It will be about the general thought process, how to iterate over different ideas and what I have learned from them. I am by no means a top competitor, but I want to share it anyway. And maybe some years from now, it will be funny to look back!

First of all, people would say that these are competitions, how realistic or similar to real world modeling? It it true that there certainly will be some differences, but many industry products start out with prototypes and this might be similar to that. And second, some competition organizers genuinely have end product in mind and intent to make the competition more "realistic". Of course this itself is a huge topic and I would go into detail here, but I strongly suggest [this podcast episode](http://www.thetalkingmachines.com/blog/2015/6/18/working-with-data-and-machine-learning-in-advertizing) and [The speaker's website](https://sites.google.com/site/claudiaperlich/home). 

So you are looking at the description of one competition, it seems quite interesting, a classification or regression problem. You decided to download the data and have a look, and see what other people are discussing in the forum. You might have some ideas about possible ways to tackle this problem, or there are shared starter code to get you started. The value of experiences is when you see a problem, you can probably "know" what methods might work, what kinds of features might be important for prediction. This is the most excruciating or most exhilarating part. The frustration of after exploring the data 1000 ways, trying all the methods you ever know, and things still doesn't work. Or the joy of finding the important features and see a huge bump in your score. They are all valuable lessons. The wonderful people in Kaggle usually will share their solutions after the competition is over. And you will know why you didn't do well and improve next time in a similar situation. It is all good!

In terms of iteration of ideas, that's where good engineering practices and master of tools come in. Knowing your tools(R packages or scikit-learn functions) well means when you have an idea, you can quickly put it to test. And good structuring or your data processing code, cross validation etc means you can swipe in and out of modules/methods quickly. And everything will be smooth..But again, this will require a lot of practice and a good habit. Usually there are a bunch of engineers in each competition, and you can learn a lot from them.

Finally what I have learned from the competitions I participated? Getting Generalized linear model(GLM) to actions, working on text data, and doing various exploratory to get better features! And as classified by someone else, there are structured dominated problems and noise dominated problems(BCI with EEG data definitely is in this category). Knowing what to do(finding tiny signals or finding complicated structure) in each cases(avoid overfitting noise or use more complicated algorithm to capture the underlying functions) will be vital. 

At the moment I am still not very familiar with the strength and weakness of some common algorithms, don't know how to handle many types of data, don't know efficient way to tackle the problem if data gets too big, don't have good engineering practices. 

So, back to the modeling!





