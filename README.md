# MLflow MLOps (Docker + Helm + CI)

Serveur de tracking MLflow containerise, deploye avec Helm sur Kubernetes, image publiee par GitHub Actions.

## Image (CI)

- Quay : `quay.io/nqasmi/mlflow-tracking:latest`
- Docker Hub : `docker.io/qasmi12/mlflow-tracking:latest`

## Deploiement local (kind)

```bash
helm upgrade --install mlflow ./helm/mlflow --namespace mlflow --create-namespace
kubectl port-forward svc/mlflow 5001:5000 -n mlflow
```

UI : http://localhost:5001

## CI

Workflow : `.github/workflows/docker-build-push.yml` (push sur `main`).
