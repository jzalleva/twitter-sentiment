# Twitter-Sentiment
This project allows the user to search for a topic on Twitter and track the change in sentiment over the course of a week. My goal was to build a program which extracts data from Twitter and runs a simple analysis. There is plenty of room for improvement but I'm happy with the results of my first project. The results are interesting and it's possible to gather some insights from popular Tweets on a topic.

The user can find Tweets containing a specified word or set of words. Once search terms are specified, an equal number of Tweets from each day of the last week are gathered from the Twitter api using Tweepy. From there, the text is cleaned and run through a machine learning sentiment analysis module. I use TextBlob to perform sentiment analysis, the results are far from perfect, but it captures the general sentiment. Each Tweet is given a score of -1.0 to 1.0 (very negative to very positive, 0 being neutral).   

Once each Tweet has a sentiment score associated with it, it is then added to a SQL database. This is not necessary, but I found it to be good practice integrating Python and SQL. After the data is in SQL, sentiment data is agreggated and averaged, based on the number of Tweets, retweets, and their corresponding sentiment scores.

The end result is a printout containing the most influential positive and negative tweets for each day over the last week. See below for an example using, "Tour de France" as a search term (I've rekindled my love of biking since the start of the pandemic). I plan on adding a graph shortly, the code for the graph's data is already developed and included in the notebook.

Each Day's Most Influential Positive Tweets: 
----------------------
1 . Tue Sep 08 - RTÉ Sport - Breaking: Sam Bennett has become only the sixth Irishman to win a stage of the Tour de France following a sprint finish to a blisteringly fast 10th day of racing.

https://t.co/DXVsrnlgNL
Sentiment: 0.25 - Retweets: 248


2 . Wed Sep 09 - Graham Watson - Visit the fantasy world of @EuroHoody at the Tour - it does make for some great reading. https://t.co/QCB0oLiXl7
Sentiment: 0.8 - Retweets: 1


3 . Thu Sep 10 - Cycling Weekly - 'I thought it was bike trouble, but it was just the legs': Julian Alaphilippe proves mortal once more on Tour de France stage 12 #TDF2020 | https://t.co/bj9oPlpNzp
Sentiment: 0.2 - Retweets: 13


4 . Fri Sep 11 - Kristen's watching le Tour de France 🚵🏻‍♂️ - @maladrift lol in the early days of the tour de france, cyclists would smoke during the races!! i cannot imagine!
Sentiment: 0.45 - Retweets: 0


5 . Sat Sep 12 - Thomas De Gendt - For sale. Pair of legs. Slightly used. Good enough to win any kind of race except Tour de France stages. Dm if interested.
Sentiment: 0.36 - Retweets: 1982


6 . Sun Sep 13 - Eurosport UK - "Higuita is down - and we don't know why!"

🇫🇷 #TDF2020 LIVE
📺 Eurosport 1
📱 💻 Uninterrupted coverage: https://t.co/YhayffKVQN
📃 Live blog updates: https://t.co/VLND45cTOe https://t.co/JYA46sLzOL
Sentiment: 0.03 - Retweets: 57


7 . Mon Sep 14 - VeloNews - Pogačar, the most aggressive rider of this year's Tour, is planning to attack race leader and countryman Primož Roglič all the way to Paris.

#TDF2020 @LeTour 

https://t.co/SKQ9QepuSy
Sentiment: 0.5 - Retweets: 5


----------------------
Each Day's Most Influential Negative Tweets: 
 ----------------------
1 . Tue Sep 08 - La Flamme Rouge - HLN reports at least one member of DQT is being re-tested. #TdF2020

https://t.co/ZBYazHn3PP
Sentiment: -0.3 - Retweets: 15


2 . Wed Sep 09 - Bruce Davies - @SBS so no Tour de France highlights in the morning anymore? Just breathtakingly boring tennis on both channels 😫👎
Sentiment: -1.0 - Retweets: 0


3 . Thu Sep 10 - Ned Boulting - On the Tour de France route today, we will see once again from the air the ruined village of Oradour-sur-Glane, the site of the massacre of 642 villagers on 10 June 1944. It is a startling sight, and was recently defaced by vandals, who replaced the word "martyrs" with "liars". https://t.co/MaIkEbMm6O
Sentiment: -0.25 - Retweets: 247


4 . Fri Sep 11 - Eileen Dewey - @marklevinshow You know what else is an ninteresting coincidence?

All three countries have teams in the Tour de France. I think they're basically the ONLY teams that are "country" teams, unless you count Astana. Weird.
Sentiment: -0.25 - Retweets: 0


5 . Sat Sep 12 - Cyclingnews.com - Bardet suffers 'small haemorrhage' after Tour de France crash

https://t.co/2FR387MxZ1 #TDF2020 https://t.co/yTvJZUzWF8
Sentiment: -0.42 - Retweets: 7


6 . Sun Sep 13 - Reuters - Bernal at a loss after brutal Tour de France failure https://t.co/LSuGzENoQq https://t.co/rWUk5TNJV9
Sentiment: -0.6 - Retweets: 6


7 . Mon Sep 14 - Okedi Peter John - Late Ewan surge seals Tour de France stage three victory https://t.co/5aCU01gxUt
Sentiment: -0.3 - Retweets: 0
