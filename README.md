# DevOps Microservices Demo (Minikube + Helm)

A complete Kubernetes-based microservices e-commerce demo deployed locally using **Minikube**, **Helm**, and **Docker**. This project demonstrates DevOps best practices in container orchestration, service packaging, and local development environment setup.

---

## Project Stack

- Kubernetes (via Minikube)
- Docker
- Helm
- NGINX Ingress Controller
- GitHub for version control

---

## Microservices Overview

- `frontend`
- `cartservice`
- `checkoutservice`
- `productcatalogservice`
- `recommendationservice`
- `currencyservice`
- `paymentservice`
- `emailservice`
- `shippingservice`
- `adservice`
- `loadgenerator` (traffic simulation)

---

## Prerequisites

Make sure the following tools are installed.

1: Install Docker

2: Install git

3: Install Minikube

4: Install Helm

5: Install kubectl

---

## Local Deployment Steps

### 1. Start Minikube

```bash
minikube start --cpus=4 --memory 4096 --disk-size 32g
```

### 2. Enable Ingress

```bash
minikube addons enable ingress
```

Wait for the ingress controller to be fully running:

```bash
kubectl get pods -n ingress-nginx
```

### 3. Clone the Repository

```bash
git clone https://github.com/Ahmedtech2003/devops-microservices-k8s.git
cd devops-microservices-k8s
```

### 4. Deploy Using Helm

```bash
cd helm-chart
helm install online-boutique ./
```

Verify everything is running:

```bash
kubectl get pods
kubectl get svc
```

### 5. Access the Application

```bash
minikube service frontend
```

This will open the browser with the frontend UI.

---

## Clean Up

To remove everything:

```bash
helm uninstall online-boutique
minikube stop
minikube delete
```

---

## Author

**Muhammad Ahmed **  
DevOps Engineer  
GitHub: [Ahmedtech2003](https://github.com/Ahmedtech2003)  
Email: ahmedtechwork1@gmail.com

