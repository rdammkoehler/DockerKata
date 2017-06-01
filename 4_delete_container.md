# Delete Container

Docker Documentation References:

[docker rm](https://docs.docker.com/engine/reference/commandline/rm/)

[docker ps](https://docs.docker.com/engine/reference/commandline/ps/)

## Intent

The purpose of this kata is to familarize yourself with the process of removing a container from your local docker installation.

## Overview

In this exercise we will delete the most recent container we created in the previous exercises.

## Kata Steps

### List Contianers

**Command**

```bash
docker ps -a
```

**Output**

```bash
thought:DockerKata rich$ docker ps -a
CONTAINER ID        IMAGE                          COMMAND                  CREATED             STATUS                      PORTS               NAMES
cfbed98f339d        nginx:alpine                   "nginx -g 'daemon ..."   5 minutes ago       Exited (0) 5 minutes ago                        goofy_jepsen
```

### Select and copy the container name (goofy_jespen)

> Because docker generates the name of the container randomly, your container will most likely not be `goofy_jepsen`. Later we will use names to ensure consistency.

### Delete the container

**Command**

```bash
docker rm goofy_jepsen
```

**Output**

```bash
thought:DockerKata rich$ docker rm goofy_jepsen
goofy_jepsen
```

### List Containers

**Command**

```bash
docker ps -a
```

Note that `goofy_jepsen` no longer exists in the listing.

[Previous](3_list_containers.md) | [Index](README.md) | [Next](5_delete_image.md)
