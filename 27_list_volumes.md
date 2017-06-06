# List Docker Volumes

Docker Documenation References:

[docker volume ls](https://docs.docker.com/engine/reference/commandline/volume_ls/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker stop](https://docs.docker.com/engine/reference/commandline/stop/)


## Intent

The purpose of this kata is to familiarize yoruself with the process of listing all of the docker volumes on your system.

## Overview

In this exercise we will list all of the docker volumes that we presently have, then create another volume by running a container. We will then list the volumes again to show the new volume.

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

[Previous](26_remove_all_images.md) | [Index](README.md) | [Next](28_remove_volume.md)
