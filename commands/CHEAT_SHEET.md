# Docker Commands Cheat Sheet

## General Commands
```sh
# Check Docker version
docker --version

# Display system-wide information
docker info
```

## Images
```sh
# List all images
docker images

# Pull an image from Docker Hub
docker pull <image_name>

# Build an image from a Dockerfile
docker build -t <image_name> .

# Remove an image
docker rmi <image_name>

# Save an image as a tar file
docker save -o my_image.tar <image_name>

# Load an image from a tar file
docker load -i my_image.tar
```

## Containers
```sh
# List running containers
docker ps

# List all containers (including stopped ones)
docker ps -a

# Run a container
docker run -d --name <container_name> <image_name>

# Run a container interactively
docker run -it <image_name> /bin/bash

# Stop a running container
docker stop <container_id>

# Start a stopped container
docker start <container_id>

# Restart a container
docker restart <container_id>

# Remove a container
docker rm <container_id>
```

## Logs and Monitoring
```sh
# Show logs of a container
docker logs <container_id>

# Follow logs in real-time
docker logs -f <container_id>

# View resource usage of containers
docker stats

# Inspect details of a container
docker inspect <container_id>
```

## Networking
```sh
# List networks
docker network ls

# Create a network
docker network create <network_name>

# Connect a container to a network
docker network connect <network_name> <container_id>

# Disconnect a container from a network
docker network disconnect <network_name> <container_id>

# Remove a network
docker network rm <network_name>
```

## Volumes
```sh
# List volumes
docker volume ls

# Create a volume
docker volume create <volume_name>

# Remove a volume
docker volume rm <volume_name>

# Remove all unused volumes
docker volume prune
```

## Docker Compose
```sh
# Start containers using docker-compose
docker-compose up -d

# Stop containers
docker-compose down

# Restart containers
docker-compose restart

# View logs
docker-compose logs
```

## Cleanup and Pruning
```sh
# Remove all stopped containers
docker container prune

# Remove all unused images
docker image prune -a

# Remove all unused networks
docker network prune

# Remove all unused volumes
docker volume prune

# Remove all unused Docker objects
docker system prune -a
```

## Registry and Image Management
```sh
# Login to Docker Hub
docker login

# Tag an image
docker tag <image_name> <repository>:<tag>

# Push an image to Docker Hub
docker push <repository>:<tag>

# Pull an image from Docker Hub
docker pull <repository>:<tag>
```

## Advanced Commands
```sh
# Execute a command inside a running container
docker exec -it <container_id> /bin/bash

# Attach to a running container
docker attach <container_id>

# Export a container to a tar file
docker export -o my_container.tar <container_id>

# Import a container from a tar file
docker import my_container.tar my_imported_image
```

## Debugging and Troubleshooting
```sh
# Check Docker logs
docker logs <container_id>

# Inspect a container
docker inspect <container_id>

# Restart Docker daemon
sudo systemctl restart docker
```

## Conclusion
This cheat sheet provides a quick reference for managing Docker images, containers, networks, volumes, and more. Master these commands for efficient containerized application development and management.
