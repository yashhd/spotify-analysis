# Analysing spotify listening history and creating models

## Introduction

Being an avid music listener, I accumulated years and years of my spotify listening history, which is over 500 hours of streaming time. I am always on a lookout for discovering new genres of music and enjoy exploring new music. Now with this substantial amount of data, I felt I could do something with it, and I built vlassifiers which could generate song recommendations based on their music taste and let them know whether or not a song is a 'favorite'. The recommendations provided by Spotify are no doubt state of the art. With their discover weekly showcasing new undiscovered songs to the user on a weekly basis. But there’s a finite number of songs recommended through that feature. With this project, one can generate recommendations based on their own music taste and their past listening history on a large scale. 

## Data

I used two datasets to proceed further namely, streaminghistorymerged.csv and SpotifyAudioFeaturesApril2019.csv. Now, Spotify does not readily provide your listening data to you in the application. One has to go to their Spotify account website on the internet and put a request to Spotify to send you your user data. You then get an email saying that it might take up to 30 days for Spotify to send that data. But it usually takes around 2-3 days and you receive the data in your email. The data is a zip file with vast information about your spotify data. The zip file contains several JSON files like searchqueries.json, payments.json, yourlibrary.json and other files which contain useful information of your account as well as data of your interaction history with music on Spotify’s application. 

The 3 streaming history files were then converted to csv through a python script and then later merged into one file called ‘streamingHostorymerged.csv’. It has 22,706 rows and 4 columns namely artist, date(time when the stream ended), msPlayed(minutes in milliseconds) and trackName. The SpotifyAudioFeaturesApril2019.csv file contains 130,663 rows and 17 columns and they are related to the songs features like acousticness, liveliness, popularity, instrumentalness etc.



