# ☸️ Node.js CI/CD with Kubernetes

[![Node.js](https://img.shields.io/badge/Node.js-Runtime-339933?logo=node.js)](https://nodejs.org)
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker)](https://docker.com)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestration-326CE5?logo=kubernetes)](https://kubernetes.io)
[![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-CI%2FCD-2088FF?logo=githubactions)](https://github.com/features/actions)

A production-grade Node.js application with a complete CI/CD pipeline and Kubernetes deployment configuration. This project demonstrates the full modern DevOps workflow — from code to automated container builds to Kubernetes-orchestrated deployment.

---

## 🏗️ Architecture Diag
<img width="1536" height="1024" alt="Image" src="https://github.com/user-attachments/assets/4f6bb370-b186-45e1-9a60-461374a76c0b" />
```
---

## 📁 Project Structure

```
nodejs-ci-cd-kubernetes/
├── .github/
│   └── workflows/
│       └── ci-cd.yml       # GitHub Actions pipeline
├── k8s/
│   ├── deployment.yaml     # Kubernetes Deployment manifest
│   └── service.yaml        # Kubernetes Service manifest
├── app.js                  # Node.js application entry point
├── package.json            # Node.js dependencies and scripts
└── Dockerfile              # Container image definition
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Application | Node.js + JavaScript | Backend API / web server |
| Containerization | Docker | Package the application |
| Orchestration | Kubernetes | Scale, manage, and deploy containers |
| CI/CD | GitHub Actions | Automate build → test → deploy |
| Registry | Docker Hub / GHCR | Store container images |

---

## ⚡ Getting Started

### Run with Docker

```bash
# Clone the repository
git clone https://github.com/Aijazkhan123/nodejs-ci-cd-kubernetes.git
cd nodejs-ci-cd-kubernetes

# Build Docker image
docker build -t nodejs-ci-cd-kubernetes .

# Run container
docker run -p 3000:3000 nodejs-ci-cd-kubernetes
```

Visit: **http://localhost:3000**

### Deploy to Kubernetes

```bash
# Apply the deployment and service manifests
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml

# Check status
kubectl get pods
kubectl get services
```

### Run Locally (without Docker)

```bash
npm install
node app.js
```

---

## ⚙️ CI/CD Pipeline

On every `git push`, the GitHub Actions workflow:

1. **Checks out** the source code
2. **Installs** Node.js dependencies with `npm install`
3. **Runs** tests with `npm test`
4. **Builds** a Docker image
5. **Pushes** the image to a container registry
6. **Deploys** to Kubernetes with `kubectl apply`

---

## 🧠 What I Learned

- Deploying containerized Node.js apps on Kubernetes
- Writing Kubernetes Deployment and Service manifests
- Building full end-to-end CI/CD pipelines with GitHub Actions
- Understanding pod scaling, rolling updates, and service networking in K8s

---

## 🗺️ Planned Improvements

- [ ] Add Kubernetes Horizontal Pod Autoscaler (HPA)
- [ ] Set up Ingress with NGINX for domain routing
- [ ] Add Helm chart for parameterized deployments
- [ ] Integrate secrets management with Kubernetes Secrets / Vault
- [ ] Add monitoring with Prometheus + Grafana

---

## 📜 License

MIT License — free to fork, learn from, and build upon.

---

`Node.js` · `Docker` · `Kubernetes` · `GitHub Actions` · `CI/CD` · `DevOps` · `Container Orchestration`
