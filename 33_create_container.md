# Create, but don't start, a Container

Docker Documentation References:

[docker create](https://docs.docker.com/engine/reference/commandline/create/)

[docker ps](https://docs.docker.com/engine/reference/commandline/ps/)

[docker rm](https://docs.docker.com/engine/reference/commandline/rm/)

## Intent

The intent of this exercise is to familiarize yourself with creating a container but not starting the container when you do it.

## Overview

In this exercise will will create a conainer with a name, but we will not start that container. We will show it in the list of containers. Then we will remove it.

## Kata Steps

### Create Container

**Command**

```bash
docker create --name docker_kata_nginx -p 80:80 nginx:alpine
```

**Output**

```bash
/ # docker create --name docker_kata_nginx -p 80:80 nginx:alpine
a5c285acb74fc12e1f68ad0758587860d062d814dab23c7815d715c474d22e3d
```

### List Containers

**Command**

```bash
docker ps -a
```

**Output**

```bash
/ # docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
a5c285acb74f        nginx:alpine        "nginx -g 'daemon ..."   5 seconds ago       Created                                 docker_kata_nginx
```

### Remove Container

**Command**

```bash
docker rm docker_kata_nginx
```

**Output**

```bash
/ # docker rm docker_kata_nginx
docker_kata_nginx
```

[Previous](32_attach_container.md) | [Index](README.md) | [Next](34_image_history.md)
