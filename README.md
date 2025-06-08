# Kafka with Node.js

This project sets up a **Kafka** message broker using Docker, with **Node.js** scripts for producing and consuming messages. Ideal for learning or testing **distributed systems** and messaging patterns.

---

## 🧠 Prerequisites

Ensure you have a basic understanding of the following:

- Intermediate **Node.js** development
- Basics of **Kafka** and **distributed system** design

---

## 🛠 Tools Required

| Tool      | Description              | Download Link                          |
|-----------|--------------------------|----------------------------------------|
| Node.js   | JavaScript runtime       | [nodejs.org](https://nodejs.org)       |
| Docker    | Container engine         | [docker.com](https://www.docker.com)   |
| VS Code   | Code editor (recommended)| [code.visualstudio.com](https://code.visualstudio.com) |

---

## 🐳 Docker Setup

### 1. Start Zookeeper

Run Zookeeper container (default port 2181):

```bash
docker run -p 2181:2181 zookeeper
docker run -p 9092:9092 \
-e KAFKA_ZOOKEEPER_CONNECT=<PRIVATE_IP>:2181 \
-e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://<PRIVATE_IP>:9092 \
-e KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR=1 \
confluentinc/cp-kafka
```
🔐 Replace <PRIVATE_IP> with your actual local machine IP address (e.g., 192.168.1.100).
## ▶️ Running Locally

### Install Dependencies

```bash
npm install
```
## 1. Run a Producer

# Sends messages to a topic:

```bash
node producer.js
```
## 2. Run Multiple Consumers
#Consumes messages from a topic using consumer groups:
```
node consumer.js <GROUP_NAME>
example:
node consumer.js group-1
node consumer.js group-2
```


