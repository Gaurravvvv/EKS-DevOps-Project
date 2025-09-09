*EKS DevOps Project*

1 . Made a small flask app .

2 . Made a requirements file .

3 . Wrote Dockerfile 

4 . Created an image of the Flask App .
 
5 . Built and ran the container on localhost:5000 .



*What's Up Next ?*

1 . The container will be uploaded on EKS(AWS) .
2 . Multiple tools will be used to setup the app 
    Eg : 
        
        1. Jenkins (CI/CD)
            Purpose: Automate building, testing, and deploying your Docker image.
            Why: You don’t want to run docker build & docker run manually every time you push code.
            Example: Push to GitHub → Jenkins auto-builds image → pushes it to AWS registry → deploys to Kubernetes.

        2.  AWS ECR (Elastic Container Registry)
            Purpose: Private container registry to store your Docker images.
            Why: Kubernetes (EKS) needs a place to pull images from. ECR is secure & integrated with AWS IAM.
            Example: Jenkins builds flask-app:1.0 → pushes it to ECR → EKS deploys it .

        3.  Kubernetes (EKS = Elastic Kubernetes Service)
            Purpose: Orchestrates containers (scaling, load balancing, self-healing).
            Why: Running 1 Docker container manually is easy, but what about 100 containers across 10 servers? That’s Kubernetes’ job.
            Example: Deploy your Flask app with YAML files → EKS handles pods, services, scaling.

        4.  Prometheus
            Purpose: Monitoring & alerting system.
            Why: You need to know CPU/memory usage, request rates, errors, etc.
            Example: “Alert me if CPU > 80% for 5 minutes.”

        5.  Grafana
            Purpose: Visualization dashboards for metrics.
            Why: Prometheus collects raw data → Grafana shows it in nice graphs.
            Example: See real-time traffic hitting your Flask app.

        6.  Trivy
            Purpose: Security scanner for Docker images & code.
            Why: Ensures your images don’t contain known vulnerabilities.
            Example: Scan flask-app:1.0 before pushing to ECR.

        7.  SonarQube
            Purpose: Code quality & static analysis.
            Why: Catches bugs, bad practices, and security flaws early.
            Example: Jenkins runs SonarQube scan → rejects deployment if issues found.



# Flask App

A simple Flask web application Dockerized for deployment to AWS ECR and Kubernetes.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Docker](#docker)
- [AWS ECR](#aws-ecr)
- [Kubernetes Deployment](#kubernetes-deployment)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

This Flask app is a minimal example project that demonstrates:

- Building and running a Flask app locally
- Dockerizing the application
- Pushing the Docker image to AWS Elastic Container Registry (ECR)
- Deploying the app to Kubernetes clusters (Minikube/EKS)

---

## Features

- Simple REST endpoint(s)
- Containerized for cloud deployment
- Easily scalable using Kubernetes

---

## Prerequisites

- Python 3.9+  
- Docker  
- AWS CLI configured with proper permissions  
- kubectl (for Kubernetes)  
- Minikube or access to EKS (optional for cloud deployment)  

---