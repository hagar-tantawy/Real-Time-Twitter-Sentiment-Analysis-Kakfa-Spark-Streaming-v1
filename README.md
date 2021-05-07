# Real-Time-Twitter-Sentiment-Analysis-Kakfa-Spark-Streaming 

**Introduction**
The project aims at building a data platform for real time
moderation and analytics of twitter data. The implementation will
utilize different big data technologies as Spark, Kafka and Hive, in
addition to visualization tools for data discovery and delivering
insights.
Objective
1- Use python to stream data from twitter as a source to Kafka
with the right configuration
2- Use Kafka queuing system for twitter messages
3- Use python to create the destination topics with the right
configuration
4- Use Spark structured streaming to fetch and process data
from Kafka.
5- Analyse the tweets sentiment using a simple approach
6- reply with the right message based on the tweet’s sentiment.
7- Output data from spark streaming to HDFS in the form of
parquet files
8- Build a Hive data model (Staging tables + Analytical tables)
that use modelling best practices for big data
9- Use PowerBI to create a dashboard that fetch data from
Hadoop. The trainee is expected to act as an analyst who is
willing to deliver some actionable information to business
users.

**Technologies used:**
1- For streaming data from twitter use
Spark
2- For queuing and persisting messages
Kafka
3- For processing data from Kafka to Hive
Spark Streaming
4- For SQL on Hadoop
Hive
5- For visualization
PowerBI 
6- Scripting 
Python  
************************************************************************************************************************ 
** Setting up envronment** 
Set up virtual environment : 
>>python3.6 -m venv ./iti41
>>source iti41/bin/activate 
>>pip install --upgrade pip 
>>pip install kafka-python
>>pip install pyspark 
>>pip install tweepy  
>>pip install kafka
>>pip install --force-reinstall pyspark==2.4.6 

>> Now we can work on that environment with all the versions we need and supported by eachy other >> source iti41/bin/activate     

##Error 401 
  >> Solution >>  ntpdate -u time.google.com  

#Create a Kafka topic: 
>> cd /usr/hdp/current/kafka-broker   
>> bin/kafka-topics.sh --create     --zookeeper localhost:2181     --replication-factor 1     --partitions 1     --topic tweets 
>> bin/kafka-topics.sh --list --zookeeper localhost:2181   

>> Run Ingesting_Real_Time_Tweets_Using_Tweepy_Kafka_Python script: 
>> python Ingesting_Real_Time_Tweets_Using_Tweepy_Kafka_Python.py
  

>> Run Spark_Streaming_Processing script: 
>> spark-submit --packages org.apache.spark:spark-streaming-kafka-0-10_2.11:2.4.6,org.apache.spark:spark-sql-kafka-0-10_2.11:2.4.6 --master local[*] /root/Spark_Streaming_Processing.py 

>> Create a Hive table: 
>> create external table bigdata.tweets(user_id string,tweet_timestamp string,followers_count string,location string, text string, retweet_count string,tweet_id string,user_name string, polarity string, subjectivity string,sentiment string) stored as parquet location 'hdfs://sandbox-hdp.hortonworks.com:8020/casestudy';
 
>>Connect hive with ODBC Driver to be able to connect on power BI and make dashborads.




