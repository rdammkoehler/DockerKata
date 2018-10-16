# Defining Your Network Interface

Docker Documentation References:

[Dockerfile](https://docs.docker.com/engine/reference/builder/)

[docker build](https://docs.docker.com/engine/reference/commandline/build/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)

Other Documentation:

[fortune](https://pkgs.alpinelinux.org/package/v3.6/community/x86_64/fortune)

[nc](http://man.openbsd.org/nc)


## Intent

The purpose of this kata is to familiarize yourself with the process of exposing a network interface of a docker image.

## Overview

In this exercise, we will create a Dockerfile and expose a network port in the definition. We will add a service to serve data from that port. We will then build the docker image and run it. Finally we will test that our network service is operating as expected. We will then stop the Container and remove the image from our repository.

## Kata Steps

### Create a `Dockerfile`

Use and editor to create a file named sh_qotd_Dockerfile, or copy the [sh_qotd_Dockerfile](sh_qotd_Dockerfile) from this repository.

The file should contain the following

```Dockerfile
FROM alpine:3.6
MAINTAINER rpd@noradltd.com

RUN apk update \
    && apk add fortune

EXPOSE 17

ENTRYPOINT [ "nc", "-lk", "-p", "17", "-e", "fortune" ]
```

### Build the Image

**Command**

```bash
docker build -t qotd:latest -f sh_qotd_Dockerfile .
```

**Output**

```bash
thought:DockerKata rich$ docker build -t qotd:latest -f sh_qotd_Dockerfile .
Sending build context to Docker daemon 548.9 kB
Step 1/5 : FROM alpine:3.6
 ---> a41a7446062d
Step 2/5 : MAINTAINER rpd@noradltd.com
 ---> Running in 9b08c30f814c
 ---> 3ee4f80b3f4a
Removing intermediate container 9b08c30f814c
Step 3/5 : RUN apk update     && apk add fortune
 ---> Running in 4404ceb1c72c
fetch http://dl-cdn.alpinelinux.org/alpine/v3.6/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.6/community/x86_64/APKINDEX.tar.gz
v3.6.0-25-gbc37d83ebc [http://dl-cdn.alpinelinux.org/alpine/v3.6/main]
v3.6.0-24-gd2b9ac4f2d [http://dl-cdn.alpinelinux.org/alpine/v3.6/community]
OK: 8429 distinct packages available
(1/2) Installing libbsd (0.8.3-r3)
(2/2) Installing fortune (0.1-r0)
Executing busybox-1.26.2-r4.trigger
OK: 7 MiB in 13 packages
 ---> f026ffbf5a4a
Removing intermediate container 4404ceb1c72c
Step 4/5 : EXPOSE 17
 ---> Running in 1f67491d47f3
 ---> 1de02f099bb3
Removing intermediate container 1f67491d47f3
Step 5/5 : ENTRYPOINT nc -lk -p 17 -e fortune
 ---> Running in c1d7d16760e9
 ---> bd9a638a435f
Removing intermediate container c1d7d16760e9
Successfully built bd9a638a435f
```

### Run the Image

**Command**

```bash
docker run -p 17:17 -d qotd:latest
```

**Output**

```bash
thought:DockerKata rich$ docker run -p 17:17 -d qotd:latest
899c09320554ed310815f784bc47b23e96c3578f228c5b6699c3e78c5e96a57c
```

### Test the Container

**Command**

```bash
nc localhost 17
```

**Output**

```bash
thought:DockerKata rich$ nc localhost 17
Whenever you find that you are on the side of the majority,
it is time to reform.
                -- Mark Twain
```

### List Running Containers

**Command**

```bash
docker ps
```

**Output**

```bash
thought:DockerKata rich$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                NAMES
6156436ef41d        qotd:latest         "nc -lk -p 17 -e f..."   12 seconds ago      Up 11 seconds       0.0.0.0:17->17/tcp   happy_stallman
```

### Stop the Container

**Command**

```bash
docker stop happy_stallman
```

**Output**

```bash
thought:DockerKata rich$ docker stop happy_stallman
happy_stallman
```

### Remove the image

**Command**

```bash
docker rmi -f qotd:latest
```

**Output**

```bash
thought:DockerKata rich$ docker rmi -f qotd:latest
Untagged: qotd:latest
Deleted: sha256:bd9a638a435f366fd6fbfc6260966665c6749a2c223e7b15cd4f944fe098eef0
Deleted: sha256:1de02f099bb30462529b3f93a861b94f4f09cd00d8fcd0eda7e121a9d725063b
Deleted: sha256:f026ffbf5a4a2c63026c508c0b09c48e4bf5ac2a8c4c9c05940408a90067c240
Deleted: sha256:3ee4f80b3f4a1372ec4d642a9f9c0bb4f13e71dcd0d64f7ae5a55872c4bc28d7
```


[Previous](20_mounting_volumes.md) | [Index](README.md) | [Next](22_define_volume.md)
