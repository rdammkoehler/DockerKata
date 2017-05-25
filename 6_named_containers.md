# Named Containers

Docker Documenation References:

[docker create](https://docs.docker.com/engine/reference/commandline/create/)

[docker pull](https://docs.docker.com/engine/reference/commandline/pull/)

[docker ps](https://docs.docker.com/engine/reference/commandline/ps/)

### Intent

The purpose of this kata is to familarize yourself with the process of creating a container with a specific name.

### Overview

In this exercise we will pull and image and create a container with a specific name using that image.

### Kata Steps

1 Pull a simple image, nginx:alpine

**Command:**

```bash
docker pull nginx:alpine
```

**Output:**

```bash
thought:DockerKata rich$ docker pull nginx:alpine
alpine: Pulling from library/nginx
cfc728c1c558: Pull complete
59e0e447b6ec: Pull complete
1c89b5c5bd38: Pull complete
584d454ad7fd: Pull complete
Digest: sha256:33eb1ed1e802d4f71e52421f56af028cdf12bb3bfff5affeaf5bf0e328ffa1bc
Status: Downloaded newer image for nginx:alpine
```

2 Create Named Container

**Command:**

```bash
docker create --name docker_katas_nginx nginx:alpine
```

**Output:**

```bash
thought:DockerKata rich$ docker create --name docker_katas_nginx nginx:alpine
52450ca5b4a9926bb18594fac1c6677fe50c99af995d9720ace45b81dd88bc0e
```

3 List All Containers

**Command:**

```bash
docker ps -a
```

**Output:**

```bash
thought:DockerKata rich$ docker ps -a
CONTAINER ID        IMAGE                          COMMAND                  CREATED             STATUS                     PORTS               NAMES
52450ca5b4a9        nginx:alpine                   "nginx -g 'daemon ..."   37 seconds ago      Created                                        docker_katas_nginx
```

[Previous](5_delete_image.md) | [Index](README.md) | [Next](7_start_containers.md)
