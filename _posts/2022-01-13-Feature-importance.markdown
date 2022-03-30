---
layout: post
title: Feature Importance.
date: 2022-01-13 14:32:20 +0300
description: This post is all about feature importance. Whereby we look at the ways one can identify if a feature is worth having in the model or rather if it has a significant influence in the prediction. The methods are model-agnostic
img: features.jpg 
fig-caption: # Add figcaption (optional)
tags: [permutation importance, pdp, shap]
---

When making predictions we are often bombarded with the question, "Which features are most usefull in the model? or rather significant"
We are going to take into consideration three methods:

- permutation importance
- partial dependence plots
and
- SHAP() values

## permutation importance

As the name permutation suggests, this method shuffles the values in a certain column i.e feature
and a prediction is made while holding other features as they are. By shuffling the data in such a manner
we expect the prediction accuracy to drop as the values are different all together, this procedure is
repeated and an average is calculated from the same. The method is applied to all other features and 
their importance is rated. We have an output which shows the confidence i.e + or - some value of how the feature 
affects the prediction accuracy.

[EXAMPLE WITH CODE HERE!](https://sirwilliam254.github.io/Feature-Importance/feat.html)

## PDP (Partial Dependence Plots)

Partial dependence plots demonstrate how a property influences the prediction. Partial dependency charts, 
like permutation importance, are computed after a model has been fitted. The model is fitted to real-world 
data that has not been modified in any manner.

[EXAMPLE](https://sirwilliam254.github.io/Feature-Importance/pdp.html)

Looking at the coding example above we see the pdp plot for pick-up longitude having a U-shaped kind of
a plot which would suggest that being picked up near the center of the longitude values lowers predicted 
fares on average, because it means shorter trips on average.

![Image]({{site.baseurl}}/assets/img/pdp1.PNG)

We can also create a 2D plot for the features pickup_longitude and dropoff_longitude which yields

![Image2]({{site.baseurl}}/assets/img/pdp2.PNG)

We expect the contours to run along the diagonals. We see that prices increase 
as we move further up to the upper right side of the plot.

<br/>

It would also be interesting to see what kind of a pdp, scaled distance would produce.
Plotting the absolute distances we have the plot:

![Image3]({{site.baseurl}}/assets/img/pdp3.PNG)

We see that controlling for absolute distance traveled, the pick up longitude
has a very small impact on predictions looking at the yielded plot.
