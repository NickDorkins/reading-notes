# Class 13: Linear Regressions

## [How to Run Linear Regression in Python](http://bigdata-madesimple.com/how-to-run-linear-regression-in-python-scikit-learn/)


[`Scikit-learn`](http://scikit-learn.org/stable/) is a powerful Python module for machine learning. It contains function for regression, classification, clustering, model selection and dimensionality reduction. The `sklearn.linear_model` [`module`](http://scikitlearn.org/stable/modules/linear_model.html) contains “methods intended for regression in which the target value is expected to be a linear combination of the input variables”.

> All examples are using the [Boston Housing data set](https://archive.ics.uci.edu/ml/datasets/Housing), the data set contains information about the housing values in suburbs of Boston.

> This information is also available at the [UCI Machine Learning Repository.](http://archive.ics.uci.edu/ml/)

## Exploring Boston Housing Data Set

The first step is to import the required Python libraries into Jupyter Notebook.

```
%matplotlib inline

import numpy as np
import pandas as pd
import scipy.stats as stats
import matplotlib.pyplot as plt
import sklearn
```

> This data set is available in [sklearn](http://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_boston.html#sklearn.datasets.load_boston) Python module, so you access it using `scikitlearn`.


Important functions to keep in mind while fitting a linear regression model are:

- `lm.fit()` -> fits a linear model

- `lm.predict()` -> Predict Y using the linear model with estimated coefficients

- `lm.score()` -> Returns the coefficient of determination (R^2). A measure of how well observed outcomes are replicated by the model, as the proportion of total variation of outcomes explained by the model.

`.coef_` gives the coefficients and `.intercept_` gives the estimated intercepts.

## Training and validation data sets

In practice you wont implement linear regression on the entire data set, you will have to split the data sets into [training and test](http://www.researchgate.net/post/Whats_the_difference_between_training_set_and_test_set) data sets. So that you train your model on training data and see how well it performed on test data.

## How to do train-test split:

You have to divide your data sets randomly. Scikit learn provides a function called train_test_split to do this.

## Residual Plots

Residual plots are a good way to visualize the errors in your data. If you have done a good job then your data should be randomly scattered around line zero. If you see structure in your data, that means your model is not capturing some thing. Maye be there is a interaction between 2 variables that you are not considering, or may be you are measuring time dependent data. If you get some structure in your data, you should go back to your model and check whether you are doing a good job with your parameters.

<br>

![Residual Plots Example](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Residual-plot.png)

Recap what was done in this article:

- Explored the boston data set and then renamed its column names.
- Explored the boston data set using .DESCR, the goal was to predict the housing prices using the given features.
- Used `Scikit` learn to fit linear regression to the entire data set and calculated the mean squared error.
- Made a train-test split and calculated the mean squared error for the training data and test data.
- Plotted the residuals for the training and test datasets.


### Additional Resources

- [Linear Regression in Python](https://realpython.com/linear-regression-in-python/)

- [Introduction to Simple Linear Regressions](https://www.youtube.com/watch?v=KsVBBJRb9TE)

- [Train & Test Splits](https://towardsdatascience.com/train-test-split-and-cross-validation-in-python-80b61beca4b6)

- [What is Linear Regression?](https://www.statisticssolutions.com/what-is-linear-regression/)