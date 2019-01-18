# kafka-docker-compose
A kafka cluster for local development purposes


## To deploy

- `docker-compose up -d`

## To create a topic

- `docker-compose exec kafka1 bash`
- `kafka-topics --create --zookeeper zookeeper1:2181 --replication-factor 3 --partitions 10 --topic test`

## To query the cluster

- `docker-compose exec worker bash`
- `kafkacat -b kafka1:9092 -L`

## To send a message

- `docker-compose exec worker /bin/bash`
- `kafkacat -b kafka1:9092 -t test -P`
- start typing

## To see received messages

- `docker-compose exec worker /bin/bash`
- `kafkacat -b kafka1:9092 -t test -C`
- watch the messages come through
