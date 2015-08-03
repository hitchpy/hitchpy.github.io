---
layout: post
title: "Time to document some thoughts"
date: 2015-07-28
comments: true
---

### Introduction

Recently I have spend some time working on two Kaggle competitions. One is a image classification problem [Diabetic Retinopathy](https://www.kaggle.com/c/diabetic-retinopathy-detection), the other one is context Ad click through rate(CTR) prediction [Avito Context Ad Clicks](https://www.kaggle.com/c/avito-context-ad-clicks). You can find my solutions [here](https://github.com/hitchpy/Kaggle-Diabetic-Retinopathy-Detection) and [here](https://github.com/hitchpy/Kaggle-Avito-Context-Ad) 

Both are very interesting topics, but I didn't have enough time to explore the problem more deeply and the models are definitely suboptimal. Still, I have learned a few things from them. 


### Image classification and convolution neural network(CNN)
Early this year, Stanford offered a class regarding CNN for visual recognition and they kindly shared all the wonderful notes and homeworks [online](http://cs231n.stanford.edu/index.html). I have followed the class and worked on the problems. And this Diabetic problem is the perfect opportunity to apply those knowledges and tried out Theano(in this case, the wonderful [Keras](http://keras.io/) wrapper package). Since I have zero prior image processing experience, I mostly just want to get a feel of CNN. I read through a few of the top competitors' solution and code, those are some serious engineering efforts! Just some low hanging fruits that might help improving my current model:

- further image preprocessing will be very helpful. including color adjustments, and normalization with population mean and standard deviation. And it seems like class balancing is not that important, some other kind of augmentation schemes will be useful(flipping etc.)

- Customizing the loss function will help. Initially I use cross-entropy for multi-class classification loss. But the model just wasn't learning anything(I was using the original pictures with huge black frames!). As pointed out by others, the classes are ordered, so a metric that can reflect this would be more appropriate. And a soft version of Kappa is also possibly better. I used MSE coupled with ranked score and cutoff, which seems to be a reasonable method too.

- This is indeed a huge project and I really admire those people that dedicated few months time to tackle this problem. I tried one VGG structure in the last two weeks and that was all I ever tried! Experimenting with nonlinearity and stride size, model depth certainly will yield meaning results. But I didn't do anything! Not even did any model validation! 

### Online learning and CTR estimation 

For many fellow Kaggler, this type of problem is nothing new. There were a few similar competitions before this already, and the methods used for this kind of problem is very standard too(Logistic regression, FFM etc). But there are always new twist to the problem. For this competition:

- The data is fairly large, so training and model iteration will be more difficult.

- There are different kind of Ads, and "Ad" is like the content of the webpage, not like what is usually showed on a sidebar. The data is very rich and you can generate a lot of useful features from it. With visits history, you can do personalization if you are really serious. But I guess it must be very time consuming and will not fit into the online learning framework, so even the top rankers are not doing it. Although with the search query and titles and parameters of the product, some people did NLP analysis and yield some useful feature.

- Although FTRL is mostly logistic regression under the hook, they never teach you to use features sets of millions(with no regularization) in statistic class. Using AdID and IPID as features seems too raw, but it did yield better result.

- A "so obvious" after they told you feature is to combine all the results from the same research(their position, type, etc) as a tuple, and treated it as categorical features. It makes intuitive sense, since whether a user will click on a particular ad will certainly depends on the whole search result, not just one single ad.

- One last question I have is really how "good" first place's model is, what does 0.0402 logloss means in this instant, and how big a difference it actually is between 0.045 and 0.040. For a sample of 7,800,000 test points, 0.005 means a total of 39,000 total difference, and that is no a small number. 

### Conclusion 
There are two ways you can approach Kaggle competitions. You can, like me, try something new, a type of problem you haven't work on, and you test some basic ideas. Or you can focus on one or two problems, and dedicate your energy to cracking that problem. I have tried the first style quite a bit, I might need to try the second one now. Just keep at it!