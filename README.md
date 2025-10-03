# AI-Powered Recruitment Platform

Full-stack recruitment application demonstrating enterprise DevOps practices: CI/CD automation, container orchestration, infrastructure as code, and real-time monitoring.

## Features

- **Resume Analysis**: AI-powered resume matching against job descriptions
- **Mock Interviews**: Practice interviews with automated feedback
- **Coding Assessments**: Multi-language code execution environment
- **Role-Based Access**: Separate dashboards for candidates, HR, and admins

## Tech Stack

**Application**: React, Node.js, Express, MongoDB  
**DevOps**: GitHub Actions, Docker, Kubernetes, Ansible, Prometheus, Grafana  
**Cloud**: Docker Hub Registry, Minikube

## Quick Start
```bash
# Clone and run
git clone https://github.com/G-karthick0501/devops_trail.git
cd devops_trail
docker-compose up -d

# Access
# Frontend: http://localhost:80
# Backend: http://localhost:5000
# Grafana: http://localhost:3000 (username/password) :: (admin/admin)
# Prometheus: http://localhost:9090

```
## Configuration Management (Ansible)
```
cd ansible
ansible-playbook -i inventory.ini playbook.yml --ask-become-pass
```

## Kubernetes Deployment
```
kubectl apply -f k8s/
kubectl get pods -n recruitment-app
```


## Rolling Update Demo
```
# Update
kubectl set image deployment/backend backend=recruitment-backend:v2 -n recruitment-app
kubectl rollout status deployment/backend -n recruitment-app

# Rollback
kubectl rollout undo deployment/backend -n recruitment-app
```

## Troubleshooting

```
# Check status
docker-compose ps
kubectl get pods -n recruitment-app

# View logs
docker logs recruitment-backend
kubectl logs <pod-name> -n recruitment-app

# Rebuild
docker-compose down -v
docker-compose up -d --build
```

## Project Structure
  .
  ├── .github/workflows/    # CI/CD pipeline definitions
  ├── ansible/              # Infrastructure automation
  ├── backend/              # Node.js API
  ├── frontend/             # React application
  ├── k8s/                  # Kubernetes manifests
  ├── monitoring/           # Prometheus and Grafana config
  └── docker-compose.yml    # Local development orchestration



