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
PORT=8080 Or 8081
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

## User Register
Register a new user by sending a POST request to http://localhost:8081/user/register with the following JSON data:
```json
{
    "name": "Test User",
    "email": "{{REAL_EMAIL_ADDRESS}}",
    "password": "password"
}
```
Replace REAL_EMAIL_ADDRESS with a valid email address (we’ll need this to send emails). Upon successful registration, proceed to log in by sending a POST request to [http://localhost:8080/user/login](http://localhost:8081/user/login) with the registered email and password.

## User Login
Login a user by sending a POST request to http://localhost:8081/user/login with the following JSON data:
```json
{
    "email": "{{REAL_EMAIL_ADDRESS}}",
    "password": "password"
}
```

## Message Sending
Send a message by making a POST request to [http://localhost:8080/chat/send](http://localhost:8080/chat/send) with the following JSON data:
```json
{
    "receiverId": "{{RECEIVER_ID}}",
    "message": "Hello there!"
}
```
Replace RECEIVER_ID with the ID of another registered user obtained from the registration response. Upon sending the message, an email notification will be dispatched to the recipient's email address.

## Recived Messages
Get Your messages by making a get request to [http://localhost:8080/get/userId](http://localhost:8080/get/userId)].
