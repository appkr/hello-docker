## Hello Docker

https://docs.docker.com/get-started/

### Container

```bash
~/hello-docker $ docker build --tag hello-docker .
```

```bash
~/hello-docker $ docker run --publish 4000:80 hello-docker
```

```bash
~/hello-docker $ docker tag hello-docker {GIT_USER_ID}/hello-docker:latest
~/hello-docker $ docker push {GIT_USER_ID}/hello-docker:latest
```

#### Cheatsheet

```bash
docker build -t friendlyname .  # Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyname  # Run "friendlyname" mapping port 4000 to 80
docker run -d -p 4000:80 friendlyname         # Same thing, but in detached mode
docker container ls                                # List all running containers
docker container ls -a             # List all containers, even those not running
docker container stop <hash>           # Gracefully stop the specified container
docker container kill <hash>         # Force shutdown of the specified container
docker container rm <hash>        # Remove specified container from this machine
docker container rm $(docker container ls -a -q)         # Remove all containers
docker image ls -a                             # List all images on this machine
docker image rm <image id>            # Remove specified image from this machine
docker image rm $(docker image ls -a -q)   # Remove all images from this machine
docker login             # Log in this CLI session using your Docker credentials
docker tag <image> username/repository:tag  # Tag <image> for upload to registry
docker push username/repository:tag            # Upload tagged image to registry
docker run username/repository:tag                   # Run image from a registry
```

### Service

```bash
~/hello-docker $ docker swarm init
```

```bash
~/hello-docker $ docker stack deploy -c docker-compose.yml getstartedlab
```

#### Cheatsheet

```bash
docker stack ls              # List all running applications on this Docker host
docker stack deploy -c <composefile> <appname>  # Run the specified Compose file
docker stack services <appname>       # List the services associated with an app
docker stack ps <appname>   # List the running containers associated with an app
docker stack rm <appname>                             # Tear down an application
```
