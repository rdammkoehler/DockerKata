# Update a Container Configuration

Docker Documentation References:

[docker update](https://docs.docker.com/engine/reference/commandline/update/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker stop](https://docs.docker.com/engine/reference/commandline/stop/)

[docker rm](https://docs.docker.com/engine/reference/commandline/rm/)

## Intent

The intent of this kata is to understand how to update a containers configuration.

## Overview

In this exercise we will create a container, show the containers stats at runtime, modify its settings, then show the containers stats again. Finally, we will stop and remove the container.

## Kata Steps

### Create a Container

**Command**

```bash
docker run -p 80:80 -d nginx:alpine
```

**Output**

```bash
/ # docker run -p 80:80 -d nginx:alpine
19d948bb72d5984ae6f167a784bc661fc9ada8bf3706b73d0c52b9c609f85e71
```

### Show Stats

**Command**

```bash
docker stats --no-stream
```

**Output**

```bash
/ # docker stats --no-stream
CONTAINER           CPU %               MEM USAGE / LIMIT       MEM %               NET I/O             BLOCK I/O           PIDS
19d948bb72d5        0.00%               1.676 MiB / 1.952 GiB   0.08%               578 B / 578 B       0 B / 0 B           2
```

### Update the Container Configuration

**Command**

```bash
docker update --memory 1Gb --memory-swap 1Gb $(docker ps -aq)
```

**Output**

```bash
/ # docker update --memory 1Gb --memory-swap 1Gb $(docker ps -aq)
19d948bb72d5
```

### Show Stats

**Command**

```bash
docker stats --no-stream
```

**Output**

```bash
/ # docker stats --no-stream
CONTAINER           CPU %               MEM USAGE / LIMIT   MEM %               NET I/O             BLOCK I/O           PIDS
19d948bb72d5        0.00%               1.656 MiB / 1 GiB   0.16%               648 B / 648 B       0 B / 0 B           2
```

### Stop the Container

**Command**

```bash
docker stop $(docker ps -aq)
```

**Output**

```bash
/ # docker stop $(docker ps -aq)
19d948bb72d5
```

### Remove the Container

**Command**

```bash
docker rm $(docker ps -aq)
```

**Output**

```bash
/ # docker rm $(docker ps -aq)
19d948bb72d5
```

[Previous](42_pause_container.md) | [Index](README.md) | [Next](45_wait_for_container.md)
