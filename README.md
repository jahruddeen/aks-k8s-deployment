# AKS Kubernetes Deployment with Azure DevOps

This project demonstrates a complete DevOps workflow to deploy a Node.js application to Azure Kubernetes Service (AKS) using Docker and Azure DevOps CI/CD.

## Architecture

Developer → GitHub → Azure DevOps Pipeline → Docker Build → Azure Container Registry → AKS Cluster → LoadBalancer Service → Application

## Technologies Used

- Docker
- Kubernetes
- Azure Kubernetes Service (AKS)
- Azure Container Registry (ACR)
- Azure DevOps
- GitHub
- Linux

## Project Structure

aks-k8s-deployment
│
├── Dockerfile
├── README.md
├── azure-pipelines.yml
│
└── kubernetes
    ├── deployment.yml
    └── service.yml

## Build Docker Image

docker build -t node-devops-app .

## Push Image to Azure Container Registry

docker tag node-devops-app <ACR_NAME>.azurecr.io/node-devops-app:v1

docker push <ACR_NAME>.azurecr.io/node-devops-app:v1

## Deploy to AKS

kubectl apply -f deployment.yml

kubectl apply -f service.yml

## Verify Deployment

kubectl get pods

kubectl get svc

## Access Application

kubectl get svc

Use the EXTERNAL-IP to access the application.

## Author

Jahruddeen Ansari

DevOps | Kubernetes | Azure | Docker

