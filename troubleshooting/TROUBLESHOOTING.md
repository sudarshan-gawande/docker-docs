# Docker Troubleshooting Guide

This guide provides solutions to common Docker issues.

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
Enable it to start on boot:
```sh
sudo systemctl enable docker
```
Verify its status:
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

## 3. Container Exiting Immediately
### Error:
```sh
docker run my_container exits immediately
```
### Solution:
- Check logs:
```sh
docker logs my_container
```
- Ensure the command in `CMD` or `ENTRYPOINT` is running correctly.

## 4. Port Binding Issues
### Error:
```sh
Bind for 0.0.0.0:80 failed: port is already allocated.
```
### Solution:
Check if another process is using the port:
```sh
sudo netstat -tulnp | grep :80
```
Stop the conflicting process:
```sh
sudo kill -9 <pid>
```

## 5. Container Not Connecting to the Internet
### Solution:
Restart the Docker network:
```sh
sudo systemctl restart docker
```
Check network settings:
```sh
docker network ls
docker network inspect bridge
```

## 6. Disk Space Issues
### Solution:
Remove unused Docker objects:
```sh
docker system prune -a
```
Check disk usage:
```sh
docker system df
```

## 7. Unable to Remove a Container
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

## 8. Image Pull Issues
### Error:
```sh
Error response from daemon: pull access denied
```
### Solution:
- Ensure you are logged in:
```sh
docker login
```
- Verify the image name and tag.

## 9. Volume Mounting Issues
### Solution:
Check volume existence:
```sh
docker volume ls
```
Inspect volume details:
```sh
docker volume inspect my_volume
```

## 10. Debugging Containers
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
This guide helps resolve common Docker issues efficiently. For deeper troubleshooting, consult Docker logs and system diagnostics.
