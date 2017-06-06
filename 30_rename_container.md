# Rename Container

Docker Documentation References:

[]()

## Intent

The purpose of this kata is to familiarize yourself with the process of renaming an existing container. 

## Overview

In this exercise we will create a container and then rename it, using `docker ps -a` to show the changes. We will then delete the container.

## Kata Steps

### Create a container

**Command**

```bash
docker run -p 80:80 -d nginx:alpine
```

**Output**

```bash
/ # docker run -p 80:80 -d nginx:alpine
a24a6518e663804ef003bff56f33711dd820544d93f2af64d9f4140bf0165558
```

### Stop the Container

**Command**

```bash
docker stop a24a6518e663804ef003bff56f33711dd820544d93f2af64d9f4140bf0165558
```

**Output**

```bash
/ # docker stop a24a6518e663804ef003bff56f33711dd820544d93f2af64d9f4140bf0165558
a24a6518e663804ef003bff56f33711dd820544d93f2af64d9f4140bf0165558
```

### List All Containers

**Command**

```bash
docker ps -a
```

**Output**

```bash
/ # docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                     PORTS               NAMES
a24a6518e663        nginx:alpine        "nginx -g 'daemon ..."   21 seconds ago      Exited (0) 3 seconds ago                       vibrant_darwin
```

### Rename the Container

**Command**

```bash
docker rename vibrant_darwin mynginx
```

**Output**

```bash
/ # docker rename vibrant_darwin mynginx
```

### List All Containers

**Command**

```bash
docker ps -a
```

**Output**

```bash
/ # docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED              STATUS                      PORTS               NAMES
a24a6518e663        nginx:alpine        "nginx -g 'daemon ..."   About a minute ago   Exited (0) 55 seconds ago                       mynginx
```

### Delete the Container

**Command**

```bash
docker rm mynginx
```

**Output**

```bash
/ # docker rm mynginx
mynginx
/ #
```


[Previous](29_fetch_logs.md) | [Index](README.md) | [Next](31_restart_container.md)
