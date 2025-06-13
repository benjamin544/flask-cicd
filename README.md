# CI/CD Flask Project

## Tools used in this project:
- Git + GitHub
- Jenkins
- Docker + Docker Hub
- Kubernetes (Minikube)
- Flask

## How it works:
1. The code is automatically pulled from GitHub (checkout).
2. Jenkins builds a Docker Image with the application.
3. The Image is pushed to Docker Hub.
4. Kubernetes deploys the Image using kubectl (deployment.yaml).
5. A NodePort service opens the application in the browser.

## How to test:
```bash
minikube start
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
minikube service flask-cicd-service
