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

Would linear regression work?

No, linear regression won't work in qualitative responses because for：

1. *Multiclass Classification*, class assigned with numerical value would imply ordering of responses. In the case of colors of rainbow, it makes no sense that red is greater than violet.

2. *Binary Classification*, linear regression would fail because we need to output probability of class A or class B, the output must be bounded between 0 and 1, linear regression may produce a value outside of this bound, which is difficult to understand as probability.

---

#### How does it work?

We start by building a classifier with some training observations 
(x1, y1), ... , （xn, yn), x are the features, and y is the response variable. After we obtain our model, we then test this classifier on unseen test data. 



