# Portfolio Website Deployment using Docker and AWS EC2

## Project Overview

This project demonstrates the containerization and cloud deployment of a personal portfolio website using Docker and Amazon EC2. The website was packaged into a Docker container, tested locally, pushed to Docker Hub, and deployed on a cloud-based virtual machine running Ubuntu Linux.

The objective of this project is to understand containerization, cloud infrastructure, and deployment workflows used in modern DevOps practices.

---

## Technologies Used

- HTML5
- CSS3
- JavaScript
- Docker
- NGINX
- AWS EC2
- Ubuntu Server
- Git
- GitHub
- Docker Hub

---

## Project Architecture

User Browser
↓
AWS EC2 Instance (Ubuntu)
↓
Docker Container
↓
NGINX Web Server
↓
Portfolio Website

---

## Prerequisites

Before running this project, ensure the following tools are installed:

- Docker Desktop
- Git
- AWS Account
- VS Code

---

## Dockerfile

```dockerfile
FROM nginx:alpine

COPY . /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

---

## Building Docker Image

Navigate to the project directory and execute:

```bash
docker build -t portfolio-site .
```

Verify image creation:

```bash
docker images
```

---

## Running Container Locally

```bash
docker run -d -p 8080:80 portfolio-site
```

Access locally:

```text
http://localhost:8080
```

---

## Docker Hub Deployment

Login to Docker Hub:

```bash
docker login
```

Tag image:

```bash
docker tag portfolio-site <dockerhub-username>/portfolio-site:v1
```

Push image:

```bash
docker push <dockerhub-username>/portfolio-site:v1
```

---

## AWS EC2 Setup

### Instance Configuration

- Instance Type: t3.micro
- Operating System: Ubuntu Server
- Security Group Rules:
  - SSH (22)
  - HTTP (80)

### Connect to EC2

```bash
ssh -i portfolio-key.pem ubuntu@<PUBLIC-IP>
```

---

## Install Docker on EC2

```bash
sudo apt update

sudo apt install docker.io -y

sudo systemctl start docker

sudo systemctl enable docker

sudo usermod -aG docker ubuntu
```

Verify installation:

```bash
docker --version
```

---

## Deploy Docker Container on EC2

Pull image from Docker Hub:

```bash
docker pull <dockerhub-username>/portfolio-site:v1
```

Run container:

```bash
docker run -d -p 80:80 <dockerhub-username>/portfolio-site:v1
```

Verify:

```bash
docker ps
```

---

## Public Access

Open the website in a browser:

```text
http://34.224.215.38/
```

---

## Project Outcomes

- Successfully containerized a web application using Docker.
- Created and managed Docker images and containers.
- Used Docker Hub as a container registry.
- Launched and configured an AWS EC2 virtual machine.
- Deployed the containerized application on a cloud server.
- Accessed the application through a public IP address.

---

## Challenges Faced

1. Configuring AWS Security Groups.
2. Managing SSH key pairs.
3. Exposing Docker container ports.
4. Troubleshooting public access issues.
5. Understanding Docker image lifecycle.

---

## Future Enhancements

- Configure custom domain name.
- Enable HTTPS using SSL certificates.
- Implement CI/CD using GitHub Actions.
- Deploy using Kubernetes.
- Add monitoring and logging solutions.

---

## References

Docker Documentation:
https://docs.docker.com

AWS EC2 Documentation:
https://docs.aws.amazon.com/ec2

NGINX Documentation:
https://nginx.org
