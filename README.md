# 🧾 Keyshell Payment App – Microservices Deployment with Docker & CI/CD

This project demonstrates the deployment of a microservices-based payment application using Docker containers, CI/CD pipelines via Jenkins, and a full suite of DevOps tools for quality assurance, monitoring, caching, and centralized logging.

## 🚀 Tech Stack

| Layer         | Technology                          |
|--------------|--------------------------------------|
| Frontend     | Angular + Nginx                      |
| Backend      | Python (FastAPI)                     |
| Database     | MongoDB                              |
| Caching      | Redis                                |
| Logging      | ELK Stack (Elasticsearch, Logstash, Kibana) |
| Monitoring   | Prometheus, Grafana, Node Exporter, cAdvisor |
| CI/CD        | Jenkins, SonarQube, Nexus            |
| Containerization | Docker, Docker Compose           |
| Infrastructure | Ubuntu EC2 Instance                |

---

## 📦 Microservices Architecture

Each service runs in its own Docker container:

- **Frontend**: Angular app served via Nginx
- **Backend**:
  - `auth_service`: FastAPI with Uvicorn
  - `payment_service`: FastAPI with Redis integration
- **Database**: MongoDB
- **Caching**: Redis for session management
- **Logging**: ELK stack for centralized log aggregation
- **Monitoring**: Prometheus + Grafana dashboards

---

## 🔁 CI/CD Pipeline Overview

1. **Code Checkout**: Jenkins pulls latest code from GitHub
2. **Code Quality**: SonarQube static analysis for frontend and backend
3. **Build**:
   - Angular frontend via Angular CLI
   - Python backend with virtualenv and Uvicorn
4. **Dockerization**:
   - Dockerfiles for each service
   - Tagged and pushed to Nexus & DockerHub
5. **Deployment**: Docker Compose orchestrates all services
6. **Monitoring**:
   - Prometheus scrapes metrics
   - Grafana visualizes dashboards and alerts
7. **Logging**:
   - Logstash collects container logs
   - Elasticsearch indexes logs
   - Kibana visualizes logs
8. **Caching**: Redis stores session data for fast retrieval

---

## 🛠️ Setup Instructions

### Prerequisites

- Ubuntu EC2 instance
- Installed tools:
  - Git, Jenkins, SonarQube, Nexus
  - Docker & Docker Compose
  - Node.js (via nvm), Angular CLI
  - Python 3.x, virtualenv
  - Prometheus, Grafana, ELK Stack

### Jenkins Configuration

- Install required plugins
- Configure global tools and credentials
- Define pipeline stages for:
  - SonarQube analysis
  - Docker image build and push
  - Deployment via Docker Compose

---

## 📊 Monitoring & Logging

- **Grafana Dashboards**:
  - Node Exporter (1860)
  - Docker cAdvisor (13946)
- **Prometheus Alerts**:
  - Alertmanager container with custom rules
- **ELK Stack**:
  - Logstash input/filter/output pipeline
  - Elasticsearch indexing
  - Kibana dashboards for log analysis

---

## 🔐 Redis Integration

- Redis container runs on shared Docker network
- Integrated with `payment_service` for session caching
- Speeds up transaction retrieval and reduces DB load

---

## 📁 Repository

- GitHub: [KEYSHELL-PAYMENT-APPLICATION/payment_application](https://github.com/KEYSHELL-PAYMENT-APPLICATION/payment_application)

---

## 📌 Notes

- Backend services use same internal ports due to Docker network isolation
- Nginx reverse proxy routes requests to appropriate backend services
- Custom `nginx.conf` and `default.conf` define routing logic

---

## 👨‍💻 Author

**Thomas V Varghese**  
Junior DevOps/Cloud Engineer at Keyshell IT Solutions  
Focused on scalable CI/CD workflows, cloud-native deployment, and infrastructure automation.

---

