# 🛒 E-commerce Backend System – Java Spring Boot + Microservices

This is a demo of how I can structure and deliver a backend system using best practices.

A modular e-commerce backend system integrating multiple microservices including ecommerce (Spring Boot backend), coupon-thrift-service (Thrift microservice), and shared API modules.
Supports unified Docker Compose deployment for easy local development and testing.

## 🔧 Tech Stack
- Java 17, Spring Boot 3.x
- Spring Security (JWT)
- Apache Thrift for RPC microservices
- MySQL & PostgreSQL databases
- Docker & Docker Compose

## ✅ Features
- RESTful API (Spring Boot)
- JWT-based authentication and authorization
- MySQL Module: User & Product & Order
- PostgreSQL Module: PgReview demo (separate datasource)
- Pagination support for listing
- Thrift Module: CouponService (via RPC, independent Docker service)
- Swagger/OpenAPI Docs
- Dockerized: docker-compose for MySQL & PostgreSQL
- Clean project structure (multi-package separation)
- Postman collection provided
- External API Integration: Dynamic weather query by coordinates (Open-Meteo)

## 📁 Project Structure
```bash

ecommerce-system/
├── coupon-thrift-api/          # Shared Thrift API definitions
├── coupon-thrift-service/      # Coupon validation Thrift microservice
├── ecommerce/                  # Main Spring Boot backend (e-commerce)
├── docker-compose.yml          # Docker Compose for all modules and databases
└── README.md                  # This documentation file

```

## 🚀 How to run
### Prerequisites
- Docker & Docker Compose installed
- Ports 8080 (backend), 9090 (thrift service), 3306 (MySQL), 5432 (PostgreSQL) available

### Start all services
```bash
git clone <your-repo-url>
cd ecommerce-system

# Build images and start containers in detached mode
docker-compose up -d --build

```
Then visit Swagger UI: http://localhost:8080/swagger-ui/index.html

### Check status
```bash
docker-compose ps
```

### View logs
```bash
docker-compose logs -f ecommerce       # Spring Boot backend logs
docker-compose logs -f coupon-thrift-service  # Thrift microservice logs
```

### Stop all services
```bash
docker-compose down
```

## 🛠 Notes
- ecommerce service depends on the coupon-thrift-service running for coupon validation RPC
- Database initialization and migrations handled by Spring Boot JPA (or Flyway if added)
- You can modify configurations in docker-compose.yml as needed



