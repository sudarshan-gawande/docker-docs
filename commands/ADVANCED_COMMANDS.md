# Advanced Docker Commands

## 1. Inspect Docker Objects
### Inspect container details:
```sh
docker inspect <container_id>
```
### Inspect image details:
```sh
docker inspect <image_id>
```
### Inspect network details:
```sh
docker network inspect <network_name>
```

## 2. Manage Container Resources
### Limit CPU usage:
```sh
docker run -d --cpus="1.5" --name limited_container <image_name>
```
### Limit memory usage:
```sh
docker run -d --memory="512m" --name limited_memory_container <image_name>
```

## 3. Docker Logs & Debugging
### Display container logs:
```sh
docker logs <container_id>
```
### Follow logs in real-time:
```sh
docker logs -f <container_id>
```
### Get logs from a specific time:
```sh
docker logs --since=30m <container_id>
```

## 4. Docker Networking
### Create a custom network:
```sh
docker network create my_custom_network
```
### Connect a running container to a network:
```sh
docker network connect my_custom_network <container_id>
```
### Disconnect a container from a network:
```sh
docker network disconnect my_custom_network <container_id>
```
### Remove a custom network:
```sh
docker network rm my_custom_network
```

## 5. Data Management with Docker Volumes
### Create a named volume:
```sh
docker volume create my_volume
```
### Attach a volume to a container:
```sh
docker run -d -v my_volume:/app/data --name volume_container <image_name>
```
### List volumes:
```sh
docker volume ls
```
### Remove a volume:
```sh
docker volume rm my_volume
```

## 6. Docker Container Checkpoints
### Create a container checkpoint (experimental feature):
```sh
docker checkpoint create <container_id> my_checkpoint
```
### Restore a container from a checkpoint:
```sh
docker start --checkpoint my_checkpoint <container_id>
```

## 7. Save and Load Images
### Save a Docker image to a tar file:
```sh
docker save -o my_image.tar <image_name>
```
### Load a Docker image from a tar file:
```sh
docker load -i my_image.tar
```

## 8. Export and Import Containers
### Export a container’s filesystem to a tar file:
```sh
docker export -o my_container.tar <container_id>
```
### Import a container from a tar file:
```sh
docker import my_container.tar my_imported_image
```

## 9. Managing Docker System Resources
### Display system-wide information:
```sh
docker info
```
### Free up space by removing unused data:
```sh
docker system prune -a
```
### Remove all stopped containers, networks, and dangling images:
```sh
docker system prune --volumes
```

## 10. Running Containers in Detached and Interactive Mode
### Run a container in detached mode:
```sh
docker run -d --name detached_container <image_name>
```
### Run a container in interactive mode:
```sh
docker run -it --name interactive_container <image_name> /bin/bash
```

## Conclusion
These advanced Docker commands help in deep container management, debugging, and optimization. Mastering these commands allows efficient handling of large-scale containerized applications.
