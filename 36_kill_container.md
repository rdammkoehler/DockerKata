# Kill a Running Container

Docker Documentation References:

[]()

## Intent

The intent of this exersice is to understand how to kill a running container. This is different from stopping it.

## Overview

In this exercise will will start a container in detached mode. We will then kill that container. Then we will remove the container.

## Kata Steps

### Start a Contanier
**Command**

```bash
docker run -d nginx:alpine
```

**Output**

```bash
/ # docker run -d nginx:alpine
aaa4af3afadf384d5762b4178ba4a10fbf610f0ed37b670f52ae8538dff52521
```

### List Containers

**Command**

```bash
docker ps
```

**Output**

```bash
/ # docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
aaa4af3afadf        nginx:alpine        "nginx -g 'daemon ..."   3 seconds ago       Up 2 seconds        80/tcp              sharp_heyrovsky
```

### Kill the Container
**Command**

```bash
docker kill sharp_heyrovsky
```

**Output**

```bash
/ # docker kill sharp_heyrovsky
sharp_heyrovsky
```

### Remove the Container

**Command**

```bash
docker rm sharp_heyrovsky
```

**Output**

```bash
/ # docker rm sharp_heyrovsky
sharp_heyrovsky
```

[Previous](35_system_info.md) | [Index](README.md) | [Next](37_login.md)
