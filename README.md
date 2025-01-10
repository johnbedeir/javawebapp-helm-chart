# Java Web App Helm Chart

This repository contains the Helm chart for deploying the `javawebapp` application to a Kubernetes cluster. Follow the steps below to create, package, and deploy the chart.

---

## Prerequisites

- Helm CLI installed ([Install Helm](https://helm.sh/docs/intro/install/))
- Kubernetes cluster configured and `kubectl` installed
- GitHub Pages enabled for this repository

---

## Steps to Use the Helm Chart

### 1. **Create the Helm Chart**

Create the Helm chart for the `javawebapp` application:

```bash
mkdir app-helm-chart
cd app-helm-chart
```

---

### 2. **Package the Helm Chart**

Package the chart into a `.tgz` file:

```bash
helm package javawebapp
```

---

### 3. **Commit the Chart to GitHub**

Commit the `.tgz` file to this GitHub repository.

---

### 4. **Index the Chart**

Generate an `index.yaml` file for the chart:

```bash
helm repo index . --url https://<your-github-username>.github.io/<repo-name>
```

Replace `<your-github-username>` with your GitHub username and `<repo-name>` with the name of your repository.

---

### 5. **Enable GitHub Pages**

1. Go to your repository's **Settings**.
2. Scroll to the **Pages** section.
3. Select the branch (e.g., `main`) and folder (`/` or `docs`) for GitHub Pages.
4. Save the settings. Your repository will be served at:
   ```
   https://<your-github-username>.github.io/<repo-name>
   ```

---

### 6. **Add the Helm Repository**

Add your GitHub Pages as a Helm repository:

```bash
helm repo add javawebapp-repo https://<your-github-username>.github.io/<repo-name>
```

---

### 7. **Update the Helm Repository**

Update your Helm repositories to fetch the latest charts:

```bash
helm repo update
```

---

### 8. **Deploy the Application**

Install the Helm chart to your Kubernetes cluster:

```bash
helm install javawebapp javawebapp-repo/javawebapp
```

---

### 9. **Uninstall the Application**

To remove the application from your cluster:

```bash
helm uninstall javawebapp
```

---

## Notes

- Replace `<your-github-username>` and `<repo-name>` with your actual GitHub username and repository name where applicable.
- Ensure your Kubernetes cluster is configured and accessible before deploying the chart.
