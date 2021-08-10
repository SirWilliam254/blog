---
layout: post
title: Scrapping Twitter using R-Studio.
date: 2021-08-10 03:32:20 +0300
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
```    
# performing some sentimental analysis on a hashtag
```
   ts_twitter <- searchTwitter("#TokyoOlympics", n = 1000, lang = "en")
   ts_twitter_df <- twListToDF(ts_twitter) #converting to a dataframe
   write.csv(ts_twitter_df, file="euro.csv", row.names=FALSE)

   ts_twitter_df %>% select(screenName, created, text) %>% sample_n(5) %>% pander(.)
```
## table showing a sample of 5 tweets 
-----------------------------------------------------------------------
   screenName           created                      text              
---------------- --------------------- --------------------------------
   caashujha      2021-08-10 17:59:37        RT @IndiainArmenia:       
                                         Strengthening India-Georgia   
                                               ties in Sports:         
                                              Congratulations to       
                                              India-Georgia duo        
                                        @bajrangpunia and his Georgian 
                                                    coach…             

  FingalLabour    2021-08-10 17:30:49    RT @JoeCostelloIE: It was a   
                                          real honour to welcome our   
                                         Gold Medallist <U+0001F947>   
                                           #KellieHarrington &amp;     
                                        Olympian Emmet Brennan home to 
                                               Dublin from #To…        

   KAILASA_UN     2021-08-10 18:30:24   RT @MeditationWhy: Meditation  
                                         on Darkness || NSC || 7 Jan   
                                         2008 https://t.co/m0mtufnFew  
                                         via @YouTube   #Nithyananda   
                                          #inspiration #Motivation…    

 FlipTheScript8   2021-08-10 17:04:33   RT @OnHerTurf: There's always  
                                        that one friend <U+0001F485>   
                                              #OlympicHERstory |       
                                                #TokyoOlympics         
                                           https://t.co/hJwHuxzbRM     

 Satchidanand01   2021-08-10 18:52:02        RT @MinhazMerchant:       
                                         @shivjiramgupta @IndiaToday   
                                           Britain 0 gold medals in    
                                         #Athletics at #TokyoOlympics  
                                        <U+0001F947> Australia 0 gold  
                                             medals in athletic…       
-----------------------------------------------------------------------
