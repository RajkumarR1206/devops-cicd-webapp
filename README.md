
---

#  DevOps CI/CD Pipeline with Monitoring

## Project Overview

This project demonstrates the implementation of a complete **DevOps CI/CD pipeline** for a web application.
The pipeline automates **code integration, testing, deployment, and monitoring** using industry-standard DevOps tools.

The goal of this project is to showcase real-world DevOps practices such as Continuous Integration, Continuous Delivery, containerization, and system monitoring.

---

## Tools & Technologies Used

| Category               | Tool            |
| ---------------------- | --------------- |
| Cloud Platform         | Microsoft Azure |
| Operating System       | Ubuntu Linux    |
| Source Code Management | GitHub          |
| CI/CD Tool             | Jenkins         |
| Containerization       | Docker          |
| Web Application        | Python (Flask)  |
| Testing Framework      | Pytest          |
| Monitoring             | Prometheus      |
| Metrics Exporter       | Node Exporter   |
| Visualization          | Grafana         |

---

##  Project Architecture

```
Developer
   |
   |  Push Code
   v
GitHub Repository
   |
   |  Jenkins pulls code
   v
Jenkins CI/CD Pipeline
   |
   |--> Build Docker Image
   |--> Run Automated Tests
   |--> Deploy Application Container
   |
   v
Web Application (Docker)
   |
   v
Monitoring Stack
   |
   |--> Node Exporter
   |--> Prometheus
   |--> Grafana
```

---

##  CI/CD Pipeline Workflow

### 1. Source Code Integration

* Application source code is stored in GitHub.
* Jenkins pulls the latest code from the repository.

### 2. Continuous Integration (CI)

* Dependencies are prepared automatically.
* Automated tests are executed using Pytest.
* Pipeline stops if tests fail.

### 3. Continuous Delivery (CD)

* Docker image is built automatically.
* Old container is stopped and removed.
* New application container is deployed automatically.
* Application becomes live on the server.

### 4. Monitoring

* Node Exporter collects system metrics.
* Prometheus scrapes metrics at regular intervals.
* Grafana visualizes metrics using dashboards.

---

## Monitoring Details

### Prometheus

* Collects time-series metrics
* Verifies system health
* Accessible on:

  ```
  http://<VM-IP>:9090
  ```

### Grafana

* Displays real-time dashboards
* Visualizes CPU, memory, disk, and network usage
* Accessible on:

  ```
  http://<VM-IP>:3000
  ```

**Grafana Dashboard Used:**
Node Exporter Full (ID: `1860`)

---

## Features Implemented

* Automated build and deployment
* Dockerized application
* Automated testing
* Continuous Integration & Delivery
* Infrastructure monitoring
* Real-time visualization
* Cloud-based deployment

---

## Verification Steps

* Jenkins pipeline completes successfully
* Web application accessible via VM public IP
* Prometheus targets show **UP**
* Grafana dashboards display live metrics

---

##  Repository Structure

```
.
├── app.py
├── Dockerfile
├── Jenkinsfile
├── requirements.txt
├── tests/
│   └── test_app.py
└── README.md
```

---

## Project Outcome

This project successfully demonstrates a full DevOps lifecycle:

* Code integration
* Automated testing
* Automated deployment
* Continuous monitoring

It reflects real-world DevOps practices used in production environments.

---

## Future Enhancements

* GitHub webhook for auto-triggered builds
* Kubernetes deployment
* Application-level metrics
* Alertmanager integration
* Blue-green or rolling deployments

---

## Conclusion

This project provides a complete hands-on implementation of a DevOps CI/CD pipeline with monitoring.
It ensures faster deployments, reduced manual intervention, and better system observability.

---
