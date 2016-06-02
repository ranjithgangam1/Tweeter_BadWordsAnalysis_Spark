# Tweeter_BadWordsAnalysis_Spark
It detects the Bad words from twitter Data. Then it calculates proportion of bad words for each hour 

Twitter data questions: (schema)  (hdfs://data/twitter)

###Problem Statement:

#### Detect the proportion of bad words in a tweet.  Plot bad word proportion by hour for all 24 hours.

Aim:

Generate an output file by using spark that has proportion of bad words in all tweets in 24 hours. Using this data plot proportion of bad words per hour.

Approach:

•	Created a list of bad words. This bad words are collected from internet. Bad words proportion accuracy can be improved by collecting more bandwords.

•	Created a RDD that has tweets by reading files from HDFS.  

•	User defined function is passed in to this RDD. In this function intersection between tweet text and bad words is done. Length of intersection is used to count the bad words in a tweet.

•	All bad words per hour are counted by creating reduceByKey transformation per hour.

•	Badwords proportion is calculated by dividing badwords by total number of words per hour.

•	Finally RDD containing badwords proportion is written into output file

See the plot based on output data in this folder

