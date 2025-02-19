# Dockers Basic Commands--
---
### Container Interaction Commands-
- `Starts/Stops/Restarts/Pauses/Unpauses` a container:
```powershell
docker start container
docker stop container
docker restart container	
docker pause container	
docker unpause container	
```
- `Blocks/Exports/Attaches` a container:
```powershell
docker wait container
docker export container	
```
> **Note:** The `export` Exports container contents to a tar archive.

- `Saves a running container as an image`:
```powershell
docker commit -m “commit message” -a “author” container username/image_name: tag	
```

- container `logs`/-
```powershell
docker logs -ft container
```
- Runs a command in a container and Creates a new image from a container-
  - container `logs`/-
```powershell
docker exec -ti container script.sh
docker commit container image	
```
- Creates a new container from an image-
```powershell

```



docker create image	
```
##Container Inspection Commands--
Commands-
docker ps  
docker -ps -a
docker diff container
docker top container
docker inspect container
docker logs container
docker stats container

Explanation-
Lists all running containers
Lists all containers
Inspects changes to directories and files in the container filesystem
Shows all running processes in an existing container
Displays low-level information about a container
Gathers the logs for a container
Shows container resource usage statistics


VPS
Apr 11, 2024

Ignas R.

5min Read

Docker Cheat Sheet: All the Most Essential Commands in One Place + Downloadable PDF
Docker is a popular open-source platform that makes it easy to build, test, deploy, and manage containerized applications in a consistent, portable, or virtual environment such as VPS.

While a powerful tool in your development arsenal, learning the different Docker commands can take time and effort. New users often benefit from having a Docker cheat sheet readily at hand.

In this tutorial, we will explain how Docker works and provide the most common Docker commands, along with a downloadable cheat sheet for you to use.

Download free docker cheat sheet

Docker Architecture
Docker Commands Cheat Sheet
Build Commands
Clean Up Commands
Container Interaction Commands
Container Inspection Commands
Manage Images Commands
Run Commands
Registry Commands
Service Commands
Network Commands
Docker Architecture
Docker architecture consists of five main components: server, client, container, image, and registry.

Docker Server

A Docker server or Docker daemon is a program that runs in the background of your computer and manages Docker containers and images. When you use the Docker command line interface.

(CLI) to create, run, or manage containers, you interact with the Docker daemon.

The Docker daemon is an essential platform component that ensures containers can be started and stopped automatically when the system boots up.

Docker Client

The Docker client lets users interact with the Docker daemon with its command-line interface (CLI). In simple terms, it’s the main part of the Docker architecture for creating, managing, and running container applications.

When you use the Docker CLI to pass a command, the Docker client sends the command to the Docker daemon running on your computer, which then carries out the requested operation. The Docker client can be installed on any machine that needs to interact with the Docker daemon, including your local machine, a remote server, or a virtual server.


Docker Container

A Docker container is a package that contains all the required prerequisites to run an application.

Containers are designed to be highly portable, meaning that they can be easily moved from one environment to another, such as from a developer’s laptop to a testing environment or from a testing environment to a production environment.

Docker Image

A Docker image is a preconfigured template that specifies what should be included in a Docker container. Usually, images are downloaded from websites like Docker Hub. However, it’s also possible to create a custom image with the help of Dockerfile.

Docker Registry

The Docker registry is a central repository that stores and manages Docker images. It is a server-based system that lets users store and share Docker images with others, making it easy to distribute and deploy applications. The most notable Docker registry is Docker Hub.

Docker Commands Cheat Sheet
Now that you know how Docker functions, let’s look at some of the most popular Docker command examples.

##Build Commands--
docker build
docker build https://github.com/docker/
rootfs.git#container:docker
docker build -t imagename/tag
docker build https://yourserver/file.tar.gz
docker build -t image:1.0
-<<EOFFROM busyboxRUN echo “hello world”EOF

Builds an image from a Dockerfile in the current directory
Builds an image from a remote GIT repository
Builds and tags an image for easier tracking
Builds an image from a remote tar archive
Builds an image via a Dockerfile that is passed through STDIN


## Clean Up Commands--
docker image prune
docker image prune -a
docker system prune
docker image rm image
docker rm container
docker swarm leave
docker stack rm stackname

Clears an unused image
Clears all images that are not being used by containers
Removes all stopped containers, all networks not used by containers, all dangling images, and all build cache
Removes an image
Removes a running container
Leaves a swarm
Removes a swarm

##  Manage Images Commands--
docker image ls
docker image rm mysql
docker tag image tag
docker history image
docker inspect image

Lists images
Removes an image
Tags an image
Displays the image history
Displays low-level information about an image

## Run Commands--
docker run (options) image (command) (arg...)

Flag
--detach , -d
--env , -e
--hostname , -h
--label , -l
--name

Explanation
Runs a container in the background and prints the container ID
Sets environment variables
Sets a hostname to a container
Creates a meta data label for a container
Assigns a name to a container


## Service Commands--
Command
docker service ls
docker stack services stackname
docker service ps servicename
docker service update servicename
docker service create image

Explanation
Lists all services running in a swarm
Lists all running services
Lists the tasks of a service
Updates a service
Creates a new service

## Network Commands--
Command
docker network create networkname
docker network rm networkname
docker network ls
docker network connect networkname container
docker network disconnect networkname container
docker network inspect networkname

Explanation
Creates a new network
Removes a specified network
Lists all networks
Connects a container to a network
Disconnects a container from a network
Displays detailed information about a network

