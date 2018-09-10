# List Containers

Docker Documentation References:

[docker ps](https://docs.docker.com/engine/reference/commandline/ps/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker stop](https://docs.docker.com/engine/reference/commandline/stop/)

## Intent

The purpose of this kata is to familiarize yourself with the process of listing containers on your local docker installation.

## Overview

In this exercise we will run an image, list running images, stop the image, and list all containers.

## Kata Steps

### Run Image

> Note: Here we will pass the `-d` option flag to docker, telling it to run the image in a detached mode, [more on this topic later](07_start_containers.md).

**Command**

```bash
docker run -d nginx:alpine
```

**Output**

```bash
thought:DockerKata rich$ docker run -d nginx:alpine
11c3e639eaa97a2d0b9119782588b913c64817a5c5c0075cbd80afe87265a47d
```

> In the output above, the large hash represents the running container's identity.

### List Running Containers

**Command**

```bash
docker ps
```

**Output**

```bash
thought:DockerKata rich$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED              STATUS              PORTS               NAMES
11c3e639eaa9        nginx:alpine        "nginx -g 'daemon ..."   About a minute ago   Up About a minute   80/tcp              determined_jennings
```

> In the output above, noticed the value in the NAMES value in the right most column. This is an arbitrary name assigned to the running container by the docker command. It is much easier to remember than the hash value. We will use that name to stop the running container in the next step

### Stop the Container

**Command**

> Note: We will stop the detached container using its name. Alternately you can use the hash value.

```bash
docker stop determined_jennings
```

**Output**

```bash
thought:DockerKata rich$ docker stop determined_jennings
determined_jennings
```

### List All Containers

Using the `-a` option we can list all containers, running or otherwise. This is helpful if you want to remove a container from your system or otherwise need information about containers that you've run in the past.

**Command**

```bash
docker ps -a
```

**Output**

```bash
thought:DockerKata rich$ docker ps -a
CONTAINER ID        IMAGE                          COMMAND                  CREATED             STATUS                      PORTS               NAMES
11c3e639eaa9        nginx:alpine                   "nginx -g 'daemon ..."   2 minutes ago       Exited (0) 30 seconds ago                       determined_jennings
```

[Previous](02_list_images.md) | [Index](README.md) | [Next](04_delete_container.md)
