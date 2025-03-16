# Introduction to Docker

## What is Docker?
Docker is an open-source platform that enables developers to automate the deployment, scaling, and management of applications using containerization. Containers allow applications to run in isolated environments with all their dependencies, making them portable and efficient across different systems.

## Why Use Docker?
- **Portability**: Runs anywhere (on-premises, cloud, or local machine).
- **Efficiency**: Lightweight and faster than virtual machines.
- **Scalability**: Easily scale applications across multiple environments.
- **Consistency**: Eliminates the "works on my machine" problem.
- **Security**: Provides application isolation.

## Key Docker Components
### 1. **Docker Engine**
The core component responsible for running and managing containers.

### 2. **Docker Images**
Pre-built packages that include the application and its dependencies. Images are stored in registries like Docker Hub.

### 3. **Docker Containers**
Running instances of Docker images that encapsulate applications and their dependencies.

### 4. **Dockerfile**
A script containing instructions to build a Docker image.

### 5. **Docker Compose**
A tool to define and manage multi-container applications using a YAML configuration file.

### 6. **Docker Registry**
A storage system for Docker images (e.g., Docker Hub, AWS ECR, Google Container Registry).

## Installation
### Install Docker on AWS EC2
1. Update the system:
   ```sh
   sudo yum update -y
   ```
2. Install Docker:
   ```sh
   sudo yum install docker -y
   ```
3. Start and enable the Docker service:
   ```sh
   sudo systemctl start docker
   sudo systemctl enable docker
   ```
4. Verify Docker installation:
   ```sh
   docker --version
   ```

## Basic Workflow
1. **Pull an Image**
   ```sh
   docker pull nginx
   ```
2. **Run a Container**
   ```sh
   docker run -d --name mynginx -p 8080:80 nginx
   ```
3. **List Running Containers**
   ```sh
   docker ps
   ```
4. **Stop a Container**
   ```sh
   docker stop mynginx
   ```
5. **Remove a Container**
   ```sh
   docker rm mynginx
   ```

## Conclusion
Docker revolutionizes the way applications are deployed and managed. By using containers, developers can ensure that their applications run consistently across different environments, making the development and deployment process more efficient. Whether you're running microservices, CI/CD pipelines, or cloud-native applications, Docker is an essential tool in modern software development.
