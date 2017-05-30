# Overriding Environment Variables

Docker Documentation References:

[Dockerfile](https://docs.docker.com/engine/reference/builder/)

[docker build](https://docs.docker.com/engine/reference/commandline/build/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)


### Intent

The purpose of this kata is to familiarize yourself with the process of overriding an environment variable that was set in the Dockerfile.

### Overview

In this exercise we will create a simple Dockerfile and set an environment variable with will impact the output of the application. We will then delete the image.

### Kata Steps

##### Create a `Dockerfile`

Use and editor to create a file named sh_hello_user_Dockerfile, or copy the [sh_hello_user_Dockerfile](sh_hello_user_Dockerfile) from this repository.

The file should contain the following

```Dockerfile
FROM alpine:3.6
MAINTAINER rpd@noradltd.com

ENV DOCKER_USER_NAME Timmy

ENTRYPOINT [ "sh", "-c", "echo $DOCKER_USER_NAME" ]
```

##### Build the IMage

**Command:**

```bash
docker build -f sh_hello_user_Dockerfile .
```

**Output:**

```bash
thought:DockerKata rich$ docker build -f sh_hello_user_Dockerfile .
Sending build context to Docker daemon 434.2 kB
Step 1/4 : FROM alpine:3.6
 ---> a41a7446062d
Step 2/4 : MAINTAINER rpd@noradltd.com
 ---> Running in a78b6083f640
 ---> dc97dfd78be5
Removing intermediate container a78b6083f640
Step 3/4 : ENV DOCKER_USER_NAME Timmy
 ---> Running in e52461bfa94a
 ---> 56d9cb50cc30
Removing intermediate container e52461bfa94a
Step 4/4 : ENTRYPOINT sh -c echo $DOCKER_USER_NAME
 ---> Running in 72f900e1536b
 ---> 804eb58d237f
Removing intermediate container 72f900e1536b
Successfully built 804eb58d237f
```

##### List Images

**Command:**

```bash
docker images
```

**Output:**

```bash
thought:DockerKata rich$ docker images
REPOSITORY                                   TAG                 IMAGE ID            CREATED             SIZE
<none>                                       <none>              804eb58d237f        3 seconds ago       3.97 MB
```

> Note: We will use the `IMAGE ID` which will differ from machine to machine, so you must select what is on your computer for the next two steps.

##### Run the Image

**Command:**

```bash
docker run --env DOCKER_USER_NAME=$USER 804eb58d237f
```

**Output:**

```bash
thought:DockerKata rich$ docker run --env DOCKER_USER_NAME=$USER 804eb58d237f
rich
```

##### Delete the Image (and related container)

**Command:**

```bash
docker rmi -f dd175670ab16
```

**Output:**

```bash
thought:DockerKata rich$ docker rmi -f dd175670ab16
Deleted: sha256:dd175670ab1602e0c5efd8325a1b7969b24d4c38a629b5615010bf6c721d0209
Deleted: sha256:ad7801c15908ecfe9c15d6a5f37d8acd14e726c6222088c2c110cb5d62a3a20c
Deleted: sha256:a2e52da4f0f75fd2c2f78d202ffeed9bee8ede516fe31ed3af9253490b12dc3e
```


[Previous](17_setting_envvars.md) | [Index](README.md) | [Next](#)
