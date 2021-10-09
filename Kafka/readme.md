# Introduction
  This compose file will install the kafka and zookeeper and start the zookeeper and kafka server

# start the kafka cluster(kafka broker and zookeeper) Foreground mode
docker-compose -f docker-compose.yml up

# start the kafka cluster(kafka broker and zookeeper)  Background mode
docker-compose -f docker-compose.yml up -d

# stop the services
docker-compose down

# connect the kafka cluster/ go inside the docker container
docker exec -it kafka /bin/sh

## installation is present in 
    /opt/kafka
## create Kafka topic
    - After connect to container cd into /opt/kafka
    - ./bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic topic1
### List the kafka topic
    - ./bin/kafka-topics.sh --list --zookeeper zookeeper:2181

### Create console Producer
    - ./bin/kafka-console-producer.sh --broker-list localhost:9092 --topic topic1

### Create console Consumer
    - ./bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic topic1




 # Multi node cluster
    - docker-compose -f two-node-kafka-clustor.yml  up -d   