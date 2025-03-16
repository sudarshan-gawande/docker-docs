# Docker Compose Commands

Docker Compose is a tool for defining and managing multi-container Docker applications using a YAML file.

## 1. Verify Docker Compose Installation
```sh
docker-compose --version
```

## 2. Create a `docker-compose.yml` File
Example `docker-compose.yml` file for an Nginx and MySQL setup:
```yaml
version: '3.8'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
    depends_on:
      - db
  db:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: root
      MYSQL_DATABASE: mydb
```

## 3. Start Containers Using Docker Compose
```sh
docker-compose up -d
```

## 4. Stop and Remove Containers
```sh
docker-compose down
```

## 5. View Running Services
```sh
docker-compose ps
```

## 6. View Logs of All Services
```sh
docker-compose logs
```

## 7. Restart All Services
```sh
docker-compose restart
```

## 8. Run a Specific Service
```sh
docker-compose run <service_name> <command>
```
Example:
```sh
docker-compose run web sh
```

## 9. Execute a Command Inside a Running Container
```sh
docker-compose exec <service_name> <command>
```
Example:
```sh
docker-compose exec web ls -l
```

## 10. Scale Services
```sh
docker-compose up --scale web=3 -d
```

## 11. Build and Rebuild Services
```sh
docker-compose build
```

## 12. Remove All Containers, Networks, and Volumes
```sh
docker-compose down -v
```

## 13. Start in Debug Mode
```sh
docker-compose up --verbose
```

## Conclusion
Docker Compose simplifies multi-container application management, enabling seamless orchestration of services with a single YAML file.
