# Analysing spotify listening history and creating models

## Introduction

Being an avid music listener, I accumulated years and years of my spotify listening history, which is over 500 hours of streaming time. I am always on a lookout for discovering new genres of music and enjoy exploring new music. Now with this substantial amount of data, I felt I could do something with it, and I built vlassifiers which could generate song recommendations based on their music taste and let them know whether or not a song is a 'favorite'. The recommendations provided by Spotify are no doubt state of the art. With their discover weekly showcasing new undiscovered songs to the user on a weekly basis. But there’s a finite number of songs recommended through that feature. With this project, one can generate recommendations based on their own music taste and their past listening history on a large scale. 

## Goal

The goal of this project is to recommend a list of songs based on the listening history and spotify’s audio features and analyze interesting results of your music taste using various classifier models namely Logistic Regression, Random Forest and Decision tree, to discover which songs appeal the most. The metric used for evaluating the results is F1 score because it is best suited when we care more about the false positives and false negatives. All the more, for a heavily imbalanced problem, f1 score is a better metric to choose.

## Data

I used two datasets to proceed further namely, streaminghistorymerged.csv and SpotifyAudioFeaturesApril2019.csv. Now, Spotify does not readily provide your listening data to you in the application. One has to go to their Spotify account website on the internet and put a request to Spotify to send you your user data. You then get an email saying that it might take up to 30 days for Spotify to send that data. But it usually takes around 2-3 days and you receive the data in your email. The data is a zip file with vast information about your spotify data. The zip file contains several JSON files like searchqueries.json, payments.json, yourlibrary.json and other files which contain useful information of your account as well as data of your interaction history with music on Spotify’s application. 

The 3 streaming history files were then converted to csv through a python script and then later merged into one file called ‘streamingHostorymerged.csv’. It has 22,706 rows and 4 columns namely artist, date(time when the stream ended), msPlayed(minutes in milliseconds) and trackName. The SpotifyAudioFeaturesApril2019.csv file contains 130,663 rows and 17 columns and they are related to the songs features like acousticness, liveliness, popularity, instrumentalness etc.

## Why use the features of the song?

The features of a song are quite important here in predicting a user’s music taste. For example, a song which is good for dancing will have a maximum danceability value of 1 and will be a good song to shake a leg. If we want to find a song with a good energy, the energy feature of that song should be 1, indicating that the track is energetic, fast, noisy and loud. Let’s say you like acoustic music a lot more, then one would look for an acousticness value of 1. In the end, the features having a stronger correlation with the favorite songs are used to make the predictions.

## Response Variable

The response variable is a feature named ‘favorite’ which indicates whether the user likes the song based on values 1 and 0, 1 being a favorite. But, a criterion had to be determined to classify a song as a favorite. When a histogram was plotted grouping the artist and the track together, I could see that frequencies of the song suddenly dropped at after 12 counts, indicating that the songs having a count greater than 12 are the ones which I truly enjoy, and they were not just listened randomly or by chance. This process also eliminates certain songs that might complicate our model.

![alt text](https://github.com/yashhd/spotify-analysis/blob/28973d5f9f694f4b62995b18423e42f0254b923f/data/favorite_count.png)




