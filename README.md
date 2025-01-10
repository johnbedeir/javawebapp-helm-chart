# javawebapp-helm-chart

1. Create helm chart

```
mkdir app-helm-chart
cd app-helm-chart
```

2. Package helm chart

```
helm package javawebapp
```

3. Commit the chart to github repository

4. Index the chart

```
helm repo index . --url https://<your-github-username>.github.io/<repo-name>

```

5. Enable GitHub Pages:
   Go to your repository's Settings.
   Scroll down to the Pages section.
   Select the branch (e.g., main) and folder (/ or docs) for GitHub Pages.
   Save the settings. Your repository is now served at a URL like:

```
https://<your-github-username>.github.io/<repo-name>
```

6. Add the helm repo

```
helm repo add javawebapp-repo https://<your-github-username>.github.io/<repo-name>
```

7. Update the helm repo

```
helm repo update
```
