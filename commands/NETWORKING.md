# Docker Networking Commands

Docker provides networking capabilities that allow containers to communicate with each other and external networks.

## 1. List Available Networks
```sh
docker network ls
```

## 2. Create a Custom Network
```sh
docker network create my_custom_network
```

## 3. Inspect a Network
```sh
docker network inspect my_custom_network
```

## 4. Connect a Running Container to a Network
```sh
docker network connect my_custom_network <container_id>
```

## 5. Disconnect a Container from a Network
```sh
docker network disconnect my_custom_network <container_id>
```

## 6. Remove a Network
```sh
docker network rm my_custom_network
```

## 7. Network Drivers in Docker
Docker supports multiple network drivers:

- **Bridge (default)**: Used for communication between containers on the same host.
  ```sh
  docker network create --driver bridge my_bridge_network
  ```
- **Host**: Shares the host network namespace, removing network isolation.
  ```sh
  docker run --net=host nginx
  ```
- **None**: Disables networking for the container.
  ```sh
  docker run --net=none nginx
  ```
- **Overlay**: Used in Docker Swarm for multi-host networking.
  ```sh
  docker network create --driver overlay my_overlay_network
  ```
- **Macvlan**: Assigns a MAC address to the container, making it appear as a physical device on the network.
  ```sh
  docker network create --driver macvlan --subnet=192.168.1.0/24 my_macvlan_network
  ```

## 8. Run a Container on a Specific Network
```sh
docker run --network=my_custom_network --name my_container nginx
```

## 9. Check the IP Address of a Running Container
```sh
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container_id>
```

## 10. Remove All Unused Networks
```sh
docker network prune
```

## Conclusion
Docker networking enables secure and efficient communication between containers. By leveraging different network drivers, you can build scalable and flexible containerized applications.