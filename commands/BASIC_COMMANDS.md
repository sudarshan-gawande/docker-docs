# Basic Docker Commands

## 1. Docker Version
Check the installed Docker version:
```sh
docker --version
```

## 2. Docker Help
List available Docker commands:
```sh
docker --help
```

## 3. Docker Images
### List all available images:
```sh
docker images
```
### Pull an image from Docker Hub:
```sh
docker pull <image_name>
```
### Remove an image:
```sh
docker rmi <image_name>
```

## 4. Docker Containers
### List running containers:
```sh
docker ps
```
### List all containers (including stopped ones):
```sh
docker ps -a
```
### Run a container:
```sh
docker run -d --name <container_name> <image_name>
```
### Run a container interactively:
```sh
docker run -it <image_name> /bin/bash
```
### Stop a running container:
```sh
docker stop <container_id>
```
### Start a stopped container:
```sh
docker start <container_id>
```
### Restart a container:
```sh
docker restart <container_id>
```
### Remove a container:
```sh
docker rm <container_id>
```

## 5. Docker Logs & Monitoring
### Show logs of a container:
```sh
docker logs <container_id>
```
### Follow logs in real-time:
```sh
docker logs -f <container_id>
```
### View resource usage of containers:
```sh
docker stats
```

## 6. Docker Networks
### List networks:
```sh
docker network ls
```
### Create a network:
```sh
docker network create <network_name>
```
### Connect a container to a network:
```sh
docker network connect <network_name> <container_id>
```
### Disconnect a container from a network:
```sh
docker network disconnect <network_name> <container_id>
```
### Remove a network:
```sh
docker network rm <network_name>
```

## 7. Docker Volumes
### List volumes:
```sh
docker volume ls
```
### Create a volume:
```sh
docker volume create <volume_name>
```
### Remove a volume:
```sh
docker volume rm <volume_name>
```
### Remove all unused volumes:
```sh
docker volume prune
```

## 8. Cleanup
### Remove all stopped containers:
```sh
docker container prune
```
### Remove all unused images:
```sh
docker image prune -a
```
### Remove all unused networks:
```sh
docker network prune
```
### Remove all unused volumes:
```sh
docker volume prune
```

## 9. Docker Registry
### Login to Docker Hub:
```sh
docker login
```
### Tag an image:
```sh
docker tag <image_name> <repository>:<tag>
```
### Push an image to Docker Hub:
```sh
docker push <repository>:<tag>
```
### Pull an image from Docker Hub:
```sh
docker pull <repository>:<tag>
```

## 10. Docker Exec & Attach
### Execute a command inside a running container:
```sh
docker exec -it <container_id> /bin/bash
```
### Attach to a running container:
```sh
docker attach <container_id>
```

## Conclusion
These basic Docker commands help in managing images, containers, networks, and volumes efficiently. Mastering these commands will enable smooth containerized application development and deployment.