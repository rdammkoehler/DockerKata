# Setting Environment Variables

Docker Documentation References:

[Dockerfile](https://docs.docker.com/engine/reference/builder/)

[docker build](https://docs.docker.com/engine/reference/commandline/build/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)

## Intent

The purpose of this kata is to familiarize yourself with the process of setting an environment variable within the Dockerfile.

## Overview

In this exercise, we will create a simple Dockerfile and set an environment variable with will impact the output of the application. We will then delete the image.

## Kata Steps

### Create a `Dockerfile`

Use and editor to create a file named sh_hello_user_Dockerfile, or copy the [sh_hello_user_Dockerfile](sh_hello_user_Dockerfile) from this repository.

The file should contain the following

```Dockerfile
FROM alpine:3.6
MAINTAINER rpd@noradltd.com

ENV DOCKER_USER_NAME Timmy

ENTRYPOINT [ "sh", "-c", "echo $DOCKER_USER_NAME" ]
```

### Build the Image

**Command**

```bash
docker build -f sh_hello_user_Dockerfile .
```

**Output**

```bash
thought:DockerKata rich$ docker build -f sh_hello_user_Dockerfile .
Sending build context to Docker daemon 428.5 kB
Step 1/4 : FROM alpine:3.6
 ---> a41a7446062d
Step 2/4 : MAINTAINER rpd@noradltd.com
 ---> Running in c8a1f43cd26a
 ---> a2e52da4f0f7
Removing intermediate container c8a1f43cd26a
Step 3/4 : ENV DOCKER_USER_NAME Timmy
 ---> Running in c4070af347b5
 ---> ad7801c15908
Removing intermediate container c4070af347b5
Step 4/4 : ENTRYPOINT sh -c echo $DOCKER_USER_NAME
 ---> Running in 9c6bec933243
 ---> dd175670ab16
Removing intermediate container 9c6bec933243
Successfully built dd175670ab16
```

### List Images

**Command**

```bash
docker images
```

**Output**

```bash
thought:DockerKata rich$ docker images
REPOSITORY                                   TAG                 IMAGE ID            CREATED             SIZE
<none>                                       <none>              dd175670ab16        3 seconds ago       3.97 MB
```

> Note: We will use the `IMAGE ID` which will differ from machine to machine, so you must select what is on your computer for the next two steps.

### Run the Image

**Command**

```bash
docker run dd175670ab16
```

**Output**

```bash
thought:DockerKata rich$ docker run dd175670ab16
Timmy
```

### Delete the Image (and related container)

**Command**

```bash
docker rmi -f dd175670ab16
```

**Output**

```bash
thought:DockerKata rich$ docker rmi -f dd175670ab16
Deleted: sha256:dd175670ab1602e0c5efd8325a1b7969b24d4c38a629b5615010bf6c721d0209
Deleted: sha256:ad7801c15908ecfe9c15d6a5f37d8acd14e726c6222088c2c110cb5d62a3a20c
Deleted: sha256:a2e52da4f0f75fd2c2f78d202ffeed9bee8ede516fe31ed3af9253490b12dc3e
```

[Previous](16_simple_ruby_image.md) | [Index](README.md) | [Next](18_overriding_envvars.md)
