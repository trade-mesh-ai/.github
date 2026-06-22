# ⚡ Trade Mesh AI

> **Event-Driven Trading Microservices Architecture**  
> Built by [Kuldeep Singh](https://github.com/kuldeepsingh123) · Associate Principal Engineer · Fintech & Microservices Specialist

---

## 👋 About

**Trade Mesh** is a production-grade microservices ecosystem for modern trading platforms — built with a focus on high throughput, low latency, and resilient event-driven design.

Here you'll find services covering:

- 📈 **Order Management** — Place, modify, cancel and track trade orders
- 💹 **Market Data** — Real-time price feeds and market event streaming
- ⚙️ **Trade Execution** — Order matching and execution engine
- 🔔 **Notification Service** — Alerts and trade confirmations
- 🛡️ **Risk & Compliance** — Pre-trade risk checks and audit trails
- 🌐 **API Gateway** — Unified entry point with OAuth 2.0 & JWT security

---

## 🏗️ Architecture

```
                        ┌─────────────────┐
                        │   API Gateway   │  ← Spring Cloud Gateway
                        │  OAuth 2.0/JWT  │
                        └────────┬────────┘
                                 │
              ┌──────────────────┼──────────────────┐
              │                  │                  │
     ┌────────▼───────┐ ┌───────▼────────┐ ┌───────▼────────┐
     │  Order Service │ │ Market Data Svc│ │Execution Engine│
     │  Spring Boot   │ │ Spring WebFlux │ │  Spring Boot   │
     └────────┬───────┘ └───────┬────────┘ └───────┬────────┘
              │                  │                  │
              └──────────────────┼──────────────────┘
                                 │
                        ┌────────▼────────┐
                        │  Apache Kafka   │  ← Event Backbone
                        │  Event Streams  │
                        └────────┬────────┘
                                 │
              ┌──────────────────┼──────────────────┐
              │                  │                  │
     ┌────────▼───────┐ ┌───────▼────────┐ ┌───────▼────────┐
     │  Notification  │ │ Risk & Compliance│ │   Audit Log   │
     │    Service     │ │    Service      │ │    Service    │
     └────────────────┘ └────────────────┘ └───────────────┘
```

---

## 📦 Repositories

| Repo | Description | Stack |
|------|-------------|-------|
| [`trade-mesh`](https://github.com/trade-mesh/trade-mesh) | Monorepo — all microservices | Spring Boot, Kafka, WebFlux |
| [`order-service`](https://github.com/trade-mesh/order-service) | Order lifecycle management | Spring Boot, JPA, Kafka |
| [`market-data-service`](https://github.com/trade-mesh/market-data-service) | Real-time market data streaming | Spring WebFlux, Kafka |
| [`execution-engine`](https://github.com/trade-mesh/execution-engine) | Trade matching & execution | Spring Boot, Kafka |
| [`notification-service`](https://github.com/trade-mesh/notification-service) | Trade alerts & confirmations | Spring Boot, Kafka |
| [`api-gateway`](https://github.com/trade-mesh/api-gateway) | Unified gateway with auth | Spring Cloud Gateway, JWT |

---

## 🛠️ Tech Stack

```
Languages       →  Java 17+, Python
Backend         →  Spring Boot 3.x, Spring WebFlux, Apache Camel
Messaging       →  Apache Kafka, Kafka Streams
Security        →  OAuth 2.0, JWT
Data            →  PostgreSQL, Redis, Hibernate / JPA
DevOps          →  Docker, Kubernetes, GitHub Actions
Observability   →  Micrometer, Prometheus, Grafana
```

---

## 🚀 Getting Started

```bash
# Clone the monorepo
git clone https://github.com/trade-mesh/trade-mesh.git
cd trade-mesh

# Copy environment config
cp .env.example .env

# Spin up all services with Docker Compose
docker-compose up -d
```

Services will be available at:
- API Gateway → `http://localhost:8080`
- Kafka UI    → `http://localhost:9090`
- Grafana     → `http://localhost:3000`

---

## 📬 Connect

- 💼 [LinkedIn](https://www.linkedin.com/in/kuldeepsingh-engineer)
- 🐙 [GitHub](https://github.com/kuldeepsingh123)
- 🧠 [MicroMinds AI](https://github.com/microminds-ai) ← my AI & engineering org
- 📧 Open an issue on any repo for questions or collaboration

---

> *"In trading, milliseconds matter. In microservices, boundaries matter. Trade Mesh respects both."*

![Java](https://img.shields.io/badge/Java-17+-orange?style=flat-square&logo=java)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen?style=flat-square&logo=springboot)
![Apache Kafka](https://img.shields.io/badge/Kafka-Event--Driven-black?style=flat-square&logo=apachekafka)
![Spring WebFlux](https://img.shields.io/badge/WebFlux-Reactive-blue?style=flat-square&logo=spring)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=flat-square&logo=docker)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)
