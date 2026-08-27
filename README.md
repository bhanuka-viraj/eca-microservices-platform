# Enterprise Cloud Architecture - Microservices Platform Super-Repository

## Student Information
- **Student Name:** J P Bhanuka Viraj Madhuranga
- **Student Number:** 241711105
- **GCP Project ID:** enterprise-cloud-module-503705

---

## Project Overview
This super-repository manages the core Spring Cloud platform services for the EduCloud enterprise system using Git submodules.

### Platform Services (Git Submodules)
- [Eureka Service Registry](https://github.com/bhanuka-viraj/eureka-server) — Service discovery & dynamic registration.
- [Spring Cloud Config Server](https://github.com/bhanuka-viraj/config-server) — Centralized configuration management.
- [Spring Cloud API Gateway](https://github.com/bhanuka-viraj/api-gateway) — Single entry point and reactive request routing.

---

## Technology Stack
- Java 25
- Spring Boot 4.1.1
- Spring Cloud 2025.1.3 (Eureka Server, Config Server, Cloud Gateway)
- PM2 Process Manager
- Google Cloud Platform (Compute Engine Multi-Zone MIGs)

---

## Local Development & Setup
`ash
# Clone super-repository with all submodules
git clone --recurse-submodules https://github.com/bhanuka-viraj/eca-microservices-platform.git
cd eca-microservices-platform

# Build all platform components
cd eureka-server && ./mvnw clean package && cd ..
cd config-server && ./mvnw clean package && cd ..
cd api-gateway && ./mvnw clean package && cd ..
`
