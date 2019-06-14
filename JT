#What's sentiment analysis
#Evaluating/Determining if a product/movie review, tweet (a writing) is positive, negative or neutral

#How to collect the data?
#Via Twitter API
#Complicated? Yes, since you need to apply and be approved by Twitter to become a twitter app developer 
#by really stating the use case, which public entity will see the information from the Twitter data collected, etc
#I was reading that it takes 2 weeks to get approve, but I was lucky to be within hrs 
#NB: Twitter limits the maximum number of tweets returned per search to 100

#After getting approved, you can create your app, which will collect the public tweets of the # you want to collect,
#in my case the 4 candidates

#importing pertinent libraries

#importing tweety for Pycharm was a pain, since even though I was doing alt + enter, 
#it would still tell me that it couldn't find the module
#First, I updated PyCharm version
#Since Conda is integrated in PyCharm, I added tweepy and textblob packages into Conda's cloud first (under: Upload a package)
#command: conda install -c conda-forge tweepy/textblob
#then went into PyCharm
#under Preferences > System Interpreter, added from Conda environment the packages freshly downloaded and added them 
#into PyCharm with alt + Enter

import tweepy
#tweepy library to access the Twitter API

import csv
#csv library for the file format

import textblob
#library to process textual data to dive in NLP tasks

import pandas as pd
#pandas library for data structure and reading csv file (merging+joining dataset)

#importing credentials
consumer_key = 'QLxxxxx'
consumer_secret = 'MOxxxx'

access_token = '11xxxxx'
access_token_secret = 'axxxxx'

#authentification code
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)

api = tweepy.API(auth)

#JustinTrudeau Tweets

public_tweets = api.search('JustinTrudeau')

#Open/Create a file to copy/paste the results-data
csvFile = open('ua.csv', 'a')

#Use csv Writer (convert objects into csv strings)
csvWriter = csv.writer(csvFile)

#Search in Twitter API, this #hashtag in english, since x (date)
#Twitter API:
#count: how many tweets you want to analyze
for tweet in tweepy.Cursor(api.search,q="@JustinTrudeau",count=75,
                           lang="en",
                           since="2019-04-01").items():

    #print the results below
    print(tweet.created_at, tweet.text)
    csvWriter.writerow([tweet.created_at, tweet.text.encode('utf-8')])

    # ‘utf-8-sig’ = used to overcome issue "Non English" language


    #as noticed, you can click on the hyperlink and get to the twitter page
    #comments by people, where they hashtag the name of the political candidate

#Source, part 1: https://ipullrank.com/step-step-twitter-sentiment-analysis-visualizing-united-airlines-pr-crisis/

#Building Twitter sentiment analysis in python


#Source, part 1: https://ipullrank.com/step-step-twitter-sentiment-analysis-visualizing-united-airlines-pr-crisis/

#Next Steps >>>>>

Clean the data
Merge both csv files 
Test the model with Naive Bayes
Matplotlib to illustrate the sentiment analysis
