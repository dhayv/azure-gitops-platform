# Azure GitOps Platform

This project simulates a **real-world GitOps deployment pipeline on Azure**, featuring:

- ✅ **App Code**: RAG-based FastAPI backend (optionally with a frontend)
- ✅ **Delivery Pipelines**: Builds Docker images + Helm charts
- ✅ **Deployment Infra**: GitOps with ArgoCD + App-of-Apps pattern
- ✅ **Cloud-Native**: Runs on Azure Kubernetes Service (AKS), integrates Azure OpenAI

---

## 📦 Repositories

| Repo | Purpose |
|------|---------|
| [`rag-app`](https://github.com/YOUR_USERNAME/rag-app) | Application source code, Helm chart, CI pipelines |
| [`rag-infra`](https://github.com/YOUR_USERNAME/rag-infra) | ArgoCD manifests, GitOps controller, App-of-Apps |

---

## 🧠 Architecture Overview

![GitOps Flow Diagram](link-to-your-diagram.png)

1. Code pushed to `rag-app`
2. CI builds:
   - Docker image → Azure Container Registry (ACR)
   - Helm chart → OCI registry
3. `rag-infra` ArgoCD `Application` points to the chart version
4. ArgoCD syncs the new version into AKS

---

## 🔧 Tech Stack

- **Cloud**: Azure Kubernetes Service (AKS), Azure Container Registry
- **App**: FastAPI, OpenAI (RAG), Docker, Helm
- **Infra**: ArgoCD, App-of-Apps pattern, GitHub Actions
- **GitOps**: Chart versioning + declarative K8s deployment

---

## 💡 Why This Project?

Most GitOps tutorials are toy examples or mix concerns. This repo simulates **how real engineering orgs separate app and infra pipelines**, using:

- 2 monorepos (`app`, `infra`)
- GitOps deployment control
- Chart versioning strategy
- ArgoCD Application modularity

---

## 🔗 Coming Soon

- ✅ Full CI/CD YAMLs
- ✅ Live demo link / screenshots
- ✅ RAG documentation workflow

