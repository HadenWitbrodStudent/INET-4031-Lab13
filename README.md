# Docker Lab: Containerizing a Three-Tier Application
**INET 4031 - Introductions to Systems**

# Project Overview

This application is a web app consisting of a frontend: Apache, backend API: Flask, and a database: MariaDB.

The user interacts with the web interface, which communicates with the Flask service, which in turn reads/writes data from the database.

---

# Prerequisites

- Docker
- Docker Compose
- Git
- Access to a Linux VM

---

# Getting Started

### Docker Compose (original setup)
```bash
git clone <repo-url>
cd <repo-folder>
docker-compose up --build
````

### Kubernetes (current setup)

```bash
kubectl apply -f k8s/
```

---

# Configuration

The `.env` file stores environment variables used by the application, such as:

* Database name
* Database user
* Database password

These values are required for the application to connect to MariaDB. A teammate should ensure these values are set correctly before starting the application.

---

# Verification

To verify the application is running:

* Ensure all containers/pods are running:

```bash
docker ps
kubectl get pods
```

* Access the application:

  * Docker Compose: [http://localhost](http://localhost)
  * Kubernetes: http://<VM-IP>:30080

* Run the provided check script (if applicable) and confirm it completes without errors.

---

# Kubernetes Deployment

The application has been migrated from Docker Compose to Kubernetes. It now runs as managed Pods, with Deployments handling scaling and self-healing, and Services handling networking.

### Deploy the application

```bash
kubectl apply -f k8s/
```

### Access the dashboard

http://<VM-IP>:30080

---
