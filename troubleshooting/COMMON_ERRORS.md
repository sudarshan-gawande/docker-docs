# Common Docker Errors and Solutions

This guide covers frequently encountered Docker errors and how to resolve them.

## 1. Docker Daemon Not Running
### Error:
```sh
Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
```
### Solution:
Start the Docker daemon:
```sh
sudo systemctl start docker
```
Enable Docker to start on boot:
```sh
sudo systemctl enable docker
```
Check the Docker service status:
```sh
sudo systemctl status docker
```

## 2. Permission Denied When Running Docker
### Error:
```sh
docker: Got permission denied while trying to connect to the Docker daemon socket.
```
### Solution:
Add your user to the Docker group:
```sh
sudo usermod -aG docker $USER
newgrp docker
```

## 3. Image Not Found or Pull Fails
### Error:
```sh
Error response from daemon: pull access denied for myimage, repository does not exist
```
### Solution:
- Verify the image name and tag:
```sh
docker search myimage
```
- Ensure you're logged into Docker Hub:
```sh
docker login
```
- Try pulling the image again:
```sh
docker pull myimage:latest
```

## 4. Port Binding Issues
### Error:
```sh
Bind for 0.0.0.0:80 failed: port is already allocated.
```
### Solution:
Find the process using the port:
```sh
sudo netstat -tulnp | grep :80
```
Stop the conflicting process:
```sh
sudo kill -9 <pid>
```

## 5. Container Exits Immediately After Running
### Error:
```sh
docker run my_container exits immediately
```
### Solution:
- Check logs:
```sh
docker logs my_container
```
- Ensure `CMD` or `ENTRYPOINT` is properly set in the Dockerfile.

## 6. Cannot Remove Running Container
### Error:
```sh
docker rm my_container -> Error: container is running
```
### Solution:
Stop the container first:
```sh
docker stop my_container
```
Then remove it:
```sh
docker rm my_container
```

## 7. Container Cannot Connect to Internet
### Solution:
Restart Docker networking:
```sh
sudo systemctl restart docker
```
Check network settings:
```sh
docker network ls
docker network inspect bridge
```

## 8. Volume Mount Issues
### Error:
```sh
mounts denied: The path does not exist
```
### Solution:
Check if the volume exists:
```sh
docker volume ls
```
Inspect volume details:
```sh
docker volume inspect my_volume
```
Ensure the host directory is accessible.

## 9. Docker Build Failing Due to Caching Issues
### Error:
```sh
failed to build: no space left on device
```
### Solution:
Clear unused Docker resources:
```sh
docker system prune -a
```
Check available disk space:
```sh
df -h
```

## 10. Debugging Running Containers
### Solution:
Access a running container’s shell:
```sh
docker exec -it my_container /bin/bash
```
Check container logs:
```sh
docker logs -f my_container
```

## Conclusion
These solutions address common Docker issues and help keep your containerized applications running smoothly. For advanced debugging, refer to Docker logs and system diagnostics.
