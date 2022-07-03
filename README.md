# Docker

```
# Docker file  - Dockerfile
This will have a simple Docker file and you can build it using
docker build -t <imagename> <path>

# To run a container
docker run --name <container name> -d -p hostport:containerport -p hostport:containerport <image id>

# Basic commands
docker stop container-name

docker start container-name

# Last created
docker ps -l

# docker size
docker ps -s

# List all containers
docker ps -a
```