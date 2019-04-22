---
layout: post
title:  "Model tuning in parametric approach"
date:   2019-04-22 18:34:00 +0800
categories: one-page-machine-learning
---
Keywords: machlne-learning, basic, estimation, prediction

![figure1][fig1]

One of the machine learning basic is the concept of a model in a general view. Model is like a hypothesis, which represents some GUESS on something real.

For example, when we toss a coin several times in a row, let’s say it’s 10000 times. Then the number of heads might be some value around 5000 when the coin is ideal. As the number of flips (=N) increases, the approximation gets closer to ½. Note that each x represents a random variable which contains 1 (head) or 0 (tail), i.e., x∈{0, 1}.

As N increases, the variance of the parameter p_0 gets small. For instance, if N=100000000, just one or two more or fewer trials will not affect that much on the result. As the very same analogy, we say that the model M learns data more and more and gets stable. Then stop learning at some point when p seems stable enough. When we find the optimal parameter p for the model, then we call the parameter in a new term, p hat. The process of finding the optimal p hat from data is parameter estimation.

Now the model M with the estimated parameter p hat can be used to decide whether the unknown trial will be ‘head’ or ‘tail’. This is called prediction of outcome (i.e., we can easily guess the coin will be head in ½ probability without tossing it 10000 times. It’s because we already get the estimated parameter ½ in our memory.)

The left part of the figure depicts the parameter estimation, while the right part is the prediction of outcome. Most of the (parametric) machine learning models are built (=estimated) and used(in prediction) in this scheme.

Though the figure illustrates a naive parameter p which is easy to know. More advanced and complex parametric models are still based on this concept of estimation and prediction.



<!---`BibTeX` --->


<!---`Original paper` [Original paper][cite1] --->






[fig1]: /one-page-machine-learning/img/img_ml/estimation_and_prediction.png "Estimation and prediction"
<!---[cite1]: https://arxiv.org/pdf/1503.02531.pdf --->
