# Docker Flask App with CI/CD Deployment

## Overview
This project demonstrates building, containerizing, and deploying a Python Flask application using Docker and a fully automated CI/CD pipeline with GitHub Actions and AWS EC2.

---

## Project Structure
- `app.py` – Flask web application
- `requirements.txt` – Python dependencies
- `Dockerfile` – Docker build instructions
- `.github/workflows/deploy.yml` – CI/CD pipeline configuration

---

## How It Works

### 1. Application
A simple Flask app that runs on port `5000`.

### 2. Dockerization
The app is containerized using Docker:
- Base image: Python
- Installs dependencies
- Runs the Flask app

### 3. CI/CD Pipeline

1. Checks out the repository  
2. Logs into Docker Hub  
3. Builds the Docker image  
4. Pushes the image to Docker Hub  
5. Connects to AWS EC2 via SSH  
6. Pulls the latest image  
7. Stops and removes the old container  
8. Runs a new container with the updated image  

---

## GitHub Secrets Used
The pipeline uses secure credentials stored in GitHub Secrets:

- `DOCKERHUB_USERNAME`
- `DOCKERHUB_TOKEN`
- `EC2_HOST`
- `EC2_USERNAME`
- `EC2_SSH_KEY`

---

## Live Application
Accessible via: https://3.92.92.229/
