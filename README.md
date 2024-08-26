# Food Delivery Rider Updates Using Kafka
In a food delivery system, real-time updates about rider status are crucial for efficient order management and customer satisfaction. 
We can create a robust and scalable architecture for handling these updates by leveraging Apache Kafka. 
Kafka's publish-subscribe model enables us to efficiently stream rider status updates to various components of our system.

- ## Knowledge
  - Node.JS Intermediate level
  - Experience with designing distributed systems
- ## Prerequisites/Tools
  - Node.js: [Download Node.JS](https://nodejs.org/en)
  - Docker: [Download Docker](https://www.docker.com)
  - VsCode: [Download VSCode](https://code.visualstudio.com)

## Commands
- Start Zookeper Container and expose PORT `2181`.
```bash
docker run -p 2181:2181 zookeeper
```
- Start Kafka Container, expose PORT `9092` and setup ENV variables.
```bash
docker run -p 9092:9092 \
-e KAFKA_ZOOKEEPER_CONNECT=<PRIVATE_IP>:2181 \
-e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://<PRIVATE_IP>:9092 \
-e KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR=1 \
confluentinc/cp-kafka
```

## Running Locally
- Run Multiple Consumers
- Create Producer

```bash
node admin.js
```

```bash
node producer.js > <name region-name>
node producer.js > Utsav south
node producer.js > Utsav north
```

```bash
node consumer.js <GROUP_NAME>
node consumer.js user-1
```
