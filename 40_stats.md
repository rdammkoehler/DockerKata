# Get Stats on Running Containers

Docker Documentation References:

[]()

## Intent

The intent of this exercise is to understand how to get live streaming stats from the containers running in docker.

## Overview

In this exercise we will start a container and then ask the Docker Engine to display stats about that container. Then we will stop and remove the container.

## Kata Steps

### Start a container

**Command**

```bash
docker run -d nginx:alpine
```

**Output**

```bash
/ # docker run -d nginx:alpine
43d08e93f0e8d27d407289c619344311053ffe7f157711678d18b77f7de62f68
```

### Display Stats

**Command**

```bash
docker stats --no-stream
```

**Output**

```bash
/ # docker stats --no-stream
CONTAINER           CPU %               MEM USAGE / LIMIT       MEM %               NET I/O             BLOCK I/O           PIDS
d3e550ecf2b0        0.00%               1.707 MiB / 1.952 GiB   0.09%               508 B / 508 B       0 B / 0 B           2
```

### Stop the container

**Command**

```bash
docker stop $(docker ps -q)
```

> Here we use `docker ps` to list the ids of all running containers and feed that into `docker stop` so we don't have to look at or remember the container id or name.

**Output**

```bash
/ # docker stop $(docker ps -q)
d3e550ecf2b0
```

### Remove the container

**Command**

```bash
docker rm $(docker ps -aq)
```

**Output**

```bash
/ # docker rm $(docker ps -aq)
d3e550ecf2b0
```
> Here we use `docker ps` to list the ids of all containers and feed that into `docker rm` so we don't have to look at or remember the container id or name.


[Previous](39_change_repos.md) | [Index](README.md) | [Next](41_network_ports.md)
