# E-Commerce Platform

## 🛠 Project Structure (Monorepo Style)

### Node.js Microservices App

```bash
E-Commerce-Platform-with-Microservices-Architecture/
├── product-service/
│   ├── Dockerfile
│   ├── src/
│   └── package.json
├── cart-service/
│   ├── Dockerfile
│   ├── src/
│   └── package.json
├── order-service/
│   ├── Dockerfile
│   ├── src/
│   └── package.json
├── helm-charts/
│   ├── product/
│   ├── cart/
│   └── order/
├── k8s/
│   ├── terraform/
│   └── argocd/
├── .github/
│   └── workflows/
│       └── ci-cd.yml
└── README.md
```

## Setting up the project

- Select a location to save the project on your computer, I shall be saving the project in the `Documents` directory for the purpose of this project
- Inside the `Documents` directory run `mkdir E-Commerce-Platform-with-Microservices-Architecture`
- Then `cd E-Commerce-Platform-with-Microservices-Architecture`
- And `mkdir product-service order-service cart-service`
  This will create the separate services in the root folder
- Lets also create the github-actions folder for our CICD by running `mkdir -p .github/workflows`
- Finally for the folder strucuture we would create a folder for our kubernets and infrastructure tools like so:
- `mkdir k8s` for kubernetes related documents and manifests(kubernetes and argocd)
- `mkidir infrastructure` for terramform modules
- We would also need a README.md for the documentaion of our project for clear understanding of our implementation and future references

## Microservices system consisting of three independent services:

- 🛒 Cart Service
- 📦 Product Service
- 📃 Order Service

Each service is containerized, deployed to Kubernetes using Helm Charts, and managed through CI/CD pipelines powered by GitHub Actions and ArgoCD with infrastructure provisioned by Terraform.
NB: We would be focusing on the Devops side of things in this project

---

## 🧱 Architecture Overview

- **Language**: Node.js (Express.js)
- **Design**: Microservices
- **Service-to-Service Communication**: REST API (HTTP)
- **Containerization**: Docker
- **Orchestration**: Kubernetes
- **Deployment**: Helm + ArgoCD
- **CI/CD**: GitHub Actions
- **Infrastructure as Code**: Terraform
- **Secrets Management**: Kubernetes Secrets / External Secrets (optional)

---

## 📦 Services

### 1. Product Service

- CRUD operations for products.
- Endpoints:
  - `GET /products`
  - `POST /products`
  - `GET /products/:id`
  - `PUT /products/:id`
  - `DELETE /products/:id`

### 2. Cart Service

- Add/remove products to/from cart.
- Endpoints:
  - `GET /cart/:userId`
  - `POST /cart/:userId/add`
  - `POST /cart/:userId/remove`

### 3. Order Service

- Places orders from cart.
- Endpoints:
  - `POST /orders`
  - `GET /orders/:userId`

---

## 🚀 Local Development

### Requirements

- Node.js v18+
- Docker & Docker Compose
- Minikube (for local Kubernetes)
- Helm

### Setup

```bash
# Clone repo
git clone git@github.com:kelomo2502/E-Commerce-Platform-with-Microservices-Architecture.git
cd E-Commerce-Platform-with-Microservices-Architecturepp

# Install service dependencies
cd product-service && npm install
cd ../cart-service && npm install
cd ../order-service && npm install
