# Remove Docker Volume

Docker Documentation References:

[]()

## Intent

The purpose of this kata is to familiarize yourself with the process of removing a docker volume.

## Overview

In this exercise we will list all of the docker volumes that we presently have, then creat a another volume by running a container. We will then list the volumes to show the new volume. We will then delete the container(s) that use that volume, and then we will delete the new volume.

## Kata Steps

### List Docker Volumes

**Command**

```bash
docker volume ls
```

**Output**

```bash
thought:DockerKata rich$ docker volume ls
DRIVER              VOLUME NAME
```

### Run a Container that uses a Volume

**Command**

```bash
docker run --detach --publish 8080:80 --volume html:/usr/share/nginx/html:ro nginx:stable-alpine
```

**Output**

```bash
thought:DockerKata rich$ docker run --detach --publish 8080:80 --volume html:/usr/share/nginx/html:ro nginx:stable-alpine
Unable to find image 'nginx:stable-alpine' locally
stable-alpine: Pulling from library/nginx
6f821164d5b7: Already exists
56a320d6ae3a: Pull complete
b163e42aa316: Pull complete
faff037f1455: Pull complete
Digest: sha256:d69b66b23458974804e0f19a6585249d4e9c30e52462df8c7a29381cd598ba20
Status: Downloaded newer image for nginx:stable-alpine
36bdcfb1e5fca03ee50a2468f2e83175ea18b9445af0d3436b8845c98997082e
```

### Stop the container

**Command**

```bash
docker stop 36bdcfb1e5fca03ee50a2468f2e83175ea18b9445af0d3436b8845c98997082e
```

**Output**

```bash
thought:DockerKata rich$ docker stop 36bdcfb1e5fca03ee50a2468f2e83175ea18b9445af0d3436b8845c98997082e
36bdcfb1e5fca03ee50a2468f2e83175ea18b9445af0d3436b8845c98997082e
```

### List Docker Volumes

**Command**

```bash
docker volume ls
```

**Output**

```bash
thought:DockerKata rich$ docker volume ls
DRIVER              VOLUME NAME
local               html
```

### Try to Delete the Volume to get the ID of the Container that owns it

># WHAT! There has to be a better way

**Command**

```bash
docker volume rm html
```

**Output**

```bash
thought:DockerKata rich$ docker volume rm html
Error response from daemon: unable to remove volume: remove html: volume is in use - [36bdcfb1e5fca03ee50a2468f2e83175ea18b9445af0d3436b8845c98997082e]
```

### Delete the Container

**Command**

```bash
docker rm 36bdcfb1e5fca03ee50a2468f2e83175ea18b9445af0d3436b8845c98997082e
```

**Output**

```bash
thought:DockerKata rich$ docker rm 36bdcfb1e5fca03ee50a2468f2e83175ea18b9445af0d3436b8845c98997082e
36bdcfb1e5fca03ee50a2468f2e83175ea18b9445af0d3436b8845c98997082e
```

### Remove the Volume

**Command**

```bash
docker volume rm html
```

**Output**

```bash
thought:DockerKata rich$ docker volume rm html
html
```

[Previous](27_list_volumes.md) | [Index](README.md) | [Next](#)
