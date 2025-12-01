# JRU-PULSE: DevOps Orchestration and Containerization

## Overview
This repository showcases the Infrastructure as Code (IaC) and container orchestration for JRU-PULSE, an intelligent Survey & Analytics Platform built on a polyglot microservices architecture.

The goal of this project was to transition the entire multi-service application from a manually configured VPS setup to a fully reproducible, Docker-orchestrated environment.

## Architecture: Docker COmpose Design
PHP Web App (8080) <-> Network <-> Python API (80) <-> Network <-> MySQL DB
![Alt Text for the image](/images/JRU-PULSE%20-%20Docker%20Composer%20-%20System%20Archi.png)

## DevOps SKill Demonstrated

- **Service Orchestration:** Deployed a functional, three-tier, polygot application stack (PHP, Python, MySQL) using a single, declarative **docker-composer.yml** file, adhering to the principle of Infrastucture as Code (IaC).

- **Internal Networking & Service Connection:** Solved the internal connection problem by teaching the PHP Web App to find the Python API using its service name (python-api) instead of a fixed IP address like 127.0.0.1.

- **Configuration Management (Secrets):** Kept application configuration secure and flexible by moving sensitive data (like database passwords and Google keys) out of the code and into a single .env file, which Docker securely delivers to the right containers.

- **Data Reliability (Persistence)**: Ensured data safety for the MySQL database by correctly setting up a persistent volume (db-data). This guarantees that user data is never lost, even when the database container is stopped or replaced.

- **Efficient Image Building:** Built production-ready images for a complex Python AI service by creating a clean, efficient Dockerfile. This shows the ability to manage large dependencies and keep deployment packages small.

- **Practical Troubleshooting (Debugging):** Identified and fixed real-world errors (like port mismatches, PHP code initialization bugs, and external service connection failures) by relying on logs and the Docker command line, demonstrating strong debugging capability.

## Deployment (IaC) 

The entire JRU-PULSE stack is defined in the single docker-compose.yml file below, enabling a complete, reproducible deployment using standard Docker commands.

Steps: 

1. Clone the repository
        `git clone https://github.com/xelmx/jru-pulse-devops-orchestration.git`
        `cd jru-pulse-devops-orchestration`

2. Build the custom application images (PHP and Python):
        `sudo docker compose build`

3. Start the entire stack (PHP Web App, Python API, MySQL DB):
        `sudo docker compose up -d`
        ![Alt Text for the image](images/Docker%20Compose%20Up.png)

4. Access the Application: The PHP Web App is accessible at http://localhost:8080.



--Please see **docker-compose.yml** for the full IaC.