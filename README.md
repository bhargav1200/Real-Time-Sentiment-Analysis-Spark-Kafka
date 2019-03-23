# Real-Time-Sentiment-Analysis-Spark-Kafka
In this project we perform Sentiment Analysis on live Twitter feed in Real Time.

## Installation
1. This project runs on Ubuntu 16.04 LTS OS environment
2. This project requires Apache Kafka,Apache Zookeeper & Java to be installed as a prerequisite.

* Make sure Java is Installed.If not installed, follow the below link.

  [Java Installation Steps](https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-get-on-ubuntu-16-04)

* Download & Start Up Apacke Kafka & Apache Zookeeper by following the below link.

  [Kafka,Zookeeper Installation Steps](https://kafka.apache.org/documentation.html#gettingStarted)
  
* Install PySpark by following the below link.

  [PySpark](https://askubuntu.com/questions/635265/how-do-i-get-pyspark-on-ubuntu)
  
* Install an editor. Here we used atom.It can be installed by following the belo link.
  
  [Atom instalation](http://tipsonubuntu.com/2016/08/05/install-atom-text-editor-ubuntu-16-04/)
  
3. Unzip the zipped .txt tweets file.

* $ unzip 16M.txt.zip

4. Start zookeeper service by navigating to the directory where kafka-tar file is downloaded and then run the below command.

* $ bin/zookeeper-server-start.sh config/zookeeper.properties.

5. Start kafka service by navigating to the directory where kafka-tar file is downloaded and then run the below command.

* $ bin/kafka-server-start.sh config/server.properties.

6. Create a topic named twitterstream in kafka.

* $ bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic twitterstream.

7. Check what topics you have.

* $ bin/kafka-topics.sh --list --zookeeper localhost:2181

8. Now install a python client to access Apache Kafka.

* $ pip install kafka-python 

8. Now stream the tweets and push them to kafka queue using the twitter_to_kafka.py.

* $ python twitter_to_kafka.py

9. Now check if the data is landing in Kafka.

* $ bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic twitterstream --from-beginning


10. Plot of count of positive & negative words at each time step.

![Tweet Count](https://github.com/kalyanghosh/Real-Time-Sentiment-Analysis-Spark-Kafka/blob/master/plot.JPG)



