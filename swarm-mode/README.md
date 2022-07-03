### Docker swam mode will need 3 vm machines to funtion as master/worker type
```
# init with a manager ip and get one tocken
docker swarm init --advertise-addr <MANAGER-IP> //192.168.99.100

# Use the token to join from worker nodes
docker swarm join \
  --token  SWMTKN-1-49nj1cmql0jkz5s954yi3oex3nedyz0fb0xx14ie39trti4wxv-8vxv8rssmk743ojnwacrr2e7c \
  192.168.99.100:2377

# Leave swarm node
docker swarm leave --force

# deploy docker swarm using compose file
docker stack deploy -c docker-compose.yml my-stack

# If you have .env file then use
docker stack deploy -c <(docker-compose config) my-stack

# Completely remove the stack
docker stack rm my-stack
# Force restart a container, May be to pick the file changes in its volume mount or a plain restart
docker service update —force < servicename or container id>

# To stop a container or to scale down a container
docker service scale <servicename>=0

# To scale up a container
docker service scale <servicename>=1

# To force update image of a container
docker service update --image "image" <servicename>

# To list swarm containers
docker services ls

# To list all containers
docker ps

# To list all containers + stopped containers
docker ps -a

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