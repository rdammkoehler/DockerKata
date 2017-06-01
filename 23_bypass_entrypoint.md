# Bypass `ENTRYPOINT`

Docker Documentation References:

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker build](https://docs.docker.com/engine/reference/commandline/build/)

[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)

## Intent

The purpose of this kata is to familiarize yourself with the process of running an image and bypassing its entrypoint safely.

## Overview

In this exercise we will create a docker image that has an entrypoint that runs `ls`, we will then run the image and bypass the `ENTRYPOINT` of the Dockerfile so we can run `sh`. We will then exit the container and delete the image.

## Kata Steps

### Create a `Dockerfile`

Use and editor to create a file named sh_noop_Dockerfile, or copy the [sh_noop_Dockerfile](sh_noop_Dockerfile) from this repository.

```Dockerfile
FROM alpine:3.6
MAINTAINER rpd@noradltd.com

ENTRYPOINT ls
```

### Build the Image

**Command**

```bash
docker build -t noop:latest -f sh_noop_Dockerfile .
```

**Output**

```bash
thought:DockerKata rich$ docker build -t noop:latest -f sh_noop_Dockerfile .
Sending build context to Docker daemon 754.7 kB
Step 1/3 : FROM alpine:3.6
 ---> a41a7446062d
Step 2/3 : MAINTAINER rpd@noradltd.com
 ---> Running in 03b5e6214ad4
 ---> 2355765f82a2
Removing intermediate container 03b5e6214ad4
Step 3/3 : ENTRYPOINT ls
 ---> Running in b020c65b0c41
 ---> e75fa49659ec
Removing intermediate container b020c65b0c41
Successfully built e75fa49659ec
```

### Test the container

**Command**

```bash
docker run noop
```

**Output**

```bash
thought:DockerKata rich$ docker run noop
bin
dev
etc
home
lib
media
mnt
proc
root
run
sbin
srv
sys
tmp
usr
var
```

### Bypass the Entrypoint

**Command**

```bash
docker run -it --entrypoint sh noop
```

**Output**

```bash
thought:DockerKata rich$ docker run -it --entrypoint sh noop
/ #
```

> Note: You are now at the `sh` prompt inside the running container

### Exit the container

**Command**

```bash
exit
```

**Output**

```bash
/ # exit
thought:DockerKata rich$
```

### Remove the image

**Command**

```bash
docker rmi -f noop
```

**Output**

```bash
thought:DockerKata rich$ docker rmi -f noop
Untagged: noop:latest
Deleted: sha256:e75fa49659ec8d02842c441c3bbc9888c591c95fdfb17aa00aed3b5722bda1ad
Deleted: sha256:2355765f82a2d13147aabb48d682bc3284c71d8a5c8b458e18bcf69c58303d7e
```

[Previous](22_define_volume.md) | [Index](README.md) | [Next](#)
