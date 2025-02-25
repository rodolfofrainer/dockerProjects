# Docker ssh client-server tunnel

This project serves as practice in the creation, administration, inspection and deletion of containers with Docker.

## The Project

There are 2 Docker files, one on each of the "client" and "server" folders. The user must create both images separately in order to use them

### Server image

The server image creates a minimal container with essentially only "openssh-server" installed and configured for the root user with the password of "redhat".

### Client image

A simple ubuntu image with "openssh-client" installed.

## Installation

### Necessary Software

- [Docker](https://www.docker.com/get-started/)

### Building the images and running containers

#### Server image

**Building image**

`docker build -t [IMAGE_TAG] ./server`

**Running container**

`docker run -d --name [CONTAINER_NAME] [IMAGE_TAG]`

- Once the container is running the user should take note of it's IP address, which can be found on his terminal with the following command `docker inspect [CONTAINER_NAME] | grep IPAddress`

#### Client image

**Building image**

`docker build -t [IMAGE_TAG] ./client`

**Running container**

`docker run -it [IMAGE_TAG]`

With this command the user will find himself using the container's terminal, to verify that it is working properly the user should use the following commands

`ssh root@[SERVER_IP]`, `yes`, `redhat`

The user will find himself interacting with the server through the ssh tunnel.
