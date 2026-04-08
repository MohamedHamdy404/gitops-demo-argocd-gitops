# Argo CD GitOps Demo - Central Repository

This repository follows the **App-of-Apps** pattern to manage multiple projects across different environments (dev, sit, prod) using Argo CD.

## Structure

- `bootstrap/`: Contains the root application (`root-app.yaml`) that bootstraps the entire platform.
- `projects/`: Defines Argo CD `AppProject` resources for logical grouping and security.
- `apps/`: Contains Argo CD `Application` manifests for each project and environment.
- `values/`: Centralized Helm values for all applications, organized by project and environment.

## Getting Started

1. **Install Argo CD**: Follow the official documentation to install Argo CD in your cluster.
2. **Apply the AppProject**:
   ```bash
   kubectl apply -f projects/platform-project.yaml
   ```
3. **Apply the Root Application**:
   ```bash
   kubectl apply -f bootstrap/root-app.yaml
   ```

Argo CD will automatically discover and deploy all applications defined in the `apps/` directory.
