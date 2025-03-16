# Docker Architecture

## Overview
Docker follows a **client-server architecture**, where the **Docker Client** communicates with the **Docker Daemon** to build, run, and manage containers. It provides a lightweight, portable, and efficient way to package applications.

## Key Components of Docker Architecture

### 1. **Docker Client**
The Docker Client (`docker` CLI) is used to interact with the Docker Daemon via REST APIs. It sends commands like `docker run`, `docker build`, and `docker ps`.

### 2. **Docker Daemon (dockerd)**
The Docker Daemon (`dockerd`) is a background service that manages Docker containers and images. It listens for API requests and performs container lifecycle management.

### 3. **Docker Images**
Docker images are pre-built templates that contain application code, dependencies, and configurations. Images are stored in repositories like Docker Hub, AWS ECR, or a private registry.

### 4. **Docker Containers**
Containers are running instances of Docker images. They are isolated environments that run applications and include everything needed to execute the software.

### 5. **Dockerfile**
A `Dockerfile` is a script that contains instructions to build a Docker image. It defines the base image, dependencies, configurations, and commands needed to run an application.

### 6. **Docker Registry**
A Docker registry stores and distributes images. Public registries like **Docker Hub** and private registries (self-hosted or cloud-based) help manage images securely.

### 7. **Docker Volumes**
Volumes are used to **persist data** outside of a container’s filesystem. They enable data sharing between containers and improve storage management.

### 8. **Docker Networks**
Docker networking allows containers to communicate with each other and external systems. It supports multiple network drivers:
- **Bridge** (default for standalone containers)
- **Host** (shares the host network)
- **Overlay** (for multi-host communication)
- **Macvlan** (assigns MAC addresses to containers)

## High-Level Docker Workflow
1. **Pull an image** from Docker Hub or a private registry:
   ```sh
   docker pull nginx
   ```
2. **Create and run a container** from the image:
   ```sh
   docker run -d --name mynginx -p 8080:80 nginx
   ```
3. **View running containers**:
   ```sh
   docker ps
   ```
4. **Stop and remove a container**:
   ```sh
   docker stop mynginx
   docker rm mynginx
   ```
5. **Push an image** to a registry:
   ```sh
   docker tag myimage myrepo/myimage:latest
   docker push myrepo/myimage:latest
   ```

## Docker Architecture Diagram
![Docker Architecture](/images/docker-architecture.png)

## Conclusion
Docker provides a highly efficient containerization framework that improves **portability, scalability, and resource efficiency**. By understanding its architecture, you can leverage its full potential for application development and deployment.
