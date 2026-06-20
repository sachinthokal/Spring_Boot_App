# 🚀 DevOps Practice Application (Product Catalog Console)

Welcome to the **DevOps Practice Application**. This is a lightweight Spring Boot 3.x microservice tailored specifically for DevOps engineers to practice containerization, CI/CD pipelines, monitoring, and chaos engineering.

It features a **clean, single-screen responsive UI dashboard** connected to live backend endpoints and an integrated chaos testing laboratory.

---

## 🛠️ Project Stack & Architecture

- **Backend:** Java 17 / 21, Spring Boot 3.x
- **DevOps Core:** Spring Boot Actuator (Health & Metrics tracking)
- **Frontend UI:** Single-Screen Premium Dashboard (HTML5, Tailwind CSS, JavaScript Fetch API)
- **Containerization:** Multi-stage Dockerfile optimized for minimal size

---

## 🔌 Available Endpoints

The application exposes the following endpoints, mapped visually onto the UI dashboard:

| Endpoint | Method | Purpose / DevOps Use-Case |
| :--- | :--- | :--- |
| `/` or `/index.html` | `GET` | The Main Single-Screen Control Console |
| `/api/products` | `GET` | Simulates fetching live transactional inventory data |
| `/api/slow` | `GET` | **Chaos Endpoint:** Injects a strict **5-second delay** (useful to test high latency alerts & gateway timeouts) |
| `/api/error` | `GET` | **Chaos Endpoint:** Triggers an intentional **HTTP 500 Internal Error** (useful to test Prometheus alert manager routing) |
| `/actuator/health` | `GET` | Exposes liveness and readiness state for Kubernetes Probes |
| `/actuator/metrics` | `GET` | Exposes JVM raw performance data for scraping |

---

## 🐳 Running Locally with Docker

This project comes equipped with a production-optimized **multi-stage Dockerfile**. To containerize and run this application locally, use the following commands:

### 1. Build the Docker Image
```bash
docker build -t devops-demo:v1 .

```

### 2. Launch the Container

```bash
docker run -d -p 8080:8080 --name my-devops-app devops-demo:v1

```

Once running, access the dashboard on: **`http://localhost:8080/`**

---

## 🎯 Planned DevOps Practice Milestones

This repository is built to be a testing ground for the following implementations:

* [x] **Milestone 1:** Basic REST API Setup & Local Verification
* [x] **Milestone 2:** Embedded Single-Screen User Interface
* [ ] **Milestone 3:** Native Multistage Dockerfile Containerization
* [ ] **Milestone 4:** Automated CI/CD Pipeline (GitHub Actions to push images to Docker Hub)
* [ ] **Milestone 5:** Orchestration with Kubernetes Manifests (Deployments, Services & Liveness Probes)
* [ ] **Milestone 6:** Monitoring Setup using Prometheus & Grafana Dashboards

---
