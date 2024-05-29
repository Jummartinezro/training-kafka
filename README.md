# training-kafka

Playing with Kafka topics

Using and inspired by [lensesio/fast-data-dev](https://github.com/lensesio/fast-data-dev?tab=readme-ov-file) docker container to launch a Kafka instance

## How to use it.

Inspired by [@amberkakkar01's guide](https://medium.com/@amberkakkar01/getting-started-with-apache-kafka-on-docker-a-step-by-step-guide-48e71e241cf2)

(And some [StackOverflow](https://medium.com/@amberkakkar01/getting-started-with-apache-kafka-on-docker-a-step-by-step-guide-48e71e241cf2))

### Launch Kafka docker image
```bash
docker-compose up --build
```

### Lenses.io UI
```bash
localhost:3030
```

### Create a topic
```bash
docker exec -it <CONTAINER_ID> /opt/landoop/kafka/bin/kafka-topics --create --replication-factor 1 --partitions 1 --topic <TOPIC> --bootstrap-server localhost:9092
```

### Produce messages

```bash
docker exec -it <CONTAINER_ID> /opt/landoop/kafka/bin/kafka-console-producer --broker-list localhost:9092 --topic <TOPIC>
```

### Consume messages

```bash
docker exec -it <CONTAINER_ID> /opt/landoop/kafka/bin/kafka-console-consumer --bootstrap-server localhost:9092 --topic <TOPIC> --from-beginning
```