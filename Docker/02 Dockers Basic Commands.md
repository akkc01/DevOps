# Dockers Commands--
---

## Check Docker Version-
- Description: Displays the version of Docker installed on your machine.
```powershell
Docker --version
```

## Pull Commands-
- Description: Downloads a Docker image from a registry (such as Docker Hub).
```powershell
docker pull <image-name>:<tag>
```
- Example-
```powershell
docker pull ubuntu:latest
```

## Run Commands-
- Basic Syntax:
```powershell
docker run [OPTIONS] IMAGE [COMMAND] [ARGUMENTS...]
```
- IMAGE: The name of the Docker image you want to run.
- COMMAND (optional): The command you want to run inside the container.
- ARGUMENTS (optional): Arguments to pass to the command.
### Key Options and Flags for docker run:
- `1- -d, --detach`
- Description: Runs the container in detached mode (in the background), so it doesn’t block your terminal.
```powershell
docker run -d <image-name>
docker run -d nginx
```

```powershell
Flag                                  	Explanation
--detach ,-d                  Runs a container in the background and prints the container ID
--env , -e	                  Sets environment variables
--hostname , -h	              Sets a hostname to a container
--label , -l	                Creates a meta data label for a container
--name	                      Assigns a name to a container
--network	                    Connects a container to a network
--rm	                        Removes container when it stops
--read-only	                  Sets the container filesystem as read-only
--workdir , -w	              Sets a working directory in a container
```
example-
```powershell
docker run -d -p 80:80 nginx
```

## Container Interaction Commands-
- `Interactin`with containers:-
```powershell
docker start container	                                      # Starts a new container
docker stop container	                                      # Stops a container
docker pause container	                                      # Pauses a container
docker unpause container	                                    # Unpauses a container
docker restart container	                                    # Restarts a container
docker wait container	                                        # Blocks a container
docker export container	                                      # Exports container contents to a tar archive
docker attach container	                                      # Attaches to a running container
docker wait container	                                        # Waits until the container is terminated and shows the exit code
docker commit -m “commit message” -a “author” container username/image_name: tag	# Saves a running container as an image
docker logs -ft container	                                    # Follows container logs
docker exec -ti container script.sh	                          # Runs a command in a container
docker commit container image	                                # Creates a new image from a container
docker create image	                                          # Creates a new container from an image

```
## Registry Commands:-
- Commands:-
```powershell
docker image ls	             # Lists images
docker image rm mysql	       # Removes an image
docker tag image tag	       # Tags an image
docker history image	       # Displays the image history
docker inspect image	       # Displays low-level information about an image
```

## Container Inspection Commands--
- Commands:-
```powershell
docker ps                   # list all running containers
docker -ps -a               # Lists all containers 
docker diff container       # Inspects changes to directories and files in the container filesystem
docker top container        # Shows all running processes in an existing container
docker inspect container    # Displays low-level information about a container
docker logs container       # Gathers the logs for a container
docker stats container      # Shows container resource usage statistics

```

## Build Commands--
- Commands-
```powershell
docker build	                                                        # Builds an image from a Dockerfile in the current directory
docker build https://github.com/docker/rootfs.git#container:docker  	# Builds an image from a remote GIT repository
docker build -t imagename/tag	                                        # Builds and tags an image for easier tracking
docker build https://yourserver/file.tar.gz	                          # Builds an image from a remote tar archive
docker build -t image:1.0-<<EOFFROM busyboxRUN echo “hello world”EOF	# Builds an image via a Dockerfile that is passed through STDIN

```

## Clean Up Commands:-
- Commands:-
```powershell
docker image prune	                                          # Clears an unused image
docker image prune -a	                                        # Clears all images that are not being used by containers
docker system prune	                      # Removes all stopped containers, networks not used, all dangling images, and all build cache
docker image rm image	                                        # Removes an image
docker rm container	                                          # Removes a running container
docker swarm leave	                                          # Leaves a swarm
docker stack rm stackname	                                    # Removes a swarm
docker volume rm $(docker volume ls -f dangling=true -q)    	# Removes all dangling volumes
docker rm $(docker ps -a -q)	                                # Removes all stopped containers
docker kill $ (docker ps -q)	                                # Stops all running containers

```

##  Manage Images Commands--
- Commands:-
```powershell
docker image ls	            # Lists images
docker image rm mysql	      # Removes an image
docker tag image tag	      # Tags an image
docker history image	      # Displays the image history
docker inspect image	      # Displays low-level information about an image

```


## Service Commands--
- Commands:-
```powershell
docker service ls	                             # Lists all services running in a swarm
docker stack services stackname	               # Lists all running services
docker service ps servicename	                 # Lists the tasks of a service
docker service update servicename              # Updates a service
docker service create image	                   # Creates a new service
docker service scale servicename=10	           # Scales one or more replicated services
docker service logs stackname servicename	     # Lists all service logs
```

## Network Commands-
- Commands:-
```powershell
docker network create networkname	                   # Creates a new network
docker network rm networkname	                       # Removes a specified network
docker network ls	                                   # Lists all networks
docker network connect networkname container	       # Connects a container to a network
docker network disconnect networkname container      # Disconnects a container from a network
docker network inspect networkname	                 # Displays detailed information about a network
```
## docker volume-
- Description: Manages Docker volumes.
- Common commands:
  ```powershell
docker volume ls: List all volumes.
docker volume create <volume-name>: Create a new volume.
docker volume inspect <volume-name>: View details of a volume.
docker volume rm <volume-name>: Remove a volume.
```

## Compose Command-
- Description: Manages multi-container Docker applications using a docker-compose.yml file.
-Common commands:
```powershell
docker-compose up: Starts the application and services defined in docker-compose.yml.
docker-compose down: Stops and removes the containers defined in docker-compose.yml.
docker-compose build: Builds the services defined in docker-compose.yml.
docker-compose logs: Fetches logs for the services in docker-compose.yml.
```

## Tag Command-
- Description: Tags an image with a new name or version.
- Usage:
  ```powershell
docker tag <source-image>:<source-tag> <target-image>:<target-tag>
```
Example-
```powershell
docker tag myapp:1.0 myapp:v2
```
## save Command-
- Description: Saves a Docker image to a tarball archive.
- Usage:
```powershell
docker save -o <output-file.tar> <image-name>:<tag>
```
-Example:-
```powershell
docker save -o myapp.tar myapp:1.0
```

