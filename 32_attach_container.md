# Attach to a Running Container

Docker Documentation References:

[docker exec](https://docs.docker.com/engine/reference/commandline/exec/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker stop](https://docs.docker.com/engine/reference/commandline/stop/)

[docker rm](https://docs.docker.com/engine/reference/commandline/rm/)

## Intent

The intent of this exercise it to familiarize yourself with the `exec` command, specifically so you can connect to a running container with a shell.

## Overview

In this exercise we will create a container running detached. Then we will use `exec` to start a shell on that container and run some commands. We will then exit the shell, disconnecting us from the container. Finally, we will stop the container and remove it.

## Kata Steps

### Create a container

**Command**

```bash
docker run -d nginx:alpine
```

**Output**

```bash
/ # docker run -d nginx:alpine
381c2c925259a8774f78e77f23e4f477b1206eb3bf847c306b21666b4e92f917
```

### Attach to the Container uisng `sh`

**Command**

```bash
docker exec -it 381c2c925259a8774f78e77f23e4f477b1206eb3bf847c306b21666b4e92f917 sh
```

**Output**

```bash
/ # docker exec -it 381c2c925259a8774f78e77f23e4f477b1206eb3bf847c306b21666b4e92f917 sh
```

#### Run some commands inside the container

**Command**

```bash
hostname
```

**Output**

```bash
/ # hostname
381c2c925259
```

### Disconect from the contianer

**Command**

```bash
exit
```

**Output**

```bash
/ # exit
```

### Stop the Container

**Command**

```bash
docker stop 381c2c925259a8774f78e77f23e4f477b1206eb3bf847c306b21666b4e92f917
```

**Output**

```bash
/ # docker stop 381c2c925259a8774f78e77f23e4f477b1206eb3bf847c306b21666b4e92f917
381c2c925259a8774f78e77f23e4f477b1206eb3bf847c306b21666b4e92f917
```

### Delete the container

**Command**

```bash
docker rm 381c2c925259a8774f78e77f23e4f477b1206eb3bf847c306b21666b4e92f917
```

**Output**

```bash
/ # docker rm 381c2c925259a8774f78e77f23e4f477b1206eb3bf847c306b21666b4e92f917
381c2c925259a8774f78e77f23e4f477b1206eb3bf847c306b21666b4e92f917
```


[Previous](31_restart_container.md) | [Index](README.md) | [Next](33_create_container.md)
