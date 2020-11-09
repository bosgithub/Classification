### Classification

#### What is classification?

Classification is a process to predict qualitative responses. This involves assigning the observation to a specific category or class, it is done by comparing the probability of each of the categories of the specific observation and assigning the one with the highest probability.

Some examples would be the color of our eyes{green,brown, blue} or fraudulent emails{spam, ham}

---

#### Common classification techniques(classifiers):

1. Logistic Regression

2. Linear Discriminant Analysis

3. K-nearest Neighbors

there are some more computer-intensive(non-linear) models such as GAM, trees, random forests, and boosting, and support vector machines

---

Would linear regression work?

No, linear regression won't work in qualitative responses because for：

1. *Multiclass Classification*, class assigned with numerical value would imply ordering of responses. In the case of colors of rainbow, it makes no sense that red is greater than violet.

2. *Binary Classification*, linear regression would fail because we need to output probability of class A or class B, the output must be bounded between 0 and 1, linear regression may produce a value outside of this bound, which is difficult to understand as probability.

---

#### How does it work?

We start by building a classifier with some training observations 
(x1, y1), ... , （xn, yn), x are the features, and y is the response variable. After we obtain our model, we then test this classifier on unseen test data. 

---

#### Logistic Regression
Logistic regression models the probability that the response variable belongs to a particular category. (example: Probability of race given the demographic region)

___Logistic Model___:

<a href="https://www.codecogs.com/eqnedit.php?latex=p(X)&space;=&space;\frac{e^{\beta_{0}&space;&plus;&space;\beta_{1}*X&space;}}&space;{1&plus;&space;e^{\beta_{0}&space;&plus;&space;\beta_{1}*X}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?p(X)&space;=&space;\frac{e^{\beta_{0}&space;&plus;&space;\beta_{1}*X&space;}}&space;{1&plus;&space;e^{\beta_{0}&space;&plus;&space;\beta_{1}*X}}" title="p(X) = \frac{e^{\beta_{0} + \beta_{1}*X }} {1+ e^{\beta_{0} + \beta_{1}*X}}" /></a>

sometimes we prefer to work with odds and log of odds or logits,

Odds:

<a href="https://www.codecogs.com/eqnedit.php?latex=\frac{p(X)}{1&space;-&space;p(X)}&space;=&space;{e^{\beta_{0}&space;&plus;&space;\beta_{1}*X&space;}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\frac{p(X)}{1&space;-&space;p(X)}&space;=&space;{e^{\beta_{0}&space;&plus;&space;\beta_{1}*X&space;}}" title="\frac{p(X)}{1 - p(X)} = {e^{\beta_{0} + \beta_{1}*X }}" /></a>

Logit:

<a href="https://www.codecogs.com/eqnedit.php?latex=log\left&space;(&space;\frac{p(X)}{1&space;-&space;p(X)}\right&space;)&space;=&space;{e^{\beta_{0}&space;&plus;&space;\beta_{1}*X&space;}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?log\left&space;(&space;\frac{p(X)}{1&space;-&space;p(X)}\right&space;)&space;=&space;{e^{\beta_{0}&space;&plus;&space;\beta_{1}*X&space;}}" title="log\left ( \frac{p(X)}{1 - p(X)}\right ) = {e^{\beta_{0} + \beta_{1}*X }}" /></a>

#### The idea of training the logistic model is to fit our model on the training data to best estimate the beta values. This is done via *Maximum Likelihood Method*.
