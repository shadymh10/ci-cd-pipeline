# 🚀 CI/CD Pipeline with Docker Hub, Kubernetes & ArgoCD (GitOps)

This repository demonstrates a complete DevOps workflow including:

- Docker image building
- Image push to Docker Hub
- Kubernetes deployment using manifests + Kustomize
- CI/CD automation with GitHub Actions
- GitOps deployment using ArgoCD

This project shows how a simple NGINX web application can be fully automated from code commit → container build → deployment on Kubernetes.

---

## 📁 Repository Structure


│
├── helloapp/ # Application code
│ ├── index.html
│ └── Dockerfile
│
├── k8s/ # Kubernetes manifests
│ ├── deployment.yaml
│ ├── service.yaml
│ └── kustomization.yaml
│
└── .github/workflows/ # CI/CD pipeline
└── build-and-deploy.yml


---

## 🐳 Docker Hub Setup

### Step 1 — Create Docker Hub Account
Go to [Docker Hub](https://hub.docker.com), register and verify email.

### Step 2 — Create Repository
Example:


Name: <dockerhub-name>/helloapp
Visibility: Public

### Step 3 — Create Docker Hub Access Token


Account Settings → Security → New Access Token

Name it: `github-ci-token` and copy the token.

### Step 4 — Add GitHub Secrets
Go to GitHub → Repo Settings → Secrets → Actions → New Secret

| Secret Name | Value |
|-------------|-------|
| DOCKERHUB_USERNAME | your DockerHub username |
| DOCKERHUB_TOKEN    | Docker Hub token created |

---

## 🧱 Application (helloapp)

### index.html
