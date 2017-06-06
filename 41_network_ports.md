# List Network Interface Ports

Docker Documentation References:

[docker port](https://docs.docker.com/engine/reference/commandline/port/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker stop](https://docs.docker.com/engine/reference/commandline/stop/)

[docker rm](https://docs.docker.com/engine/reference/commandline/rm/)

## Intent

The intent of this kata is to learn how to inspect the network interface exposed by a docker container.


## Overview

In this exercise we will start a container, list its network interface ports, and then stop and remove the container.

## Kata Steps

### Start a Container

**Command**

```bash
docker run -p 80:80 -d nginx:alpine
```

**Output**

```bash
/ # docker run -p 80:80 -d nginx:alpine
d2caf9f4806bea6b82a6568ffcc307709960d9d9ab18451ef7cec37e8764c616
```

### List Network Interface Ports

**Command**

```bash
docker port $(docker ps -q)
```

**Output**

```bash
/ # docker port $(docker ps -q)
80/tcp -> 0.0.0.0:80
```

### Stop the Container

**Command**

```bash
docker stop $(docker ps -q)
```

**Output**

```bash
/ # docker stop $(docker ps -q)
d2caf9f4806b```

### Remove the Container

**Command**

```bash
docker rm $(docker ps -qa)
```

**Output**

```bash
/ # docker rm $(docker ps -qa)
d2caf9f4806b
42263eb21a32
```

[Previous](40_stats.md) | [Index](README.md) | [Next](42_pause_container.md)
