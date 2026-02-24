# 🚀 MEAN DevOps Assignment

## 📌 Project Overview
This project demonstrates containerization, deployment, CI/CD automation, and reverse proxy configuration for a MEAN stack application.

The application consists of:
- Frontend: Angular
- Backend: Node.js + Express
- Database: MongoDB
- Containerization: Docker
- Orchestration: Docker Compose
- CI/CD: GitHub Actions
- Deployment: AWS EC2 (Ubuntu)
- Reverse Proxy: Nginx

---

## 🐳 Containerization

### Backend
- Dockerfile created inside `/backend`
- Exposes port 8080

### Frontend
- Dockerfile created inside `/frontend`
- Served using Nginx
- Exposes port 80

### Database
- MongoDB official Docker image used

---

## ☁️ Deployment on AWS EC2

### Steps:
1. Created Ubuntu EC2 instance
2. Installed Docker & Docker Compose
3. Pulled Docker images from Docker Hub
4. Deployed using:

```bash
docker-compose up -d

Application accessible at:
http://<EC2_PUBLIC_IP>

CI/CD Pipeline (GitHub Actions)

Pipeline triggers on push to main branch.

It performs:

Builds backend Docker image

Builds frontend Docker image

Pushes images to Docker Hub

SSH into EC2

Pulls latest images

Restarts containers
Workflow file location:
.github/workflows/deploy.yml

Secrets Used

The following secrets are configured in GitHub:

DOCKER_USERNAME

DOCKER_PASSWORD

EC2_HOST

EC2_KEY

Nginx Reverse Proxy

Nginx configured to:

Route / → Frontend

Route /api → Backend

Entire application accessible via port 80
