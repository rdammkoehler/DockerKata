# Unpause a Container

Docker Documentation References:

[docker unpause](https://docs.docker.com/engine/reference/commandline/unpause/)

[docker pause](https://docs.docker.com/engine/reference/commandline/pause/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker stop](https://docs.docker.com/engine/reference/commandline/stop/)

[docker rm](https://docs.docker.com/engine/reference/commandline/rm/)

## Intent

The intent of this kata is to learn how to pause a running container. This kata is essentially the same as the [Pause a Container](42_pause_container.md) kata.

## Overview

In this exercise we will start a container, execute a command against the container, pause the container, execute another command against the container, list the running containers, kill the container, and then remove the container

## Kata Steps

### Start a Container

**Command**

```bash
docker run -p 80:80 -d nginx:alpine
```

**Output**

```bash
/ # docker run -p 80:80 -d nginx:alpine
2848300c09f1ad4feb2cea39750ed346022301057f71bc42809367e1d179c478
```

### Execute a command against the Container

**Command**

```bash
wget localhost
```

**Output**

```bash
/ # wget localhost
Connecting to localhost (127.0.0.1:80)
index.html           100% |*************************************************************************************************************|   612   0:00:00 ETA
```

### Pause the Container

**Command**

```bash
docker pause $(docker ps -q)
```

**Output**

```bash
/ # docker pause $(docker ps -q)
2848300c09f1
```

### Execute a command aginst the Container

**Command**

```bash
wget localhost
```

**Output**

```bash
/ # wget localhost
Connecting to localhost (127.0.0.1:80)
^C
```

> Note that this command fails because the container is paused, it is not responding to the `wget` call. (If you get tired of waiting you can hit Ctrl-C)

### List the Containers

**Command**

```bash
docker ps -a
```

**Output**

```bash
/ # docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED              STATUS                       PORTS                NAMES
2848300c09f1        nginx:alpine        "nginx -g 'daemon ..."   About a minute ago   Up About a minute (Paused)   0.0.0.0:80->80/tcp   quizzical_haibt
```

### Unpause the Container

**Command**

```bash
docker unpause $(docker ps -aq)
```

**Output**

```bash
/ # docker unpause $(docker ps -aq)
2848300c09f1
```

### Stop the Container

**Command**

```bash
docker stop $(docker ps -qa)
```

**Output**

```bash
/ # docker stop $(docker ps -qa)
2848300c09f1
```

### Remove the Container

**Command**

```bash
docker rm $(docker ps -aq)
```

**Output**

```bash
/ # docker rm $(docker ps -aq)
2848300c09f1
```

[Previous](42_pause_container.md) | [Index](README.md) | [Next](44_update_container_config.md)
