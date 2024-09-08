# Introduction
> Docker is a platform that simplifies the creation, deployment, and running of applications using containers. It packages applications and their dependencies into a single unit, ensuring consistent execution across various environments. Docker provides a lightweight and efficient way to build, ship, and run applications.

# Docker Architecture
> The Docker architecture consists of several key components:

* ***Docker Daemon:*** The core service that runs on a host machine. It manages images, containers, networks, and volumes.
* ***Docker Client:*** An interface used to interact with the Docker daemon. It sends commands to the daemon, which executes them.
* ***Docker Images:*** Read-only templates that define the environment for a container. They contain the application and its dependencies.
* ***Docker Containers:*** Instances of Docker images. They are created from images and can be started, stopped, paused, and removed.
* ***Docker Registry:*** A repository for storing Docker images. The official Docker Hub is a public registry, while private registries can also be used.

# Image Commands
* ***docker pull [image_name]:*** Pulls an image from a registry.
Example: docker pull hello-world
* ***docker search [search_term]:*** Searches for images in a registry.
Example: docker search ubuntu
* ***docker images:*** Lists all images on the system.
Example: docker images
* ***docker rmi [image_id]:*** Removes an image.
Example: docker rmi <image_id>

# Container Commands
* ***docker run [image_name]:*** Creates and starts a container from an image.
> Example: docker run hello-world
* ***docker ps:*** Lists running containers.
> Example: docker ps
* ***docker stop [container_id]:*** Stops a running container.
> Example: docker stop <container_id>
* ***docker start [container_id]:*** Starts a stopped container.
> Example: docker start <container_id>
* ***docker rm [container_id]:*** Removes a container.
> Example: docker rm <container_id>
* ***docker exec [container_id] [command]:*** Executes a command inside a running container.

# Dockerfile
> A Dockerfile is a text document that contains a set of instructions to build a Docker image. It defines the base image, environment variables, dependencies, and commands to run during the build process.

# Dockerfile Commands
* ***FROM:*** Specifies the base image to use.
> Example: FROM ubuntu:latest
* ***RUN:*** Executes commands in the image during the build process.
> Example: RUN apt-get update && apt-get install -y nginx
* ***COPY:*** Copies files from the host system to the image.
> Example: COPY . /app
* ***CMD:*** Sets the default command to run when a container is created.
> Example: CMD ["nginx", "-g", "daemon off;"]
* ***EXPOSE:*** Exposes ports for incoming connections.
> Example: EXPOSE 80

# Docker Compose
> Docker Compose is a tool for defining and running multi-container Docker applications. It uses a YAML file to configure the services and their dependencies.   
```
Docker Compose Syntax
YAML
version: '3.7'

services:
  web:
    build: .
    ports:
      - "8080:80"
    volumes:
      - "./app:/usr/src/app"
    depends_on:
      - db

  db:
    image: postgres:latest
    volumes:
      - db_data:/var/lib/postgresql/data

volumes:
  db_data:
```
