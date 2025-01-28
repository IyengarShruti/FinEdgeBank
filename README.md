## FinEdge Bank - Mock Financial Technology Application

## Overview
FinEdge Bank presents a cutting-edge mock financial technology application built with Python and cloud technologies. It demonstrates a complete development lifecycle, from local development to cloud deployment.

## Core Features

User Management: Secure registration and authentication.
Account Handling: Creation and management of user accounts.
Transaction Processing: Perform and track financial transactions.
Development Journey
Local Development

Flask backend with PostgreSQL for user and transaction data.
Environment variables configured in a .env file.
Dockerization

Application containerized using Docker for consistency across environments.
Cloud Deployment

Hosted on AWS using EKS for Kubernetes, RDS for PostgreSQL, and AWS Secrets Manager for secure data handling.
Infrastructure as Code (IaC)

Automated setup using Terraform and configuration management with Ansible.
CI/CD

## GitHub Actions for automated testing and deployment.
Architecture Overview
Frontend: Flask-based web application.
Backend: Hosted on AWS EKS and RDS (PostgreSQL).
Infrastructure: Managed with Terraform and Ansible.
Monitoring: Prometheus and Grafana for performance tracking.

## Deployment Guide
1. Infrastructure Setup

Navigate to the terraform directory.
Run the following commands:
bash
Copy
Edit
terraform init  
terraform apply
Update Kubernetes context with Terraform output.

## 2. Kubernetes Configuration

Deploy the application using Kubernetes manifests:
bash
Copy
Edit
kubectl apply -f k8s/
Set up ingress controller:
bash
Copy
Edit
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.2/deploy/static/provider/aws/deploy.yaml
## 3. Monitoring Setup

Run Ansible scripts to configure Prometheus and Grafana:
bash
Copy
Edit
ansible-playbook playbook.yml -vv
Access monitoring tools:
Prometheus: <PROMETHEUS_PUBLIC_IP>:9090
Grafana: <GRAFANA_PUBLIC_IP>:3000 (default credentials: admin/admin).
Local Development & Testing
Requirements

## Docker and Docker Compose installed.
Steps

Create a .env file in the src directory with database credentials.
Run the application locally:
bash
Copy
Edit
docker-compose up --build
Access the app at http://localhost:5000.
Cleanup
For Docker:
bash
Copy
Edit
docker-compose down
For Terraform resources:
bash
Copy
Edit
terraform destroy
## FinEdge Bank is a complete mock project showcasing secure, scalable financial technology solutions. 🚀
