# 🚀 AI based Observability with Honeycomb, OpenTelemetry & MCP

## 📌 Project Overview

This project demonstrates an **end-to-end observability pipeline** using **Kubernetes (Minikube)**, **OpenTelemetry**, **Honeycomb**, and **MCP (Model Context Protocol)**, with AI-assisted insights via **GitHub Copilot**.

The goal is to:

* Deploy a sample microservice (**HotROD**) on Kubernetes
* Collect distributed traces using **OpenTelemetry Collector**
* Export telemetry data to **Honeycomb** for observability
* Connect **Honeycomb MCP Server** to enable AI-powered observability insights
* Query and analyze traces directly from **GitHub Copilot in VS Code**

---

## 🏗️ Architecture Overview

**Flow:**

1. **Minikube Cluster** runs locally
2. **HotROD Demo Application** generates distributed traces
3. **OpenTelemetry Collector** receives OTLP traces
4. **Honeycomb** stores and visualizes telemetry data
5. **Honeycomb MCP Server** exposes observability context
6. **GitHub Copilot (VS Code)** consumes MCP context for intelligent insights

```text
HotROD App
   ↓ (OTLP gRPC)
OpenTelemetry Collector
   ↓
Honeycomb.io
   ↓
Honeycomb MCP Server
   ↓
GitHub Copilot (VS Code)
```

---

## 🧰 Technologies Used

* **Kubernetes** – Container orchestration
* **Minikube** – Local Kubernetes cluster
* **Docker** – Container runtime
* **OpenTelemetry** – Distributed tracing & telemetry
* **Honeycomb** – Observability platform
* **MCP (Model Context Protocol)** – AI observability integration
* **GitHub Copilot** – AI-powered development assistant
* **Jaeger HotROD** – Sample microservices demo app

---

## ⚙️ Setup Steps

### 1️⃣ Start Minikube

```bash
minikube start
```

---

### 2️⃣ Deploy Kubernetes Resources

Apply the YAML file which creates:

* `observability` namespace
* OpenTelemetry Collector
* HotROD demo application
* Required services

```bash
kubectl apply -f deployment.yaml
```

---

### 3️⃣ Verify Pods

```bash
kubectl get pods -n observability
```

---

### 4️⃣ Access HotROD UI

```bash
kubectl port-forward -n observability deploy/demo-app 8080:8080
```

Open browser:

```
http://localhost:8080
```

Generate traffic to produce traces.

---

### 5️⃣ Confirm Traces in Honeycomb

* Log in to **Honeycomb UI**
* Dataset is auto-created via API
* Verify incoming traces from `hotrod-demo`

---

### 6️⃣ Connect Honeycomb MCP Server

* Use Honeycomb MCP Server URL
* Configure MCP connection in **VS Code**
* Authenticate using Honeycomb API key

---

### 7️⃣ Use GitHub Copilot for Observability

With MCP connected, GitHub Copilot can:

* Query live traces
* Explain latency issues
* Analyze service behavior
* Assist in debugging using real telemetry

---

## ✨ Key Features

* ✅ Real-time distributed tracing
* ✅ Kubernetes-native observability
* ✅ Vendor-neutral OpenTelemetry pipeline
* ✅ AI-powered insights using MCP
* ✅ Developer-friendly observability via VS Code

---

## 📊 Example Use Cases

* Detect high-latency services
* Understand request flow across microservices
* Debug production-like issues locally
* Ask Copilot questions like:

  * *"Why is this request slow?"*
  * *"Show errors in last 5 minutes"*

---

⭐ *If you like this project, consider giving it a star!*
