# End-to-End DevOps Pipeline using Docker, Jenkins, Kubernetes & Monitoring

## Project Overview
This project demonstrates a **complete DevOps workflow** for beginners by implementing an end-to-end CI/CD pipeline using industry-standard tools.

The project starts from source code stored in GitHub, automates the build using Jenkins, containerizes the application with Docker, deploys it on Kubernetes, and monitors the system using Prometheus and Grafana.

This project is designed for **learning, resume building, and interview preparation**.

---

## Project Objectives
- Understand real-world DevOps pipeline flow
- Learn CI/CD using Jenkins
- Containerize applications using Docker
- Deploy applications on Kubernetes
- Implement basic monitoring using Prometheus & Grafana

---

## Tools & Technologies Used
- **GitHub** – Source code management  
- **Jenkins** – Continuous Integration (CI)  
- **Docker** – Containerization  
- **Kubernetes (Minikube)** – Container orchestration  
- **Prometheus** – Monitoring & metrics collection  
- **Grafana** – Visualization & dashboards  
- **Nginx** – Web server  

---

## ⚙️ DevOps Workflow (How This Project Works)
Developer Pushes Code to GitHub
↓
Jenkins Pipeline Triggers Automatically
↓
Jenkins Clones Repository
↓
Docker Image is Built
↓
Application is Deployed to Kubernetes
↓
Application & Containers are Monitored


---

##Project Structure
End-to-End-DevOps-Pipeline/
├── app/
│ └── index.html
├── Dockerfile
├── Jenkinsfile
├── k8s/
│ ├── deployment.yaml
│ └── service.yaml
├── monitoring/
│ └── prometheus.yml
└── README.md


---

##How to Run This Project (Step-by-Step)

### Clone the Repository
```bash
git clone https://github.com/m-prasanna/End-to-End-DevOps-Pipeline-using-Docker-Jenkins-Kubernetes-Monitoring.git
cd End-to-End-DevOps-Pipeline-using-Docker-Jenkins-Kubernetes-Monitoring

docker build -t devops-web .
docker run -d -p 8082:80 devops-web


minikube start
kubectl apply -f k8s/
minikube service devops-service


Monitoring Setup
docker run -d -p 9090:9090 -v ${PWD}\monitoring\prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus

http://localhost:9090


docker run -d -p 3000:3000 grafana/grafana
http://localhost:3000





