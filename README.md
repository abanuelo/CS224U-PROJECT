# CS224U-Project - Hashtag Predictor
Using Latent Dirichlet Allocation (LDA) to identify topics of new hashtags and suggest relevant hashtags from tweets.

## Data
For the data, we used Twitter Snapshot data from 2010-2011, provided by Professor Christopher Potts via the defunct TwapperKeeper service. The data has 44 million tweets grouped into 36 main topics.

## Preprocessing Data
To clean the data, we applied edit distance techniques to reduce mispellings and mapped mispellings to correctly spelled word. Along with that, we removed username mentions in tweets (ie @username), URL references, and RT references (retweets).

## Topic Modeling Using LDA
We constructed SST graphs to build a graphical relationship of tweet topics. Then we applied LDA for topic modeling of tweets. Using coherence score as an evaluative metric, we determined the optimal K topics to search was K = 22. Hashtags were extracted from tweets and topic modeling using LDA was applied. More specifically, once LDA determined the best model to apply, we used that model to measure the weights of words within a tweet to determine its topic and subsequent hashtags suggestion based on its topic.

<p align="center">
  <img src="https://user-images.githubusercontent.com/32311654/49634109-9853f700-f9b0-11e8-8d92-fc1d63750f5f.png">
</p>

## Results
Our method of evaluation is calculating the recall of the hashtags given the hashtags of a held out test set, which reaches a score of 0.13. This method is chosen over other metrics such as, precision and F1, because it is impossible calculate false positives, i.e. when a recommended hashtag is irrelevant to a tweet, given the current data set. 


