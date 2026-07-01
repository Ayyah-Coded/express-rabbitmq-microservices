# 🚀 Express RabbitMQ Microservices

![Node.js](https://img.shields.io/badge/Node.js-22.x-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-Framework-000000?style=for-the-badge&logo=express&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-Message_Broker-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-Database-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=for-the-badge&logo=docker&logoColor=white)

![GitHub stars](https://img.shields.io/github/stars/yahayahayat/express-rabbitmq-microservices?style=for-the-badge)
![GitHub forks](https://img.shields.io/github/forks/yahayahayat/express-rabbitmq-microservices?style=for-the-badge)
![GitHub last commit](https://img.shields.io/github/last-commit/yahayahayat/express-rabbitmq-microservices?style=for-the-badge)
![GitHub License](https://img.shields.io/github/license/yahayahayat/express-rabbitmq-microservices?style=for-the-badge)

> A lightweight event-driven microservices architecture built with **Express.js**, **RabbitMQ**, and **MongoDB**, containerized for local development using **Docker** and **Docker Compose**.

## 📖 Overview

This project demonstrates how asynchronous communication works in a microservices architecture using **RabbitMQ** as a message broker.

It consists of three independent Express.js services:

- 👤 **User Service** – Handles user-related operations.
- 📋 **Task Service** – Manages tasks and publishes events to RabbitMQ.
- 🔔 **Notification Service** – Consumes events from RabbitMQ and processes notifications asynchronously.

The project was built as a learning exercise to gain hands-on experience with:

- Microservices architecture
- Event-driven communication
- RabbitMQ messaging
- Docker containerization
- MongoDB integration
- Service isolation and orchestration

---

## 🏗️ Architecture

```text
                +----------------+
                |   User Service |
                +----------------+
                        |
                        |
                        v
                    MongoDB

+---------------+      Publish Event      +-------------------+
| Task Service  | ----------------------> |     RabbitMQ      |
+---------------+                         +-------------------+
                                                  |
                                                  |
                                           Consume Event
                                                  |
                                                  v
                                      +----------------------+
                                      | Notification Service |
                                      +----------------------+
                                                  |
                                                  v
                                               MongoDB
```

---

## ⚙️ Tech Stack

| Technology | Purpose |
|------------|---------|
| Express.js | REST API |
| RabbitMQ | Asynchronous messaging |
| MongoDB | Database |
| Docker | Containerization |
| Docker Compose | Multi-container orchestration |
| Node.js | Runtime |

---

## 📁 Project Structure

```text
express-rabbitmq-microservices/
│
├── docker-compose.yml
│
├── user-service/
│   ├── Dockerfile
│   ├── package.json
│   └── index.js
│
├── task-service/
│   ├── Dockerfile
│   ├── package.json
│   └── index.js
│
└── notification-service/
    ├── Dockerfile
    ├── package.json
    └── index.js
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have installed:

- Docker
- Docker Compose

Verify installation

```bash
docker --version
docker compose version
```

---

## ▶️ Run the Project

Clone the repository

```bash
git clone https://github.com/Ayyah-Coded/express-rabbitmq-microservices.git
```

Navigate into the project

```bash
cd express-rabbitmq-microservices
```

Build and start all containers

```bash
docker compose up --build -d
```

---

## 🐳 Running Containers

The command above starts:

| Service | Port |
|----------|------|
| MongoDB | 27017 |
| RabbitMQ | 5672 |
| RabbitMQ Management UI | 15672 |
| User Service | 3001 |
| Task Service | 3002 |
| Notification Service | 3003 |

---

## 🐇 RabbitMQ Management Dashboard

RabbitMQ includes a web dashboard.

Open:

```
http://localhost:15672
```

Default credentials

```
Username: guest
Password: guest
```

---

## 🛑 Stop the Project

```bash
docker compose down
```

Remove containers and volumes

```bash
docker compose down -v
```

---

## 💡 How It Works

1. The **Task Service** creates a task.
2. It publishes an event to RabbitMQ.
3. RabbitMQ queues the event.
4. The **Notification Service** consumes the event.
5. The notification is processed asynchronously without blocking the Task Service.

This demonstrates loose coupling between services using message queues.

---

## 🎯 Learning Objectives

This project demonstrates practical knowledge of:

- RESTful API development
- Express.js
- Microservices architecture
- Event-driven design
- RabbitMQ producers and consumers
- Docker image creation
- Docker Compose orchestration
- MongoDB integration
- Asynchronous service communication

---

## 🔮 Possible Improvements

- API Gateway
- JWT Authentication
- Service discovery
- Centralized logging
- Distributed tracing
- Retry mechanism
- Dead Letter Queues (DLQ)
- Health checks
- Kubernetes deployment
- CI/CD pipeline
- Unit & integration tests

---

## 👨‍💻 Author

**Yahaya Hayatullahi**

Backend / Full-Stack Developer

GitHub: https://github.com/Ayyah-Coded

LinkedIn: https://linkedin.com/in/<your-profile>

Portfolio: https://<your-portfolio>

---

## 📄 License

This project is licensed under the MIT License.

---

⭐ If you found this project useful or interesting, consider giving it a star!
