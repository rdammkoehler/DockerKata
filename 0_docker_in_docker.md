# Docker In Docker

Many of the exercises herein can be destructive to your docker environment. If you are so inclined you can run Docker inside of Docker so that you can make changes to environment (even destructive ones) without upsetting your daily routines outside of the Kata exercises. The following instructions provide setup for running Docker Inside of Docker. 

> Throughout the documentaiton we will refer to this Docker In Docker container as *meta-docker*. Each set of instructions will contain notes on how (if possible) you can execute these commands without the *meta-docker* in place, or otherwise point out the differences in behavior you will see.

Documentation References:

[Docker Image](https://hub.docker.com/_/docker/)

## Setup

### Run a Docker Image

#### If this is the first time...
**Command**

```bash
docker run --privileged --name meta-docker -p 17:17 -p 8080:80 -d docker:stable-dind
```

> The network interface ports being opened above are used by some of the katas. We need to publish those in order to complete several of the katas. If you don't know publish those ports, any kata involving using a browser or shell command to talk with the container will fail. Look for instructions in those instances for running the commands outside the *meta-docker*.

> Also note, the command above connects localhost port 17 to the *meta-docker* on port 17, but it connects localhost port 8080 to port 80 on the *meta-docker* based on the assumption that you have something running on port 80 already.

**Output**

```bash
thought:DockerKata rich$ docker run --privileged --name meta-docker -p 17:17 -p 8080:80 -d docker:stable-dind
b7ecc8a2a071c47147af2880b06394678cbe602178dc3f5ca7caca810a5a2871
```

#### If this after the first time...
**Command**

```bash
docker start meta-docker
```

**Output**

```bash
thought:DockerKata rich$ docker start meta-docker
meta-docker
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
