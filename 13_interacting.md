# Interacting With Containers

Docker Documentation References:

[docker exec](https://docs.docker.com/engine/reference/commandline/exec/)

### Intent

The purpose of this kata is to familiarize yourself with the process of executing interactive commands on a running container.

### Overview

In this exerciese we will start a container and open an interactive shell where we can execute arbitrary commands against the running container. We will then stop the container.

### Kata Steps

1 Start the Container

**Command:**

```bash
docker start docker_katas_nginx
```

**Output:**

```bash
thought:DockerKata rich$ docker start docker_katas_nginx
docker_katas_nginx
```

2 Open a Shell on the container

**Command:**

```bash
docker exec -it docker_katas_nginx sh
```

**Output:**

```bash
thought:DockerKata rich$ docker exec -it docker_katas_nginx sh
/ #
```

> Note: Your are now in a shell window on the Container

3 Interact with the Container

**Command:**

```sh
ps -ef
```

**Output:**

```sh
/ # ps -ef
PID   USER     TIME   COMMAND
    1 root       0:00 nginx: master process nginx -g daemon off;
    6 nginx      0:00 nginx: worker process
    7 root       0:00 sh
   13 root       0:00 ps -ef
```

**Command:**

```sh
hostname
```

**Output:**

```sh
/ # hostname
52450ca5b4a9
```

**Command:**

```sh
exit
```

**Output:**

```bash
/ # exit
thought:DockerKata rich$
```

4 Stop the current container

**Command:**

```bash
docker stop docker_katas_nginx
```

**Output:**

```bash
docker_katas_nginx
```


[Previous](12_commit_changes.md) | [Index](README.md) | [Next](#)
