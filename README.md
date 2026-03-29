# 🚀 Production-Ready CI/CD Pipeline with Kubernetes (Node.js)

![CI](https://github.com/Aijazkhan123/nodejs-ci-cd-kubernetes/actions/workflows/main.yml/badge.svg)
![Docker](https://img.shields.io/badge/docker-ready-blue)
![Kubernetes](https://img.shields.io/badge/kubernetes-deployed-blue)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📌 Overview

This project demonstrates an **end-to-end CI/CD pipeline** for a containerized Node.js application, deployed on Kubernetes. It reflects a **production-like DevOps workflow** where code changes automatically trigger build, test, and deployment stages.

The goal of this project is to showcase hands-on expertise in **automation, containerization, and orchestration** using industry-standard tools.

---

## 🏗️ System Architecture

```
Developer → GitHub → GitHub Actions → DockerHub → Kubernetes Cluster
```

* **Continuous Integration (CI):** Automated build and Docker image creation
* **Continuous Deployment (CD):** Automatic rollout to Kubernetes cluster
* **Container Registry:** DockerHub stores versioned images

---

## 🛠️ Tech Stack

| Category         | Tools Used                   |
| ---------------- | ---------------------------- |
| Application      | Node.js (Express)            |
| CI/CD            | GitHub Actions               |
| Containerization | Docker                       |
| Orchestration    | Kubernetes (Kind / Minikube) |
| Registry         | DockerHub                    |
| Version Control  | Git & GitHub                 |

---

## ⚙️ Key Features

* ✅ Fully automated CI/CD pipeline
* ✅ Docker image build & push on every commit
* ✅ Kubernetes-based deployment with rolling updates
* ✅ Scalable and cloud-native architecture
* ✅ Clean separation of CI and CD stages

---

## 🔄 CI/CD Workflow

1. Developer pushes code to GitHub
2. GitHub Actions workflow is triggered
3. Application is built and tested
4. Docker image is created and pushed to DockerHub
5. Kubernetes deployment is updated with the latest image

---

## 📂 Project Structure

```
nodejs-ci-cd-kubernetes/
├── .github/
│   └── workflows/        # GitHub Actions CI/CD pipeline
├── k8s/
│   ├── deployment.yaml   # Kubernetes Deployment manifest
│   └── service.yaml      # Kubernetes Service manifest
├── app.js                # Node.js application
├── Dockerfile            # Container image definition
└── package.json          # Node.js dependencies
```

---

## 🚀 Run It Locally

### 🔹 With Docker

```bash
git clone https://github.com/Aijazkhan123/nodejs-ci-cd-kubernetes.git
cd nodejs-ci-cd-kubernetes
docker build -t nodejs-k8s-app .
docker run -p 3000:3000 nodejs-k8s-app
```

---

### 🔹 Deploy to Kubernetes

```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl get pods
kubectl get services
```

---

### 🔹 Without Docker

```bash
npm install
node app.js
```

---

## 📊 DevOps & Engineering Highlights

* 🔹 Designed and implemented a **complete CI/CD pipeline**
* 🔹 Applied **containerization best practices using Docker**
* 🔹 Deployed and managed workloads on **Kubernetes clusters**
* 🔹 Simulated **real-world DevOps workflows used in production**
* 🔹 Demonstrated understanding of **automation and scalability**

---

## 👨‍💻 Author

**Aijaz Khan**
🔗 GitHub: https://github.com/Aijazkhan123

---

## ⭐ Support

If you find this project useful, consider giving it a ⭐ — it helps increase visibility and showcases your work to recruiters.

---
