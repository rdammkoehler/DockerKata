# Remove Exited Containers

Docker Documentation References:

[docker rm](https://docs.docker.com/engine/reference/commandline/rm/)

[docker ps](https://docs.docker.com/engine/reference/commandline/ps/)

Other documentation:

[Melissa Anderson - How To Remove Docker Images, Containers, and Volumes](https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes)

## Intent

The purpose of this kata is to familiarize yourself with the process of removing all exited containers from your docker configuration.

> WARNING: This will delete those containers and you will need to recreate them. Do NOT execute this Kata against your local configuration unless you are willing to recreate all of your containers.

## Overview

In this exercise, we will list all of the exited containers on our system, then we will delete them, and relist the exited containers. Note that this action is not recoverable, don't execute this kata unless your ok with loosing your containers.

## Kata Steps

### List all Exited Containers

**Command**

```bash
docker ps -a -f status=exited
```

**Output**

```bash
thought:DockerKata rich$ docker ps -a -f status=exited
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
4b8cadc3e0a8        e75fa49659ec        "sh"                18 minutes ago      Exited (0) 16 minutes ago                       lucid_stonebraker
5a8565827a32        e75fa49659ec        "/bin/sh -c ls"     20 minutes ago      Exited (0) 20 minutes ago                       affectionate_joliot
thought:DockerKata rich$
```

### Delete all Exited Containers

> WARNING: This will delete those containers and you will need to recreate them. Do NOT execute this Kata against your local configuration unless you are willing to recreate all of your containers.

**Command**

```bash
docker rm $(docker ps -a -f status=exited -q)
```

**Output**

```bash
thought:DockerKata rich$ docker rm $(docker ps -a -f status=exited -q)
4b8cadc3e0a8
5a8565827a32
```

> WARNING: This will delete those containers and you will need to recreate them. Do NOT execute this Kata against your local configuration unless you are willing to recreate all of your containers.

### List all Exited Containers

**Command**

```bash
docker ps -a -f status=exited
```

**Output**

```bash
thought:DockerKata rich$ docker ps -a -f status=exited
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
```

[Previous](23_bypass_entrypoint.md) | [Index](README.md) | [Next](25_remove_dangling_images.md)
