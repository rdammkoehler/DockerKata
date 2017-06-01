# Defining Your Volume

Docker Documentation References:


[Dockerfile](https://docs.docker.com/engine/reference/builder/)

[docker build](https://docs.docker.com/engine/reference/commandline/build/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)

### Intent

The purpose of this kata is to familiarize yourself with the process of creating a volume mount point in a docker image. 

### Overview

### Kata Steps

##### Create a `Dockerfile`

Use and editor to create a file named sh_http_lcl_Dockerfile, or copy the [sh_http_lcl_Dockerfile](sh_http_lcl_Dockerfile) from this repository.

The file should contain the following

```Dockerfile
FROM alpine:3.6
MAINTAINER rpd@noradltd.com

RUN "ps -ef" > /docker_kata_vol/ps.out

VOLUME /docker_kata_vol
```

##### Build the Image

**Command**

```bash
docker build -t qotd:latest -f sh_http_lcl_Dockerfile .
```

[Previous](21_define_network_interface.md) | [Index](README.md) | [Next](#)
