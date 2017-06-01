# Defining Your Volume

Docker Documentation References:

[Dockerfile](https://docs.docker.com/engine/reference/builder/)

[docker build](https://docs.docker.com/engine/reference/commandline/build/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)

## Intent

The purpose of this kata is to familiarize yourself with the process of creating a volume mount point in a docker image. 

## Overview

In this exercise we will create a docker image that writes to a host volume when it is run. The command simply dumps the output of the ps command into a file. When we run the image the container will mount a local volume to capture the output of the command. We will then remove the output, the container(s), the image, and the docker volume.

## Kata Steps

### Create a `Dockerfile`

Use and editor to create a file named sh_ps_out_Dockerfile, or copy the [sh_ps_out_Dockerfile](sh_ps_out_Dockerfile) from this repository.

The file should contain the following

```Dockerfile
FROM alpine:3.6
MAINTAINER rpd@noradltd.com

VOLUME /docker_kata_vol

ENTRYPOINT mkdir -p /docker_kata_vol && /bin/ps -ef > /docker_kata_vol/ps.out
```

### Build the Image

**Command**

```bash
docker build -t ps_out:latest -f sh_ps_out_Dockerfile .
```

**Output**

```bash
thought:DockerKata rich$ docker build -t ps_out:latest -f sh_ps_out_Dockerfile .
Sending build context to Docker daemon   578 kB
Step 1/4 : FROM alpine:3.6
 ---> a41a7446062d
Step 2/4 : MAINTAINER rpd@noradltd.com
 ---> Running in 5d56c34a0c4c
 ---> b2e7f794afb7
Removing intermediate container 5d56c34a0c4c
Step 3/4 : VOLUME /docker_kata_vol
 ---> Running in 1fe5bdcab8df
 ---> 90e6b25914e3
Removing intermediate container 1fe5bdcab8df
Step 4/4 : ENTRYPOINT mkdir -p /docker_kata_vol && /bin/ps -ef > /docker_kata_vol/ps.out
 ---> Running in 3a65d9a82abb
 ---> 4a4aeb757b9a
Removing intermediate container 3a65d9a82abb
Successfully built 4a4aeb757b9a
```

### Test the container

**Command**

```bash
mkdir -p test && docker run --volume `pwd`/test:/docker_kata_vol ps_out:latest && ls test && cat test/ps.out
```

> Tip: You must specify an absolute location for the host volume to mount to, hence the `pwd` in the volume argument.

**Output**

```bash
thought:DockerKata rich$ mkdir -p test && docker run --volume `pwd`/test:/docker_kata_vol ps_out:latest && ls test && cat test/ps.out
ps.out
PID   USER     TIME   COMMAND
    1 root       0:00 /bin/sh -c mkdir -p /docker_kata_vol && /bin/ps -ef > /docker_kata_vol/ps.out
    8 root       0:00 /bin/ps -ef
```

### Remove the output

**Command**

```bash
rm -Rf test
```

### Remove the image

**Command**

```bash
docker rmi -f ps_out
```

**Output**

```bash
thought:DockerKata rich$ docker rmi -f ps_out
Untagged: ps_out:latest
Deleted: sha256:4a4aeb757b9af7cdd07f561e2a9dbc429aaf10c22626ba45367b7363b5ad712c
Deleted: sha256:90e6b25914e3c0fd89fe446b0cad43a398e7b33cc4b5d8c53782450e50d0e262
Deleted: sha256:b2e7f794afb7995540168a50371e21513ba8900e7edb94bf4319475d83cff99a
```
### Remove exited containers

**Command**

```bash
docker rm $(docker ps -a -f status=exited -q)
```

**Output**

```bash
thought:DockerKata rich$ docker rm $(docker ps -a -f status=exited -q)
29c6fb36ca34
516a0940ac7b
f07a83fb857b
30abde40e934
4b244250786a
cd5c6d5b51f6
6ffffde2c258
139698da14d8
53d1b3074522
bc59b50e589a
ea6a7eadaf89
b93733dc0169
ce1554e80f95
c2f23ac73644
```

### Remove the docker volume

**Command**

```bash
docker volume rm test
```

**Output**

```bash
thought:DockerKata rich$ docker volume rm test
test
```

[Previous](21_define_network_interface.md) | [Index](README.md) | [Next](#)
