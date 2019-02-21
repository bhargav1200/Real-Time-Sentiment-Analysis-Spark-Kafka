# Real-Time-Sentiment-Analysis-Spark-Kafka
In this project we perform Sentiment Analysis on live Twitter feed in Real Time.

## Installation
1. This project runs on Ubuntu 16.04 LTS OS environment
2. This project requires Apache Kafka,Apache Zookeeper & Java to be installed as a prerequisite.

* Make sure Java is Installed.If not installed, follow the below link.

  [Java Installation Steps](https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-get-on-ubuntu-16-04)

* Download & Start Up Apacke Kafka & Apache Zookeeper by following the below link.

  [Kafka,Zookeeper Installation Steps](https://kafka.apache.org/documentation.html#gettingStarted)
  
3. Unzip the zipped .txt tweets file.

* $ unzip 16M.txt.zip

4. Start zookeeper service.

* $ bin/zookeeper-server-start.sh config/zookeeper.properties.

5. Start kafka service.

* $ bin/kafka-server-start.sh config/server.properties.

6. Create a topic named twitterstream in kafka.

* $ bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic twitterstream.

7. Check what topics you have.

* $ bin/kafka-topics.sh --list --zookeeper localhost:2181
