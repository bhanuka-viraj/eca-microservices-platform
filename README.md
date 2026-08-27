# Enterprise Cloud Architecture - Microservices Platform Super-Repository

## 👨‍🎓 Student & Project Information
- **Student Name:** J P Bhanuka Viraj Madhuranga
- **Student ID:** 241711105
- **GitHub Username:** bhanuka-viraj
- **GCP Project ID:** enterprise-cloud-module-503705
- **GCP Region:** `us-central1` (Multi-zone: `us-central1-a`, `us-central1-b`)

---

## 🌐 Live Production Endpoints

| Component | Architecture Role | Live Public URL | Protocol / Health |
| :--- | :--- | :--- | :--- |
| **API Gateway** | Global Load Balancer (Port 80 $\to$ 8080) | [http://34.160.86.95/api/v1/courses](http://34.160.86.95/api/v1/courses) | HTTP 200 OK |
| **Config Server** | Global Load Balancer (Port 80 $\to$ 8888) | [http://34.160.42.139/actuator/health](http://34.160.42.139/actuator/health) | HTTP 200 OK |
| **Eureka Service Registry** | Platform VM Instance Direct | [http://34.44.99.62:8761](http://34.44.99.62:8761) | HTTP 200 OK |
| **Frontend Web App** | Global Load Balancer $\to$ Cloud Run | [http://34.111.29.195](http://34.111.29.195) | HTTP 200 OK |

---

## 🏛️ Platform Architecture Overview

This super-repository manages the core Spring Cloud platform services for the EduCloud enterprise system using Git submodules:

### Platform Services (Git Submodules)
- **[Eureka Service Registry](https://github.com/bhanuka-viraj/eureka-server):** Centralized service discovery & dynamic instance registration (Port 8761).
- **[Spring Cloud Config Server](https://github.com/bhanuka-viraj/config-server):** Centralized configuration management with Git and Native classpath backends (Port 8888).
- **[Spring Cloud API Gateway](https://github.com/bhanuka-viraj/api-gateway):** Reactive Spring Cloud Gateway providing single entry point, dynamic Eureka discovery routing, CORS filters, and Actuator telemetry (Port 8080).

---

## 🖥️ Compute Engine Multi-Zone Deployment

- **Managed Instance Group:** `educloud-platform-mig`
- **Zones:** `us-central1-a`, `us-central1-b`
- **Instance Template:** `educloud-public-template-v1`
- **Named Ports:** `http:8080`, `config:8888`, `eureka:8761`
- **Process Manager:** PM2 daemon configured for automated startup, fault tolerance, and restart policies.

---

## 🛠️ Technology Stack
- Java 25
- Spring Boot 4.1.1
- Spring Cloud 2025.1.3 (Eureka Server, Config Server, Cloud Gateway)
- PM2 Process Manager
- Google Cloud Platform (Compute Engine Multi-Zone MIGs, Cloud Load Balancing, Cloud NAT)

---

## 💻 Local Development & Setup

```bash
# Clone super-repository with all submodules
git clone --recurse-submodules https://github.com/bhanuka-viraj/eca-microservices-platform.git
cd eca-microservices-platform

# Build all platform components
cd eureka-server && ./mvnw clean package && cd ..
cd config-server && ./mvnw clean package && cd ..
cd api-gateway && ./mvnw clean package && cd ..
```
