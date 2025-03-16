# Kafka Spring Cloud Event-Driven Architecture

This repository demonstrates an event-driven architecture using Kafka and Spring Cloud.

## Getting Started

### Running Kafka on Windows

1. Start the Zookeeper server:
   ```sh
   bin\windows\zookeeper-server-start.bat config/zookeeper.properties
   ```
2. Start the Kafka broker:
   ```sh
   bin\windows\kafka-server-start.bat config/server.properties
   ```
3. Start the Kafka console consumer:
   ```sh
   bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic R4 \
       --property print.key=true --property print.value=true \
       --property key.deserializer=org.apache.kafka.common.serialization.StringDeserializer \
       --property value.deserializer=org.apache.kafka.common.serialization.StringDeserializer
   ```
4. Start the Kafka console producer:
   ```sh
   bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic R4
   ```

### Running Kafka with Docker

1. Start the Kafka services using Docker Compose:
   ```sh
   docker-compose up -d
   ```
2. Start a Kafka console consumer inside the broker container:
   ```sh
   docker exec --interactive --tty broker kafka-console-consumer --bootstrap-server broker:9092 --topic R2
   ```
3. Start a Kafka console producer inside the broker container:
   ```sh
   docker exec --interactive --tty broker kafka-console-producer --bootstrap-server broker:9092 --topic R2
   ```
4. Start a Kafka console consumer with deserialization properties:
   ```sh
   docker exec --interactive --tty broker kafka-console-consumer --bootstrap-server broker:9092 --topic R66 \
       --property print.key=true --property print.value=true \
       --property key.deserializer=org.apache.kafka.common.serialization.StringDeserializer \
       --property value.deserializer=org.apache.kafka.common.serialization.LongDeserializer
   ```
5. List all available Kafka topics:
   ```sh
   docker exec --interactive --tty broker kafka-topics --bootstrap-server broker:9092 --list
   ```

## Demo

![kafka](https://github.com/user-attachments/assets/3a34c420-b223-44c7-b765-848f10ba2a18)


