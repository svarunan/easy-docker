### Docker compose mode

```
# Docker pull all the images in yml
docker-compose pull

# Build containers from docker-compose.yml
docker-compose up -d

# Tell Docker to start up the containers again but rebuild it to get the latest changes 
docker-compose up --build

# Scale a container
docker-compose up -d --scale <container_name>=2

# Compose down
docker-compose down

# Compose down with volumes
docker-compose down -v

# To start the last exited container
docker-compose start

# Tail the logs of the container
docker-compose logs -f

# To list all containers
docker ps

# To list all containers + stopped containers
docker ps -a

# Remove images
docker rmi image

# Remove container
docker rm container-id

# Force remove container
docker rm -f container-id

# To inspect docker container and its config
docker node inspect

# To remove existing docker networks
docker network prune

# To remove dangling images, dead containers
docker system prune

# To Reload docker daemon services
systemctl daemon-reload

# To restart docker and daemon services
systemctl restart docker

# To get IP address on a container
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container id

# To get IP address of all the containers
docker ps -q | xargs -n 1 docker inspect --format '{{ .Name }} {{range .NetworkSettings.Networks}} {{.IPAddress}}{{end}}' | sed 's#^/##';

```