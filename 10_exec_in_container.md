# Execute Command In Container

Docker Documentation References:

[docker exec](https://docs.docker.com/engine/reference/commandline/exec/)

### Intent

The purpose of this kata is to familiarize yourself with the process of executing commands inside an active docker container.

### Overview

In this exeercise we will start a container and execute the `ps` command on the running container and then stop the container.

### Kata Steps

#### Start the Container

**Command**

```bash
docker start docker_katas_nginx
```

**Output**

```bash
thought:DockerKata rich$ docker start docker_katas_nginx
docker_katas_nginx
```

#### Execute the `ps` command

**Command**

```bash
docker exec docker_katas_nginx ps
```

**Output**

```bash
thought:DockerKata rich$ docker exec docker_katas_nginx ps
PID   USER     TIME   COMMAND
    1 root       0:00 nginx: master process nginx -g daemon off;
    7 nginx      0:00 nginx: worker process
    8 root       0:00 ps
```

#### Stop the Container

**Command**

```bash
docker stop docker_katas_nginx
```

**Output**

```bash
thought:DockerKata rich$ docker stop docker_katas_nginx
docker_katas_nginx
```

[Previous](9_delete_image_by_tag.md) | [Index](README.md) | [Next](11_change_container_state.md)
