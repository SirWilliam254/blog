---
layout: post
title: Scrapping Twitter using R-Studio.
date: 2021-05-3 03:32:20 +0300
description: Getting the trending hashtags from Twitter using R via API. # Add post description (optional)
img: TWITTER.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [twitter, API, R, Machine Learning]
---
## Twitter API
allows the access of tweets in a programmatic and automated manner.
Using this idea we can perform analysis on certain keywords and the like to
draw some interesting insights. This notebook goes over how we can use twitter api via R-studio,
download tweets of interest autonomously and consequently act on it.

The first thing we ought to do is call on the relevant packages.
```r
######################## TWITTER SCRAPPING ###################################
# Required packages
> library(twitteR)
> library(tidytext)
> library(dplyr)
> library(ggplot2)
> library(janeaustenr)
> library(pander)
```
## Connecting to twitter
For one to connect to the twitter server ,one needs to request for access by applying for a developer account. Once granted you receive the necessary keys and tokens.
```r
# connecting to twitter
consumer_key <- "paste here"
consumer_secret <- "paste here"
access_token <- "paste here"
access_secret <- "paste here"

setup_twitter_oauth(consumer_key, consumer_secret, access_token, access_secret)
```    
