# Node.js CI/CD with Kubernetes

[![Node.js](https://img.shields.io/badge/Node.js-JavaScript-339933?logo=node.js)](https://nodejs.org) [![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestration-326CE5?logo=kubernetes)](https://kubernetes.io) [![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker)](https://docker.com) [![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI%2FCD-2088FF?logo=github-actions)](https://github.com/features/actions) [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> A Node.js application with a fully automated CI/CD pipeline that builds a Docker image and deploys it to a Kubernetes cluster — production-grade delivery from a single git push.

---

## CI/CD + Kubernetes Pipeline

<svg width="900" height="380" viewBox="0 0 900 380" xmlns="http://www.w3.org/2000/svg" font-family="'Segoe UI', system-ui, sans-serif">
  <defs>
    <marker id="arr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse">
      <path d="M1 1L9 5L1 9" fill="none" stroke="#64748b" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </marker>
    <filter id="shadow" x="-10%" y="-10%" width="120%" height="130%">
      <feDropShadow dx="0" dy="2" stdDeviation="3" flood-color="#0001"/>
    </filter>
  </defs>

  <rect width="900" height="380" fill="#f8fafc" rx="16"/>

  <text x="450" y="36" text-anchor="middle" font-size="15" font-weight="700" fill="#0f172a" letter-spacing="-0.3">CI/CD + Kubernetes Pipeline — nodejs-ci-cd-kubernetes</text>
  <text x="450" y="54" text-anchor="middle" font-size="11" fill="#94a3b8">Git push → Build → Push to Registry → Deploy to Kubernetes</text>

  <!-- Row 1: CI steps -->
  <!-- Step 1 -->
  <g filter="url(#shadow)">
    <rect x="30" y="80" width="120" height="85" rx="10" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="30" y="80" width="120" height="6" rx="3" fill="#6366f1"/>
  <rect x="30" y="83" width="120" height="3" fill="#6366f1"/>
  <text x="90" y="118" text-anchor="middle" font-size="20">💻</text>
  <text x="90" y="138" text-anchor="middle" font-size="11" font-weight="600" fill="#1e293b">Git Push</text>
  <text x="90" y="153" text-anchor="middle" font-size="9" fill="#64748b">main branch</text>

  <line x1="152" y1="122" x2="172" y2="122" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>

  <!-- Step 2 -->
  <g filter="url(#shadow)">
    <rect x="174" y="80" width="120" height="85" rx="10" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="174" y="80" width="120" height="6" rx="3" fill="#2088ff"/>
  <rect x="174" y="83" width="120" height="3" fill="#2088ff"/>
  <text x="234" y="118" text-anchor="middle" font-size="20">⚙️</text>
  <text x="234" y="138" text-anchor="middle" font-size="11" font-weight="600" fill="#1e293b">GitHub Actions</text>
  <text x="234" y="153" text-anchor="middle" font-size="9" fill="#64748b">Workflow triggered</text>

  <line x1="296" y1="122" x2="316" y2="122" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>

  <!-- Step 3 -->
  <g filter="url(#shadow)">
    <rect x="318" y="80" width="120" height="85" rx="10" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="318" y="80" width="120" height="6" rx="3" fill="#2496ed"/>
  <rect x="318" y="83" width="120" height="3" fill="#2496ed"/>
  <text x="378" y="118" text-anchor="middle" font-size="20">🐳</text>
  <text x="378" y="138" text-anchor="middle" font-size="11" font-weight="600" fill="#1e293b">Docker Build</text>
  <text x="378" y="153" text-anchor="middle" font-size="9" fill="#64748b">Image built</text>

  <line x1="440" y1="122" x2="460" y2="122" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>

  <!-- Step 4 -->
  <g filter="url(#shadow)">
    <rect x="462" y="80" width="120" height="85" rx="10" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="462" y="80" width="120" height="6" rx="3" fill="#0ea5e9"/>
  <rect x="462" y="83" width="120" height="3" fill="#0ea5e9"/>
  <text x="522" y="118" text-anchor="middle" font-size="20">📤</text>
  <text x="522" y="138" text-anchor="middle" font-size="11" font-weight="600" fill="#1e293b">Push Registry</text>
  <text x="522" y="153" text-anchor="middle" font-size="9" fill="#64748b">Docker Hub</text>

  <line x1="584" y1="122" x2="604" y2="122" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>

  <!-- Step 5 -->
  <g filter="url(#shadow)">
    <rect x="606" y="80" width="120" height="85" rx="10" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="606" y="80" width="120" height="6" rx="3" fill="#326ce5"/>
  <rect x="606" y="83" width="120" height="3" fill="#326ce5"/>
  <text x="666" y="118" text-anchor="middle" font-size="20">☸️</text>
  <text x="666" y="138" text-anchor="middle" font-size="11" font-weight="600" fill="#1e293b">kubectl apply</text>
  <text x="666" y="153" text-anchor="middle" font-size="9" fill="#64748b">K8s updated</text>

  <line x1="728" y1="122" x2="748" y2="122" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>

  <!-- Step 6 -->
  <g filter="url(#shadow)">
    <rect x="750" y="80" width="120" height="85" rx="10" fill="#fff" stroke="#e2e8f0" stroke-width="1.5"/>
  </g>
  <rect x="750" y="80" width="120" height="6" rx="3" fill="#22c55e"/>
  <rect x="750" y="83" width="120" height="3" fill="#22c55e"/>
  <text x="810" y="118" text-anchor="middle" font-size="20">✅</text>
  <text x="810" y="138" text-anchor="middle" font-size="11" font-weight="600" fill="#1e293b">App Live</text>
  <text x="810" y="153" text-anchor="middle" font-size="9" fill="#64748b">Rolling update done</text>

  <!-- Kubernetes cluster diagram -->
  <rect x="30" y="200" width="840" height="140" rx="12" fill="#eff6ff" stroke="#326ce5" stroke-width="1.5" stroke-dasharray="6 4"/>
  <text x="50" y="222" font-size="11" font-weight="700" fill="#326ce5">☸️  Kubernetes Cluster</text>

  <!-- Deployment box -->
  <rect x="60" y="232" width="200" height="90" rx="8" fill="#fff" stroke="#326ce5" stroke-width="1" filter="url(#shadow)"/>
  <text x="160" y="253" text-anchor="middle" font-size="11" font-weight="700" fill="#1e293b">Deployment</text>
  <text x="160" y="270" text-anchor="middle" font-size="10" fill="#64748b">replicas: 2</text>
  <!-- Pod 1 -->
  <rect x="75" y="278" width="75" height="34" rx="6" fill="#dbeafe" stroke="#93c5fd" stroke-width="1"/>
  <text x="112" y="298" text-anchor="middle" font-size="10" fill="#1d4ed8">Pod 1</text>
  <text x="112" y="308" text-anchor="middle" font-size="9" fill="#3b82f6">node:app</text>
  <!-- Pod 2 -->
  <rect x="162" y="278" width="75" height="34" rx="6" fill="#dbeafe" stroke="#93c5fd" stroke-width="1"/>
  <text x="199" y="298" text-anchor="middle" font-size="10" fill="#1d4ed8">Pod 2</text>
  <text x="199" y="308" text-anchor="middle" font-size="9" fill="#3b82f6">node:app</text>

  <!-- Arrow -->
  <line x1="262" y1="292" x2="318" y2="292" stroke="#326ce5" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>

  <!-- Service box -->
  <rect x="320" y="232" width="180" height="90" rx="8" fill="#fff" stroke="#7c3aed" stroke-width="1" filter="url(#shadow)"/>
  <text x="410" y="253" text-anchor="middle" font-size="11" font-weight="700" fill="#1e293b">Service</text>
  <text x="410" y="270" text-anchor="middle" font-size="10" fill="#64748b">type: NodePort</text>
  <text x="410" y="286" text-anchor="middle" font-size="10" fill="#64748b">port: 80 → 3000</text>
  <text x="410" y="302" text-anchor="middle" font-size="10" fill="#64748b">nodePort: 30080</text>

  <!-- Arrow -->
  <line x1="502" y1="292" x2="558" y2="292" stroke="#326ce5" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>

  <!-- Ingress box -->
  <rect x="560" y="232" width="180" height="90" rx="8" fill="#fff" stroke="#f59e0b" stroke-width="1" filter="url(#shadow)"/>
  <text x="650" y="253" text-anchor="middle" font-size="11" font-weight="700" fill="#1e293b">Ingress</text>
  <text x="650" y="270" text-anchor="middle" font-size="10" fill="#64748b">External HTTP routing</text>
  <text x="650" y="286" text-anchor="middle" font-size="10" fill="#64748b">routes to Service</text>
  <text x="650" y="302" text-anchor="middle" font-size="10" fill="#64748b">NodeIP:30080</text>

  <!-- External user -->
  <text x="800" y="278" text-anchor="middle" font-size="20">👤</text>
  <text x="800" y="298" text-anchor="middle" font-size="10" fill="#64748b">User</text>
  <line x1="742" y1="277" x2="775" y2="277" stroke="#64748b" stroke-width="1.5" marker-end="url(#arr)" stroke-dasharray="4 3"/>

  <!-- Bottom -->
  <rect x="30" y="355" width="840" height="0" rx="8" fill="#f1f5f9"/>
</svg>

---

## Project Structure

<svg width="900" height="340" viewBox="0 0 900 340" xmlns="http://www.w3.org/2000/svg" font-family="'Segoe UI', system-ui, sans-serif">
  <defs>
    <filter id="shadow" x="-10%" y="-10%" width="120%" height="130%">
      <feDropShadow dx="0" dy="2" stdDeviation="3" flood-color="#0001"/>
    </filter>
  </defs>

  <rect width="900" height="340" fill="#0f172a" rx="16"/>
  <text x="450" y="38" text-anchor="middle" font-size="15" font-weight="700" fill="#f1f5f9" letter-spacing="-0.3">Project Structure — nodejs-ci-cd-kubernetes</text>

  <!-- File tree -->
  <rect x="40" y="60" width="280" height="250" rx="10" fill="#1e293b" stroke="#334155" stroke-width="1"/>
  <text x="60" y="88" font-size="12" font-weight="700" fill="#94a3b8" font-family="monospace">nodejs-ci-cd-kubernetes/</text>

  <line x1="72" y1="100" x2="72" y2="270" stroke="#334155" stroke-width="1"/>

  <line x1="72" y1="112" x2="88" y2="112" stroke="#334155" stroke-width="1"/>
  <text x="94" y="117" font-size="11" fill="#7dd3fc" font-family="monospace">📁 .github/workflows/</text>

  <line x1="100" y1="124" x2="100" y2="136" stroke="#334155" stroke-width="1"/>
  <line x1="100" y1="136" x2="116" y2="136" stroke="#334155" stroke-width="1"/>
  <text x="122" y="141" font-size="11" fill="#fbbf24" font-family="monospace">ci-cd.yml</text>

  <line x1="72" y1="155" x2="88" y2="155" stroke="#334155" stroke-width="1"/>
  <text x="94" y="160" font-size="11" fill="#7dd3fc" font-family="monospace">📁 k8s/</text>

  <line x1="100" y1="168" x2="100" y2="192" stroke="#334155" stroke-width="1"/>
  <line x1="100" y1="172" x2="116" y2="172" stroke="#334155" stroke-width="1"/>
  <text x="122" y="177" font-size="11" fill="#93c5fd" font-family="monospace">deployment.yaml</text>

  <line x1="100" y1="192" x2="116" y2="192" stroke="#334155" stroke-width="1"/>
  <text x="122" y="197" font-size="11" fill="#a5b4fc" font-family="monospace">service.yaml</text>

  <line x1="72" y1="212" x2="88" y2="212" stroke="#334155" stroke-width="1"/>
  <text x="94" y="217" font-size="11" fill="#86efac" font-family="monospace">📦 app.js</text>

  <line x1="72" y1="234" x2="88" y2="234" stroke="#334155" stroke-width="1"/>
  <text x="94" y="239" font-size="11" fill="#7dd3fc" font-family="monospace">🐳 Dockerfile</text>

  <line x1="72" y1="256" x2="88" y2="256" stroke="#334155" stroke-width="1"/>
  <text x="94" y="261" font-size="11" fill="#c4b5fd" font-family="monospace">📄 package.json</text>

  <!-- Detail cards — 2 columns -->
  <rect x="360" y="60" width="240" height="78" rx="8" fill="#1e293b" stroke="#fbbf24" stroke-width="1.5"/>
  <text x="376" y="80" font-size="11" font-weight="700" fill="#fbbf24">⚙️ .github/workflows/ci-cd.yml</text>
  <text x="376" y="96" font-size="10" fill="#94a3b8">GitHub Actions pipeline. Builds Docker</text>
  <text x="376" y="110" font-size="10" fill="#94a3b8">image, pushes to registry, deploys to K8s.</text>
  <text x="376" y="126" font-size="10" fill="#64748b">on: push → build → push → kubectl apply</text>

  <rect x="360" y="152" width="240" height="78" rx="8" fill="#1e293b" stroke="#93c5fd" stroke-width="1.5"/>
  <text x="376" y="172" font-size="11" font-weight="700" fill="#93c5fd">☸️ k8s/deployment.yaml</text>
  <text x="376" y="188" font-size="10" fill="#94a3b8">Defines Deployment with 2 replicas.</text>
  <text x="376" y="202" font-size="10" fill="#94a3b8">Manages rolling updates automatically.</text>
  <text x="376" y="218" font-size="10" fill="#64748b">replicas: 2  ·  image: nodejs-app</text>

  <rect x="360" y="244" width="240" height="66" rx="8" fill="#1e293b" stroke="#a5b4fc" stroke-width="1.5"/>
  <text x="376" y="264" font-size="11" font-weight="700" fill="#a5b4fc">☸️ k8s/service.yaml</text>
  <text x="376" y="280" font-size="10" fill="#94a3b8">Exposes pods via NodePort.</text>
  <text x="376" y="294" font-size="10" fill="#64748b">port: 80 → targetPort: 3000</text>

  <rect x="620" y="60" width="240" height="78" rx="8" fill="#1e293b" stroke="#86efac" stroke-width="1.5"/>
  <text x="636" y="80" font-size="11" font-weight="700" fill="#86efac">📦 app.js</text>
  <text x="636" y="96" font-size="10" fill="#94a3b8">Node.js web application server.</text>
  <text x="636" y="110" font-size="10" fill="#94a3b8">Handles HTTP requests on port 3000.</text>
  <text x="636" y="126" font-size="10" fill="#64748b">GET /  ·  JSON responses</text>

  <rect x="620" y="152" width="240" height="78" rx="8" fill="#1e293b" stroke="#7dd3fc" stroke-width="1.5"/>
  <text x="636" y="172" font-size="11" font-weight="700" fill="#7dd3fc">🐳 Dockerfile</text>
  <text x="636" y="188" font-size="10" fill="#94a3b8">Containerizes Node.js app using</text>
  <text x="636" y="202" font-size="10" fill="#94a3b8">node:alpine base image.</text>
  <text x="636" y="218" font-size="10" fill="#64748b">npm install → COPY → CMD node app.js</text>

  <rect x="620" y="244" width="240" height="66" rx="8" fill="#1e293b" stroke="#c4b5fd" stroke-width="1.5"/>
  <text x="636" y="264" font-size="11" font-weight="700" fill="#c4b5fd">📄 package.json</text>
  <text x="636" y="280" font-size="10" fill="#94a3b8">Node.js project manifest and deps.</text>
  <text x="636" y="294" font-size="10" fill="#64748b">name, version, scripts, dependencies</text>

  <!-- Bottom bar -->
  <rect x="40" y="298" width="820" height="0" rx="8" fill="#1e293b"/>
</svg>

---

## What I Built

I built and automated a complete cloud-native delivery pipeline for a Node.js application. From a single `git push`, the GitHub Actions pipeline builds a Docker image, pushes it to a container registry, and deploys it to a Kubernetes cluster using declarative manifests.

This project demonstrates my ability to:
- Write and manage **Kubernetes Deployment and Service manifests**
- Build automated **CI/CD pipelines** that deploy to container orchestration platforms
- Containerize Node.js applications with **Docker**
- Apply **GitOps principles** — infrastructure and deployment defined as code
- Work with the core tools used in modern cloud-native engineering teams

---

## Tech Stack

| Technology | Role |
|---|---|
| Node.js | Application runtime |
| Docker | Container image build |
| Kubernetes | Container orchestration and scaling |
| GitHub Actions | CI/CD pipeline automation |

---

## How the Pipeline Works

```
Git Push to main
    ↓
GitHub Actions triggered
    ↓
Docker image built and pushed to registry
    ↓
kubectl apply — Kubernetes Deployment updated
    ↓
Rolling update — zero downtime ✅
```

**Kubernetes resources used:**
- `Deployment` — manages replica count, rolling updates, and self-healing
- `Service` — exposes the app with a stable DNS name and load balancing across pods

---

## File Structure

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

## Run It Locally

**With Docker:**
```bash
git clone https://github.com/Aijazkhan123/nodejs-ci-cd-kubernetes.git
cd nodejs-ci-cd-kubernetes
docker build -t nodejs-k8s-app .
docker run -p 3000:3000 nodejs-k8s-app
```

**Deploy to Kubernetes:**
```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl get pods
kubectl get services
```

**Without Docker:**
```bash
npm install
node app.js
```

---

## Planned Improvements

- [ ] Add Helm chart for parameterized deployments
- [ ] Integrate container image scanning with Trivy
- [ ] Configure Horizontal Pod Autoscaler (HPA)
- [ ] Add Prometheus + Grafana monitoring stack

---

## Skills Demonstrated

`Kubernetes` · `Docker` · `CI/CD` · `GitHub Actions` · `Node.js` · `GitOps` · `Container Orchestration` · `YAML Manifests` · `Rolling Deployments`
