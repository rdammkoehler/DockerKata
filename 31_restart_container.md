# Restart a Container

Docker Documentation References:

[docker restart](https://docs.docker.com/engine/reference/commandline/restart/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker ps](https://docs.docker.com/engine/reference/commandline/ps/)

[docker stop](https://docs.docker.com/engine/reference/commandline/stop/)

[docker rm](https://docs.docker.com/engine/reference/commandline/rm/)

## Intent

The purpose of this kata is to familiarize yourself with the process of restarting a container.

## Overview

In this exercise, we will create a container, list the running containers, then restart the container, then list the running containers, then we will stop the container and delete it.

## Kata Steps

### Create a container

**Command**

```bash
docker run -p 80:80 -d nginx:alpine
```

**Output**

```bash
/ # docker run -p 80:80 -d nginx:alpine
cd36553fe412a72ccce129e778a1fe445ff24cbf277573060b22942929203158
```

### List the running containers

**Command**

```bash
docker ps
```

**Output**

```bash
/ # docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                NAMES
cd36553fe412        nginx:alpine        "nginx -g 'daemon ..."   8 seconds ago       Up 7 seconds        0.0.0.0:80->80/tcp   jovial_mahavira
```

### Restart the Container

**Command**

```bash
docker restart jovial_mahavira
```

**Output**

```bash
/ # docker restart jovial_mahavira
jovial_mahavira
```

### List the Running Containers

**Command**

```bash
docker ps
```

**Output**

```bash
/ # docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                NAMES
cd36553fe412        nginx:alpine        "nginx -g 'daemon ..."   27 seconds ago      Up 5 seconds        0.0.0.0:80->80/tcp   jovial_mahavira
```

> Notice that the uptime is shorter now.

### Stop the Container

**Command**

```bash
docker stop jovial_mahavira
```

**Output**

```bash
/ # docker stop jovial_mahavira
jovial_mahavira
```

### Delete the container

**Command**

```bash
docker rm jovial_mahavira
```

**Output**

```bash
/ # docker rm jovial_mahavira
jovial_mahavira
/ #
```

[Previous](30_rename_container.md) | [Index](README.md) | [Next](32_attach_container.md)
