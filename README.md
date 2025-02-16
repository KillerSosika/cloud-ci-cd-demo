# 🚀 Cloud CI/CD Demo - Deploy to AWS EKS

This project demonstrates a **CI/CD pipeline** for deploying a containerized application to **AWS Elastic Kubernetes Service (EKS)** using **GitHub Actions**.

## 🌟 Features
✅ **Fully automated deployment** using GitHub Actions  
✅ **Kubernetes (EKS) integration**  
✅ **Dockerized application** with auto-deploy  
✅ **AWS LoadBalancer Service** for external access  

## 🛠 Tech Stack
- **AWS EKS** - Managed Kubernetes  
- **GitHub Actions** - CI/CD automation  
- **Docker** - Containerization  
- **Kubernetes** - Orchestration  
- **Nginx** (Optional Ingress) - Load Balancing  

## ⚙️ Setup & Deployment

### 🐳 1. Build & Push Docker Image
If you make changes to the app, rebuild and push the Docker image:

docker build -t your-dockerhub-username/myapp:latest .
docker push your-dockerhub-username/myapp:latest

🚀 2. Deploy to Kubernetes (EKS)
GitHub Actions will deploy automatically on push to main, but you can deploy manually:

kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml

🔍 3. Check Deployment Status

kubectl get pods
kubectl get services
Find the EXTERNAL-IP from kubectl get services and open in browser.

🔄 How to Update Deployment
If you push new Docker images, update the deployment:

kubectl rollout restart deployment myapp
🛠 Local Development
To run locally using Docker:


docker run -p 5000:5000 your-dockerhub-username/myapp:latest
