### Working with containers

Running a container

```shell
docker run <image>
```

Displaying containers

```shell
# list running containers
docker ps
docker container ls

# list all containers
docker ps -a
docker container ls -a
```

Viewing logs

```shell
docker logs <container id>
```

Execute command in a running container

```shell
docker exec <container id> <command>

# interact with container's shell
docker exec -it <container id> sh
```

Starting and stopping containers

```shell
docker container start <container id>
docker start <container id>

docker container stop <container id>
docker stop <container id>
```

Removing containers

```shell
docker container rm <container id>
docker rm <container id>

# force remove
docker rm -f <container id>

# remove all stopped containers
docker container prune
```

Volumes to share and persist data

```shell
docker volume create app-data     # create a volume named app-data

docker volume ls                  # list all volumes

docker run -v app-data:/app/data  # bind mount app-data to container's app/data
```

Copying files

```shell
# copy data.txt from container to host's current directory
docker cp <container id>:/app/data.txt .

# copy data.txt from host to container's app/data
docker cp data.txt <container id>:/app/data
```

Sharing source code with container
```shell
docker run -v $(pwd):/app <image id>
```
