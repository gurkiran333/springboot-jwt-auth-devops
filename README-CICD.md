# CI/CD Automation for Spring Boot JWT Authentication (DevOps Project)

This repository demonstrates a **production-style CI/CD pipeline**
implemented for a **Spring Boot JWT Authentication Service** using
**Jenkins, Docker, and Maven**.

> **Important Note**  
> The application source code is inspired by an open-source Spring Boot
> JWT authentication example.  
> This project focuses **only on DevOps automation, CI/CD pipelines,
> containerization, and deployment best practices**.

---

## Project Objective

The goal of this project is to demonstrate how a DevOps engineer:

- Designs and automates CI/CD pipelines
- Works with existing Spring Boot application code
- Containerizes secure authentication services
- Implements real-world DevOps workflows used in production
- Builds portfolio-ready DevOps projects

---

## Tech Stack

| Category | Technology |
|--------|-----------|
| Language | Java 17 |
| Framework | Spring Boot |
| Security | Spring Security + JWT |
| Build Tool | Maven |
| CI/CD | Jenkins (Declarative Pipeline) |
| Containerization | Docker (Multi-stage build) |
| Base Image | eclipse-temurin |
| Application Port | 8082 |

---

## What I Implemented (My Contribution)

✔ Jenkins Declarative CI/CD Pipeline  
✔ Maven-based automated build process  
✔ Docker multi-stage image creation  
✔ Automated container deployment  
✔ Secure and repeatable CI/CD workflow  

> The **application business logic is not the focus**.  
> The **entire CI/CD, Docker, and deployment automation is designed and implemented by me**.

---

## CI/CD Pipeline Flow

1. Checkout source code from GitHub
2. Build Spring Boot application using Maven
3. Package application as executable JAR
4. Build Docker image using multi-stage Dockerfile
5. Stop & remove existing container (if running)
6. Deploy application as a Docker container

---

## Jenkinsfile Overview

Pipeline stages include:
- **Checkout**
- **Build Application**
- **Build Docker Image**
- **Deploy Docker Container**

The pipeline is fully automated and runs without manual intervention.

---

## Docker Strategy

- Multi-stage Docker build
- JDK image used only for build stage
- Lightweight JRE image used for runtime
- Final image contains only the application JAR

### Benefits
- Smaller Docker image size
- Improved container security
- Faster startup and deployment
- Production-aligned container strategy

---

## How to Run (Using Jenkins)

### Prerequisites
- Jenkins installed
- Docker installed on Jenkins node
- Git installed
- Docker Hub account (optional)

### Steps
1. Create a **Pipeline Job** in Jenkins
2. Connect this GitHub repository
3. Jenkins will automatically detect the `Jenkinsfile`
4. Click **Build Now**

Application will be accessible at:  
http://<jenkins-server-ip>:8080

---

## Learning Outcomes

- Real-world CI/CD pipeline design
- Docker multi-stage builds for Spring Boot
- Jenkins automation for Java applications
- DevOps best practices for production pipelines
- Portfolio-ready DevOps project structure

---

## Author

**Gurkiran Singh**  
DevOps Engineer  
GitHub: https://github.com/gurkiran333