# Docker cheatsheat

## Containers

### Run container

`docker container run --publish [host_port]:[container_port] --detach --name [name] [docker_image_name]`

`docker container run -p [host_port]:[container_port] -d --name [name] [docker_image_name]`

`docker container run -p [host_port]:[container_port] -d --name [name] [docker_image_name] --network [network_name]`

`docker container run -v [host_path]:[cointainer_path] -d --name [name] [docker_image_name]`

### Start existing container

`docker container start [name/id]`

### List all running containers

`docker container ps`

### List all containers

`docker container ps -a`

`docker ps -a`

### Logs

`docker container logs --tail [nr_of_lines] [name]`

`docker container logs -f [name]`

`docker container logs --since=12h [name]`

### Top

`docker container top [name]`

### Stop

`docker container stop [names/ids]`

### Remove container

`docker container rm [-f] [names/ids]`

### Inspect container

`docker container inspect [names/ids]`

### Stats

`docker container stats [names/ids]`

`docker container stats`

### Get a shell - start a new container

`docker container run -it`

### Get a shell - exisiting container

`docker container exec -it [name] [script]`

- Example:

`docker container exec -it alpine sh`

## Images

### Pull image

`docker image pull`

### List images

`docker image ls`

### Build image from current folder

`docker image build -t [name] .`

### Remove dangling images

`docker image prune`

### Remove all unused images

`docker image prune -a`

`docker image prune -a -f --filter "until=2017-01-04T00:00:00"`

- Example: remove all images created 10 days ago

`docker image prune -a --force --filter "until=240h"`

## Networks

### Show networks

`docker network ls`

### Inspect networks

`docker network inspect [names/ids]`

### Create network

`docker network create [--driver] [driver_name] [name]`

`docker network create [-d] [driver_name] [name]`

### Connect to a network

`docker network connect [network_name] [container_name]`

`docker network connect --ip [ip] [network_name] [container_name]`

### Disconnect from a network

`docker network disconnect [network_name] [container_name]`

## Volumes

### Show volumes

`docker volume ls`

### Remove volumes

`docker volume rm [-f] [names/ids]`

### Remove all unused volumes

`docker volume prune [-f]`

## Compose

### Build

`docker-compose build [name]`

### Setup

`docker-compose up [-d]`
`docker-compose -f docker-compose.yml up`

### Cleanup

`docker-compose down`

### Cleanup(remoove build images)

`docker-compose down --rmi [all/local]`

## Swarm

### Init swarm

`docker swarm init`

`docker swarm init --advertise-addr [IP address]`

### Join a swarm

`docker swarm join [token]`

### Get token

`docker swarm join-token manager`

## Swarm nodes

### List nodes

`docker node ls`

### Promote nodes

`docker node update --role manager [node]`

### Running container inside node

`dokcer node ps [node]`

## Service

### List services

`docker service ls`

### Create service

`docker service create [image_name] [command]`

`docker service create --replicas 3 [image_name] [command]`

### List tasks/containers

`docker service ps [names/ids]`

### Scale service

`docker service update [name/id] --replicas 3`

### Remove service

`docker service rm [names/ids]`