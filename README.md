# Azure GitOps Platform

This is a simulation of a production-grade GitOps architecture built on Azure.

It separates application delivery and platform infrastructure using real CI/CD pipelines, ArgoCD App-of-Apps pattern, and a RAG-based FastAPI service.
The system is built to simulate how senior engineers orchestrate versioned deploys, platform control planes, and modular Kubernetes environments in the real world.
Everything runs on AKS, integrated with Azure OpenAI for retrieval-augmented responses.

- ✅ **App Code**: RAG-based FastAPI backend (optionally with a frontend)
- ✅ **Delivery Pipelines**: Builds Docker images + Helm charts
- ✅ **Deployment Infra**: GitOps with ArgoCD + App-of-Apps pattern
- ✅ **Cloud-Native**: Runs on Azure Kubernetes Service (AKS), integrates Azure OpenAI

---

## 📦 Repositories

| Repo | Purpose |
|------|---------|
| [`rag-app`](https://github.com/dhayv/azure-rag-app) | Application source code, Helm chart, CI pipelines |
| [`rag-infra`](https://github.com/dhayv/azure-rag-infra) | ArgoCD manifests, GitOps controller, App-of-Apps |

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

Most GitOps walkthroughs break under real-world constraints. They mix app code with infra, hardcode secrets, or ignore modular deploy patterns.
This project pressure-tests separation of delivery pipelines and platform orchestration using:

- 🧱 2 monorepos for clean team boundaries (`app`, `infra`)
- 🔁 Chart versioning + OCI pushes for rollback control
- 🔁 ArgoCD App-of-Apps to simulate platform-scale deployment logic
- 📈 CI-built Helm charts + Docker images for immutable delivery

It’s not a sandbox. It’s a prototype for production-grade reproducibility.

---

## 🔗 Coming Soon

- ✅ Full CI/CD YAMLs
- ✅ Live demo link / screenshots
- ✅ RAG documentation workflow

