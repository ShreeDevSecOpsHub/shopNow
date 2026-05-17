

## ShopNow - MERN Stack Kubernetes & Helm Deployment

A complete **production-grade** deployment of a MERN (MongoDB, Express, React, Node.js) e-commerce application using **Kubernetes**, **Helm Charts**, and **Jenkins CI/CD**.

---

## 📋 Project Overview

**ShopNow** is a full-stack e-commerce platform consisting of:

- **Frontend** → React.js (Customer-facing app)
- **Admin Dashboard** → React.js
- **Backend** → Node.js + Express.js
- **Database** → MongoDB

This repository contains Kubernetes manifests, Helm charts, and Jenkins pipeline for automated deployment.

---

## 🗂 Project Structure

```bash
shopNow/
├── frontend/                  # React Customer Application
├── admin/                     # React Admin Dashboard
├── backend/                   # Node.js Express Backend
├── kubernetes/
│   ├── k8s-manifests/         # Raw Kubernetes YAML files
│   └── helm/
│       └── charts/            # Helm Charts (frontend, backend, admin, mongodb)
├── jenkins/
│   └── Jenkinsfile            # CI/CD Pipeline
├── Dockerfile.*               # Dockerfiles for each service
└── README.md
```

---

## 🚀 Features Implemented

- Horizontal Pod Autoscaling (HPA)
- Persistent storage for MongoDB using StatefulSet + PVC
- Path-based Ingress routing
- Resource requests & limits
- Environment configuration via Helm
- Automated CI/CD with Jenkins + AWS ECR

---

## 📦 Helm Charts

Helm charts are located at `kubernetes/helm/charts/`

### Installation Commands

```bash
# Create Namespace
kubectl create namespace shopnow-demo

# Install using Helm
helm upgrade --install mongodb kubernetes/helm/charts/mongodb --namespace shopnow-demo
helm upgrade --install backend kubernetes/helm/charts/backend --namespace shopnow-demo
helm upgrade --install frontend kubernetes/helm/charts/frontend --namespace shopnow-demo
helm upgrade --install admin kubernetes/helm/charts/admin --namespace shopnow-demo
```

---

## ⚙️ Kubernetes Manifests

Raw YAML files are available in `kubernetes/k8s-manifests/`

- Deployments
- Services
- Ingress (with path routing: `/`, `/admin`, `/api`)
- StatefulSet (MongoDB)
- Secrets & ConfigMaps
- HorizontalPodAutoscaler

---

## 🔄 Jenkins CI/CD Pipeline

Full pipeline available at `jenkins/Jenkinsfile`

**Pipeline Stages:**
1. Git Checkout
2. Docker Build (Frontend, Admin, Backend)
3. Push images to AWS ECR
4. Deploy/Update application using Helm

---

## 🛠 Setup & Personalization

1. Replace all occurrences of placeholder names with your details:
   - Your username
   - AWS Account ID
   - AWS Region
   - ECR Repository paths

2. Update Ingress host/path as per your cluster setup.

3. Create Kubernetes Secrets for MongoDB credentials.

4. Install prerequisites:
   - NGINX Ingress Controller
   - Metrics Server
   - Storage Class

---

## 📌 Challenges Faced & Solutions

| Challenge                        | Solution                                      |
|----------------------------------|-----------------------------------------------|
| Multi-user cluster conflicts     | Personalized Ingress paths (`/<username>`)    |
| Database persistence             | StatefulSet + PVC                             |
| Image versioning                 | Jenkins `BUILD_NUMBER` as image tag          |
| Configuration management         | Helm `values.yaml` + `--set` overrides       |
| Scaling & Resource Management    | HPA + Resource Requests/Limits                |

---

## 🧪 Local Testing

- Use **Minikube** or **Kind**
- Build images locally and load them
- Apply manifests or Helm charts

---

## 🛠 Technologies Used

- **Frontend**: React.js
- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Container**: Docker
- **Orchestration**: Kubernetes
- **Package Manager**: Helm
- **CI/CD**: Jenkins
- **Registry**: AWS ECR
- **Cluster**: AWS EKS

---

## 📄 License

This project is created for **DevOps Assignment** purposes.

---

**Made with ❤️ for Learning Kubernetes & DevOps**

**Your Name**  
**GitHub**: [https://github.com/YOUR-USERNAME](https://github.com/YOUR-USERNAME)
```

---

**Done!** Just copy everything from the code block above and save it as `README.md`.

Would you also like me to create:
- A separate detailed `kubernetes/README.md`
- The full `Jenkinsfile`
- Sample `values.yaml` for Helm

Let me know!
