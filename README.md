# INT332
Docker commands,volume,bind mounts 
# Docker Basics – INT332

## 1. Check Docker Installation
docker --version

## 2. Pull an Image
docker pull ubuntu

## 3. List Images
docker images

## 4. Run a Container (Foreground)
docker run ubuntu

## 5. Run a Container (Interactive)
docker run -it ubuntu bash

## 6. Run a Container (Detached Mode)
docker run -d ubuntu

## 7. List Running Containers
docker ps

## 8. List All Containers (running + stopped)
docker ps -a

## 9. Stop a Running Container
docker stop <container_id>

## 10. Remove a Container
docker rm <container_id>

## 11. Remove an Image
docker rmi <image_id>

## 12. Container Logs
docker logs <container_name>

## 13. Container Terminal Access
docker exec -it <container_name> bash
