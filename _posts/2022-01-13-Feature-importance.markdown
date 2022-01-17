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
