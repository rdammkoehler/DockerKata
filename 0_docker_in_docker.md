# Docker In Docker

Many of the exercises herein can be destructive to your docker environment. If you are so inclined you can run Docker inside of Docker so that you can make changes to environment (even destructive ones) without upsetting your daily routines outside of the Kata exercises. The following instructions provide setup for running Docker Inside of Docker. 

Documentation References:

[Docker Image](https://hub.docker.com/_/docker/)

## Setup

### Run a Docker Image

**Command**

```bash
docker run --privileged --name meta-docker -p 17:17 -p 8080:80 -d docker:stable-dind
```

### Shell Into the Docker Container

**Command**
```bash
docker exec -it meta-docker sh
```

### Do One or More Katas

[Index of Katas](README.md)

### Exit the Shell

**Command**

```bash
exit
```

### Stop the `meta-docker` Container

**Command**

```bash
docker stop meta-docker
```
