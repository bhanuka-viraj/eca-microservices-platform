# Microservices Platform Super-Repository

## Student Information
- **Student Name:** [Your Full Name]
- **Student Number:** [Your Student Number]
- **Slack Handle:** [@your-slack-handle]
- **GCP Project ID:** [your-gcp-project-id]

---

## Project Description
This super-repository manages the core Spring Cloud platform services for the Enterprise Cloud Architecture project.

### Platform Services (Git Submodules):
- [Eureka Service Registry](eureka-server)
- [Config Server](config-server)
- [API Gateway](api-gateway)

---

## Technology Stack
- Java 25
- Spring Boot 3.x
- Spring Cloud 2024.x (Eureka Server, Config Server, Cloud Gateway)
- PM2 Process Manager
- Google Cloud Platform (Compute Engine Multi-Zone MIGs)

---

## Setup & Local Development
```bash
# Clone repository with all submodules
git clone --recurse-submodules https://github.com/<username>/platform-repo.git

# Build all services
cd eureka-server && ./mvnw clean package
cd ../config-server && ./mvnw clean package
cd ../api-gateway && ./mvnw clean package
```\n