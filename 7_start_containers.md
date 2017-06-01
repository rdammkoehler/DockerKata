# Start Containers

Docker Documentation References:

[docker start](https://docs.docker.com/engine/reference/commandline/start/)

[docker stop](https://docs.docker.com/engine/reference/commandline/stop/)

##Intent

The purpose of this kata is to familarize yourself with the process of running a container.

##Overview

In this exercise we will use an existing container and run it in the detached mode, we will then stop the container

##Kata Steps

###Start Container

**Command**

```bash
docker start docker_katas_nginx
```

**Output**

```bash
thought:DockerKata rich$ docker start docker_katas_nginx
docker_katas_nginx
```

###Test the running container

**Command**

```bash
open http://localhost:8080
```

Or [click here](http://localhost:8080)

**Output**

![NGINX Screen Shot](screenshots/image_pull_and_run_kata_nginx_verification.png)

###Stop the Container

**Command**

```bash
docker stop docker_katas_nginx
```

**Output**

```bash
thought:DockerKata rich$ docker stop docker_katas_nginx
docker_katas_nginx
```

[Previous](6_named_containers.md) | [Index](README.md) | [Next](8_tag_an_image.md)
