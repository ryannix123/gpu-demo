# Flask GPU Demo - GitOps Deployment with ArgoCD

This repository contains a GitOps-friendly deployment of the [flask-gpu-demo](https://quay.io/repository/ryan_nix/flask-gpu-demo) app using OpenShift and ArgoCD. Its target use case is Red Hat Advanced Cluster Management (RHACM)

## 📦 Components

- Flask app running with GPU support
- Secure OpenShift Route
- Liveness and readiness probes
- ArgoCD Application manifest

## 🚀 Getting Started

1. Fork this repo to your GitHub.
2. Update `argocd/application.yaml`:
   - Set `repoURL` to your GitHub repo URL.
3. Apply the ArgoCD `Application` manifest to your OpenShift GitOps instance:

   ```bash
   oc apply -f argocd/application.yaml
   ```

4. ArgoCD will automatically create the namespace and deploy the app.

## 💻 Prerequisites

- OpenShift with NVIDIA GPU support
- ArgoCD installed (via Operator or manually)
- GPU Operator installed and configured
- Cluster must allow Route creation

## 📋 Notes

- The app expects a `/healthz` endpoint; update probes if needed.
