# Spring Boot + Nginx Load Balancer using Docker Compose

This project demonstrates how to run a **Spring Boot application behind Nginx** using **Docker Compose**, with **load balancing** across multiple application instances.

The setup includes:
- 🐳 Dockerized Spring Boot Application
- 🌀 Nginx Reverse Proxy
- ⚖️ Round-robin Load Balancing
- 🔗 Automatic Docker Networking

---

## Architecture Overview

```
                     Client
                        |
                        v
                 http://localhost:8081
                        |
                 +----------------+
                 |     NGINX      |
                 |  Load Balancer |
                 +--------+-------+
                          |
        -------------------------------------
        |                                   |
        v                                   v
 +-------------+                     +-------------+
 |  spring1    |                     |  spring2    |
 | (Instance 1)|                     | (Instance 2)|
 +-------------+                     +-------------+
```

---

## Technologies Used

- Spring Boot
- Docker
- Docker Compose
- Nginx
- Temurin JDK 17

---

## Project Structure

```
project-root/
│
├── docker-compose.yml
│
├── nginx/
│   └── default.conf
│
└── app/
    └── springapp.jar
```

---

## Running the Project

1. Clone the repo:
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

2. Place your Spring Boot JAR as `app/springapp.jar`.

3. Start services:
```bash
docker-compose up -d
```

4. Verify:
```bash
docker ps
```

---

## Testing Load Balancing

Visit:
```
http://localhost:8081/instance
```

Refresh several times — responses should alternate between `spring1` and `spring2`.

---

## Stopping the Services

```bash
docker-compose down
```

---

## Author

**Naga Venkata Somaraju Indukuri**
Spring Boot | Docker | Nginx | DevOps
