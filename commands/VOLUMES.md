# Docker Volumes Commands

Docker volumes provide a way to persist data beyond the lifecycle of a container.

## 1. List Available Volumes
```sh
docker volume ls
```

## 2. Create a New Volume
```sh
docker volume create my_volume
```

## 3. Inspect a Volume
```sh
docker volume inspect my_volume
```

## 4. Remove a Volume
```sh
docker volume rm my_volume
```

## 5. Remove All Unused Volumes
```sh
docker volume prune
```

## 6. Use a Volume in a Container
```sh
docker run -d -v my_volume:/app/data --name volume_container nginx
```

## 7. Bind Mount a Host Directory to a Container
```sh
docker run -d -v /host/path:/container/path --name bind_mount_container nginx
```

## 8. Named vs. Anonymous Volumes
- **Named Volume:**
  ```sh
  docker run -d -v my_named_volume:/app/data nginx
  ```
- **Anonymous Volume:**
  ```sh
  docker run -d -v /app/data nginx
  ```

## 9. Backup a Volume
```sh
docker run --rm -v my_volume:/data -v $(pwd):/backup busybox tar czf /backup/backup.tar.gz -C /data .
```

## 10. Restore a Volume from Backup
```sh
docker run --rm -v my_volume:/data -v $(pwd):/backup busybox tar xzf /backup/backup.tar.gz -C /data
```

## Conclusion
Docker volumes provide persistent data storage and allow sharing data between containers, making them essential for stateful applications.