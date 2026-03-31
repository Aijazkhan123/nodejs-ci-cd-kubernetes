# ☸️ nodejs-ci-cd-kubernetes

![CI](https://img.shields.io/badge/CI-passing-39d353?style=flat-square&logo=github-actions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-ready-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-orchestrated-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-18.x-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

> A production-grade Node.js application with a complete CI/CD pipeline and Kubernetes deployment configuration. Demonstrates the full modern DevOps workflow — from source code to automated container builds to Kubernetes-orchestrated deployment.

---

## 🏗️ Architecture

![Architecture Diagram](architecture.png)

---

## 📁 Project Structure

```
nodejs-ci-cd-kubernetes/
├── .github/
│   └── workflows/
│       └── ci-cd.yml       # GitHub Actions pipeline definition
├── k8s/
│   ├── deployment.yaml     # Kubernetes Deployment manifest
│   └── service.yaml        # Kubernetes Service manifest
├── app.js                  # Node.js application entry point
├── package.json            # Dependencies and npm scripts
└── Dockerfile              # Container image definition
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| **Application** | Node.js + JavaScript | Backend API / web server |
| **Containerization** | Docker | Package the application into a portable image |
| **Orchestration** | Kubernetes | Scale, manage, and deploy containers |
| **CI/CD** | GitHub Actions | Automate build → test → deploy pipeline |
| **Registry** | Docker Hub / GHCR | Store and version container images |

---

## ⚡ Getting Started

### Run with Docker

```bash
# Clone the repository
git clone https://github.com/Aijazkhan123/nodejs-ci-cd-kubernetes.git
cd nodejs-ci-cd-kubernetes

# Build the Docker image
docker build -t nodejs-ci-cd-kubernetes .

# Run the container
docker run -p 3000:3000 nodejs-ci-cd-kubernetes
```

Visit: **http://localhost:3000**

---

### Deploy to Kubernetes

```bash
# Apply the Deployment and Service manifests
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml

# Verify the rollout
kubectl get pods
# NAME                          READY   STATUS    RESTARTS   AGE
# nodejs-app-7d4f9b-xk2lm       1/1     Running   0          42s
# nodejs-app-7d4f9b-p9qr1       1/1     Running   0          42s
# nodejs-app-7d4f9b-n3vw8       1/1     Running   0          42s

kubectl get services
```

---

### Run Locally (without Docker)

```bash
npm install
node app.js
```

---

## ⚙️ CI/CD Pipeline

The GitHub Actions workflow triggers on every `git push` to the `main` branch and executes the following stages:

```
 01 ──► 02 ──► 03 ──► 04 ──► 05 ──► 06
 │      │      │      │      │      │
 ▼      ▼      ▼      ▼      ▼      ▼
Checkout  Install  Test   Build   Push   Deploy
source    deps     suite  image   image  k8s
```

| Step | Action | Command |
|---|---|---|
| **1** | Checkout source code | `actions/checkout@v3` |
| **2** | Install Node.js dependencies | `npm install` |
| **3** | Run test suite | `npm test` |
| **4** | Build Docker image | `docker build` |
| **5** | Push to container registry | `docker push` |
| **6** | Deploy to Kubernetes | `kubectl apply` |

---

## 🧠 What I Learned

- Deploying containerized Node.js applications on Kubernetes using Deployment and Service manifests
- Writing full end-to-end CI/CD pipelines with GitHub Actions from scratch
- Understanding pod scaling, rolling updates, and service networking in Kubernetes
- Building and publishing Docker images to container registries as part of an automated pipeline

---

## 🗺️ Planned Improvements

| Feature | Description |
|---|---|
| **Horizontal Pod Autoscaler (HPA)** | Auto-scale pods based on CPU/memory usage under load |
| **NGINX Ingress** | Domain routing with TLS termination via cert-manager |
| **Helm Chart** | Parameterized, reusable deployments across environments |
| **Secrets Management** | Kubernetes Secrets + HashiCorp Vault integration |
| **Prometheus + Grafana** | Full observability stack for metrics and alerting |
| **Semantic Versioning** | Auto-tagged image releases tied to git tags via CI |

---

## 📜 License

[MIT License](LICENSE) — free to fork, learn from, and build upon.

---

`Node.js` · `Docker` · `Kubernetes` · `GitHub Actions` · `CI/CD` · `DevOps` · `Container Orchestration`
