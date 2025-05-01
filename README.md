# TP7: Microservices with REST, GraphQL, gRPC and Kafka

## Objective(s)
• Create two distinct microservices: one for movie data and another for TV series, using gRPC for communication between microservices.
• Implement an API Gateway that acts as an entry point for clients. The API Gateway must be able to serve data via RESTful and GraphQL endpoints.
• Integrate Kafka for communication between movie and TV series microservices.

## Tools Used
- Node.js
- Express
- Apollo Server
- gRPC
- body-parser
- CORS
- Kafka
- kafkajs

## Project Description
This project aims to implement a streaming API architecture based on Node.js. The main objective is to create a microservices system for movies and TV shows, which will then be connected through an API Gateway. The API Gateway will serve data to clients via RESTful and GraphQL endpoints. Additionally, the integration of Kafka into the architecture will enable asynchronous and reliable communication between microservices and the API Gateway, enhancing the system's robustness and scalability.

## Project Structure
The project is divided into several steps:
1. Microservices setup
2. API Gateway configuration
3. GraphQL schema definition
4. GraphQL resolvers implementation
5. Kafka integration in microservices

## Installation

### Prerequisites
1. Install NodeJS from [official website](https://nodejs.org/en/download)
   - On Ubuntu: `sudo snap install node --classic`
2. Download Kafka and Zookeeper binaries from [official website](https://kafka.apache.org/downloads)

### Setup
1. Create project directory:
   ```bash
   mkdir tp-microservices
   cd tp-microservices
   npm init -y


2. Install dependencies:
   npm install express @apollo/server @grpc/grpc-js @grpc/proto-loader body-parser cors kafkajs
3. File Structure
tp-microservices/
│
├── movie.proto              # Définition Protobuf des films
├── tvShow.proto             # Définition Protobuf des séries TV
│
├── movieMicroservice.js     # Microservice pour les films
├── tvShowMicroservice.js    # Microservice pour les séries TV
│
├── apiGateway.js            # Point d’entrée principal (REST + GraphQL)
├── resolvers.js             # Résolveurs GraphQL
├── schema.js                # Schéma GraphQL
│
├── package.json
└── README.md


Running the Services
Start services in the following order:

Movie microservice:
node movieMicroservice.js

TV show microservice:
node tvShowMicroservice.js

API Gateway:
node apiGateway.js

Testing
The API Gateway will be available at http://localhost:3000

REST endpoints:

Movies: /movies and /movies/:id

TV Shows: /tvshows and /tvshows/:id

GraphQL endpoint: /graphql

4. Kafka Integration
   kafka-topics --create --partitions 1 --replication-factor 1 --topic movies_topic --bootstrap-server localhost:9092
kafka-topics --create --partitions 1 --replication-factor 1 --topic tvshows_topic --bootstrap-server localhost:9092
