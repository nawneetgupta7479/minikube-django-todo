# 🚀 Django TODO App Deployed with Kubernetes (Minikube)

This is a fullstack TODO web application built using **Django REST Framework**, containerized using **Docker**, and deployed locally with **Minikube (Kubernetes)**. The Kubernetes configuration includes Deployment, Service, and Ingress YAMLs. The app was tested and run on an **AWS EC2 t2.medium instance** with Minikube installed. Docker images were pulled from **Docker Hub**, where the `django-todo-app` image was pre-built and hosted.

---

## 📦 Tech Stack & Tools

- ⚙️ **Backend**: Django + Django REST Framework  
- 🐳 **Docker**: Pre-built image hosted on Docker Hub  
- ☸️ **Kubernetes**: Minikube for local cluster orchestration  
- 🔁 **Routing**: NodePort & Ingress setup  
- ☁️ **Cloud**: AWS EC2 (t2.medium instance used for testing)

---

## 📁 Folder Structure

```
kubernetes_project/
├── deployment.yaml    # Kubernetes Deployment using DockerHub image
├── service.yaml       # NodePort service to expose the app
├── ingress.yaml       # Ingress rule for hostname-based routing
├── pod.yaml           # Optional: standalone pod for testing
```

---

## ⚙️ Kubernetes Setup Instructions

### 1. Start Minikube
```bash
minikube start
```

### 2. Apply Kubernetes Manifests
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f ingress.yaml
```

### 3. Access the App

Using NodePort:
```bash
minikube service django-todo-service --url
```

Or using Ingress:
- First, get Minikube IP:
  ```bash
  minikube ip
  ```
- Then update your `/etc/hosts`:
  ```
  <minikube-ip> django-todo.local
  ```
- Access in browser:  
  `http://django-todo.local`

---

## 🐋 Docker Image Used

- DockerHub Image: `guptanawneet/react_django:latest`  
  Pulled directly in Kubernetes Deployment via container spec.

---

## 💰 Cloud Info

This project was tested and deployed temporarily on an **AWS EC2 t2.medium instance** for verifying Kubernetes setup and Minikube configuration. The instance was **terminated after deployment testing** to avoid unnecessary billing.

---

## 📌 Highlights

- Production-style Kubernetes setup (deployment, service, ingress)
- Dockerized backend with images hosted on Docker Hub
- NodePort + Ingress routing support
- Runs on local Minikube or EC2-hosted Minikube cluster

---

## 🧑‍💻 Author

**Nawneet Kumar Gupta**  
*Fullstack Developer | Cloud + Kubernetes Enthusiast*  
GitHub: [https://github.com/nawneetgupta7479](https://github.com/nawneetgupta7479)
