# Remove Dangling Images

Docker Documentation References:

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)

Other documentation:

[Melissa Anderson - How To Remove Docker Images, Containers, and Volumes](https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes)

[Shishir Mahajan - What are Docker <none>:<none> images?](http://www.projectatomic.io/blog/2015/07/what-are-docker-none-none-images/)
## Intent

The purpose of this kata is to familiarize yourself with the process of removing all [dangling images](http://www.projectatomic.io/blog/2015/07/what-are-docker-none-none-images/) from your repository.

## Overview

In this exercise, we will create a docker image with no tags, causing it to be dangling. We will then remove the dangling images from our local repository.

## Kata Steps

### Create a dangling image

**Command**

```bash
docker build -f sh_noop_Dockerfile .
```

**Output**
```bash
thought:DockerKata rich$ docker build -f sh_noop_Dockerfile .
Sending build context to Docker daemon 784.4 kB
Step 1/3 : FROM alpine:3.6
 ---> a41a7446062d
Step 2/3 : MAINTAINER rpd@noradltd.com
 ---> Running in a2e7ad2babe9
 ---> 290fdc4d097d
Removing intermediate container a2e7ad2babe9
Step 3/3 : ENTRYPOINT ls
 ---> Running in 1883c45ab0fd
 ---> d6933bdb5bd2
Removing intermediate container 1883c45ab0fd
Successfully built d6933bdb5bd2
```

> Note: because we did not provide a tag for our image it will be considered dangling.

### List dangling images

**Command**

```bash
docker images -f dangling=true
```

**Output**

```bash
thought:DockerKata rich$ docker images -f dangling=true
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
<none>              <none>              d6933bdb5bd2        6 seconds ago       3.97 MB
```

### Remove dangling images

**Command**

```bash
docker rmi $(docker images -f dangling=true -q)
```

**Output**

```bash
thought:DockerKata rich$ docker rmi $(docker images -f dangling=true -q)
Deleted: sha256:d6933bdb5bd2ea5f9daa2e53a03575df364e0da04182e14c5a77fa59e2fc0576
Deleted: sha256:290fdc4d097d522e29087252cd11e7871eb3dcb4434ec0aff8fd0b4ecf176c57
```

### List dangling images

**Command**

```bash
docker images -f dangling=true
```

**Output**

```bash
thought:DockerKata rich$ docker images -f dangling=true
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
```

[Previous](24_remove_exited_containers.md) | [Index](README.md) | [Next](26_remove_all_images.md)
