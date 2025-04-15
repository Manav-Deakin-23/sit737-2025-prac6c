# sit737-2025-prac6c
 
# 🧪 SIT737 – Practical 6.2C – Interacting with Deployed Kubernetes App

## 📘 Overview

In this task, we interact with a Node.js calculator application that has already been deployed to a Kubernetes cluster (as part of Task 6.1P). The goal is to verify that the application is running properly and can be accessed via the Kubernetes service using port-forwarding.

---

## ✅ Prerequisites

Ensure the following are installed and configured:
- Docker Desktop with Kubernetes enabled
- Node.js
- kubectl CLI
- A deployed Kubernetes application (from Task 6.1P)
- Docker image (e.g. `manav0226/calculator:v2`)
- Git & Visual Studio Code

---

## 🚀 Steps Performed

### 1. 🔍 Verify Pods and Services

Check that the application pods and services are running correctly:

```bash
kubectl get pods
kubectl get services

## 2. 🔀 Port-Forward the Service
Forward local port 8080 to the Kubernetes service port:

kubectl port-forward service/calculator-service 8080:80

3. 🌐 Access the Application
Open a browser and navigate to:

http://localhost:8080

 🛠 Update the Application (Optional)
To test version updates:

Modify server.js (e.g., change heading text)

Build and push new image:

docker build -t manav0226/calculator:v3 .
docker push manav0226/calculator:v3
Update deployment.yaml with the new image tag:

image: manav0226/calculator:v3
Reapply deployment:

kubectl apply -f deployment.yaml

🛑 Stop the Application
To stop the forwarded service, press Ctrl + C in the terminal.
