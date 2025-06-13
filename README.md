CI/CD Flask Project
Tools used in this project:
Git + GitHub

Jenkins

Docker + Docker Hub

Kubernetes (Minikube)

Flask

How it works:
The code is automatically pulled from GitHub (git checkout).

Jenkins builds a Docker image of the Flask application.

The Docker image is pushed to Docker Hub.

Kubernetes deploys the Docker image using kubectl and the deployment manifest (deployment.yaml).

A NodePort service exposes the application so it can be accessed from the browser.

How to test the project locally:
Start Minikube:


minikube start
Deploy the application:



kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
Open the service in your browser:


minikube service flask-cicd-service
