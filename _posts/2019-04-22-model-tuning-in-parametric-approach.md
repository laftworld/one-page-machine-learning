---
layout: post
mathjax: true
title:  "Model tuning in parametric approach"
date:   2019-04-22 18:28:00 +0800
categories: one-page-machine-learning
---
Keywords: machlne-learning, basic, parametric approach

![figure1][fig1]

Machine learning is a bunch of engineering techniques for building a model 𝑀 which represents given data ‘well’ enough. Though ‘well’ is ambiguous to say, we will find out how this ‘well’ness is defined in terms of engineering in later chapters.

There are 3 major types of approaches in supervised learning, parametric approaches, non-parametric approaches, and semi-parametric approaches. Parametric approaches, in particular, require a parameter 𝜽 (it could be a fixed value, a list of values (i.e., a vector), or even a set of probability distributions) in a model 𝑀 to be tuned to certain “criteria”. The criteria vary with respect to different objectives of why we want the model. The objectives can be maximizing utilities or minimizing “errors” over the given “constraints”.

Note that when you find words in quotation marks (e.g., “errors”), it means that the term is used in general (i.e., common sense), but it actually contains detail which can be investigated more deeply. For example, there are hundreds of “distances” defined in different ways for different usages (https://en.wikipedia.org/wiki/Distance). In terms of engineering, it is required to very carefully pick a proper term to solve a problem.

Without loss of generality, the parameter stated above is represented as 𝜽 in the figure. We choose to use the machine learning model 𝑀 as a parametric model for particular reasons, and we can choose 𝑀 as a non-parametric or as semi-parametric for some other reasons, which we will see later.

Imagine that you are an owner of a vending machine 𝑀 who just bought it from a factory. You do not yet know which beverages will be more consumable after installing it in the school corridor. The size and functions of 𝑀 are already designed and well known (i.e., you put in the coins, press the button, then get the item) but the display of items is not yet decided because you don’t know the market enough. Then what you first need to do is to collect data from the customers so that you can decide which items to sell. Let me describe how it works. You just put any items at random (Cola in the first row, soda in the second row, and so on), and put the plug and see what will happen during a week. After the week, you check that some items were more consumed than the others. Then you adjust the display under your policy (i.e., the more consumed, the more displayed), fill in the new stock, and wait one more week. You repeat this process until your effort to adjust seems useless. Then you can say that you learned enough of the customers in the corridor. Then leave the machine as it is and move to install another machine to attain more money. This is exactly the same what the machine 𝑀(=vending machine) searches the parameter 𝜽(=how items displayed) over data (=items).

In the figure above, there are basically two separate areas. Known, and unknown. We have the parametric model 𝑀 in the area of known (i.e., you know everything about the machine but 𝜽). What you do at first is to randomly initialize the parameter 𝜽 so that the model is now in the area of unknown. As 𝑀 learns the data, 𝜽 is tuned(=learnt) toward the data. The model is in the state of underfitting on first several trials, which means 𝑀 needs to learn more. As the trial is going on, 𝑀 moves to the state of overfitting. Which means it learns too much so that it predicts almost perfectly for the given data. However, though the vending machine is well fit to the school students, how to deal with their parents, who do have a completely different taste with students, came to celebrate their graduation? Well, you can simply just say that ‘that is just an exception, we can ignore the case’. This may be right in the case of a vending machine, but what if the machine is not a vending machine and is used in the medical domain? just 1 over million mispredict may cause big trouble. Since being overfit in training data gives high error rates for test data, the high error rate for the test case is not a desirable option.

The more fundamental reason why overfitting is not welcomed is that predicting given data has nowhere to be used. The reason why we let the machine predict is to make it be able to treat well for the cases which it has not seen before.

𝑀 starts learning 𝜽 from underfit (i.e., random, completely wrong), move to overfit (i.e., precisely right to the given data, useless). We can find the optimum between them.

To find the point where to stop learning, 𝑀 exploits not only training data but validation data. As 𝜽 is tuned to the training data, validation data is used to check the performance never changing 𝜽. If 𝑀 is too tuned to the training data, the error rate is going to serge under validation data. There is when the machine 𝑀 stops learning. Then we finally get the machine with a so-so performance in training data and so-so performance in test data. Note that exact prediction in the test set is under God’s domain in the real world because the future is partially based on known area, but basically based on unknown area.



<!---`BibTeX` --->


<!---`Original paper` [Original paper][cite1] --->






[fig1]: /one-page-machine-learning/img/img_ml/known-unknown.png "Model tuning"
<!---[cite1]: https://arxiv.org/pdf/1503.02531.pdf --->
