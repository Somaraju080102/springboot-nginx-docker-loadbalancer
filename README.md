Spring Boot + Nginx Load Balancer using Docker Compose

This project demonstrates how to run a Spring Boot application behind Nginx, using Docker Compose with load balancing across multiple instances.

It includes:

🐳 Dockerized Spring Boot application

🌀 Nginx reverse proxy

⚖️ Load balancing (round-robin) between multiple app containers

🔗 Single entrypoint for clients

📡 Automatic container networking

                     Client
                        |
                        v
                 http://localhost:8081
                        |
                 +----------------+
                 |     NGINX      |
                 |  Reverse Proxy |
                 +--------+-------+
                          |
        -------------------------------------
        |                                   |
        v                                   v
 +-------------+                     +-------------+
 |  spring1    |                     |  spring2    |
 | (App Inst 1)|                     | (App Inst 2)|
 +-------------+                     +-------------+


**🧰 Technologies Used
**

    Spring Boot

    Docker

    Docker Compose

    Nginx (reverse proxy + load balancer)

    Temurin JDK 17 (Docker base image)

**🛠️ How to Run
**
**   1️⃣ Clone the repository
**  
      git clone https://github.com/<your-username>/springboot-nginx-docker-loadbalancer.git
      cd springboot-nginx-docker-loadbalancer

**  2️⃣ Ensure your Spring Boot JAR is placed in app/ as:
**  
      app/springapp.jar
      
**  3️⃣ Start all services
**  
      docker-compose up -d

**4️⃣ Check running containers
**
    docker ps


**  You should see: **

    nginx

    spring1

    spring2

5️⃣ Test the application

Open:

http://localhost:8081/instance


Refresh multiple times — you will see responses alternate between:

Served by instance: spring1
Served by instance: spring2


🎉 Load balancing works!

  
