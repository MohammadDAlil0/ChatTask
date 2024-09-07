# ChatTask

This project serves for building and deploying microservices using Node.js, Typescript, socket.io,and RabbitMQ.

## Table of Contents

- [Requirements](#requirements)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [APIs](#apis)
## Requirements

To run this project, you will need:

- Node.js
- MongoDB
- Typescript
- Docker

## Getting Started

### Prerequisites

Again, Make sure you have Node.js and MongoDB installed on your machine.

### Installation
1. Clone the repository:

```bash
git clone https://github.com/MohammadDAlil0/ChatTask
```
2. Install dependencies:
```bash
cd ChatTask
cd chat-service
npm install
cd ..
cd user-service
npm install
```
3. Set up environment variables:

Create 2 .env files in the root directory of each service and provide the following variables: 
```bash
NODE_ENV="development"
PORT=8080
JWT_SECRET="your-jwt-secret"
MONGO_URI="your-mongodb-url"
MESSAGE_BROKER_URL="your-message-broker-url"
```
4. Start the server in each service by running:
```bash
npm run dev
```
The first server should now be running on http://localhost:8080.
The second server should now be running on http://localhost:8081.

### APIs
