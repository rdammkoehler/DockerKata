# Wait for a Container to Stop

Docker Documentation References:

[]()

## Intent

The intent of this kata is to learn how to wait for a container to shutdown through the Docker CLI

## Overview

In this exercise we will create a container, then execute a shutdown command that waits for the container to stop. We will then remove the continer.

## Kata Steps

### Create a Container

**Command**

```bash
docker run -p 80:80 -d nginx:alpine
```

**Output**

```bash
/ # docker run -p 80:80 -d nginx:alpine
39e01664831135501d866fea47988d0748c204145f33f4713ebab010f246fb1c
```

### Wait for Container

**Command**

```bash
(docker wait $(docker ps -q) && echo 'the container exited') &
```

> This command runs `docker wait` and when it finishes will trigger another command, in this case to echo the string 'the container exited'. All of this is running in the background of your current shell. You could use multiple shells if you wanted to see the interaction without the background processes.

**Output**

```bash
/ # (docker wait $(docker ps -q) && echo 'the container exited') &
```

### Stop the Container

**Command**

```bash
docker stop $(docker ps -q)
```

**Output**

```bash
/ # docker stop $(docker ps -q)
39e016648311
0
the container exited
```

> Did you notice the output? We see the normal hash back from the stop command followed by the output of the wait command (zero) which is the status of the contiainer, and that is followed by the string 'the container exited' from our call above.

### Remove the Container

**Command**

```bash
docker rm $(docker ps -aq)
```

**Output**

```bash
/ # docker rm $(docker ps -aq)
39e016648311
[1]+  Done                       (docker wait $(...) && echo "the container exited")
```

> Note that the operating system also prints out the status of the background job at the end here. That is just the nature of a linux shell.
> 

[Previous](44_update_container_config.md) | [Index](README.md) | [Next](#)
