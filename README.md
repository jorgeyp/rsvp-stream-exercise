# rsvp-stream-exercise

## Requirements:
- Kafka 2.11-2.1.0
- MongoDB 4
- Node.js 10.15.0

## Quickstart
Running the exercise requires a Kafka topic, a MongoDB database and a collection with the following default names:
- Kafka topic: "meetup"
- MongoDB database: "meetup"
- MongoDB collection: "rsvp"

Then you can run the projects with the following commands:
- ws2kafka: `sbt run`
- kafka2mongodb: `sbt run`
- rsvp-endpoins:
```
npm install
npm start
```

## Architecture
![img](https://github.com/jorgeyp/rsvp-stream-exercise/blob/master/RSVP%20stream%20exercise%20architecture.png)

## Usefull snippets

Run Zookeper:
`bin/kafka-topics.sh --list --zookeeper localhost:2181`

Run Kafka:
`bin/kafka-server-start.sh config/server.properties`

Create topic:
`bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic meetup`

Set topic retention time:
`bin/kafka-configs.sh --zookeeper localhost:2181 --entity-type topics --entity-name meetup --alter --add-config retention.ms=180000`
