# Fetch Logs From a Container

Docker Documentation References:

[docker logs](https://docs.docker.com/engine/reference/commandline/logs/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker ps](https://docs.docker.com/engine/reference/commandline/ps/)

[docker stop](https://docs.docker.com/engine/reference/commandline/stop/)

[docker rm](https://docs.docker.com/engine/reference/commandline/rm/)

Other documentation:

[`wget`](https://www.gnu.org/software/wget/manual/wget.html)

## Intent

The purpose of this kata is to familiarize yourself with the process of fetching the logs from a running container.

## Overview

In this exercise we will start a container and interact with it through a web browser, causing it to create log output. We will then get log output using a docker command. We will then stop the container.

## Kata Steps

### Start a Container

**Command**

```bash
docker run -p 80:80 -d nginx:alpine
```

**Output**

```bash
/ # docker run -p 80:80 -d nginx:alpine
e4920d2b5c3c085203f53758735b6d3d9ba2d705d5e431219553006f9e61de6a
```

### List Running Containers

**Command**

```bash
docker ps
```

**Output**

```bash
/ # docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                NAMES
e4920d2b5c3c        nginx:alpine        "nginx -g 'daemon ..."   16 seconds ago      Up 14 seconds       0.0.0.0:80->80/tcp   affectionate_kalam
```

> You will need the `CONTAINER ID` or `NAMES` value for the next step

### Check the logs of the container

**Command**

```bash
docker logs affectionate_kalam
```

**Output**

```bash
/ # docker logs affectionate_kalam
```

> Because there have been no interactions with the container you should get no resluts, nothing has been logged yet

### Visit the Web Server

**Command**

```bash
wget localhost
```

**Output**

```bash
/ # wget localhost
Connecting to localhost (127.0.0.1:80)
index.html           100% |*************************************************************************************************************|   612   0:00:00 ETA
```

> Note: You can also use your browser to visit [http://localhost:8080](http://localhost:8080) to create log enteries. If you are outside the *meta-docker* use port [80](http://localhost:80).

### Check the Logs of the container

**Command**

```bash
docker logs affectionate_kalam
```

**Output**

```bash
/ # docker logs affectionate_kalam
172.17.0.1 - - [06/Jun/2017:04:54:02 +0000] "GET / HTTP/1.1" 304 0 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36" "-"
2017/06/06 04:54:03 [error] 6#6: *1 open() "/usr/share/nginx/html/favicon.ico" failed (2: No such file or directory), client: 172.17.0.1, server: localhost, request: "GET /favicon.ico HTTP/1.1", host: "localhost:8080", referrer: "http://localhost:8080/"
172.17.0.1 - - [06/Jun/2017:04:54:03 +0000] "GET /favicon.ico HTTP/1.1" 404 571 "http://localhost:8080/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36" "-"
2017/06/06 04:54:04 [error] 6#6: *1 open() "/usr/share/nginx/html/favicon.ico" failed (2: No such file or directory), client: 172.17.0.1, server: localhost, request: "GET /favicon.ico HTTP/1.1", host: "localhost:8080", referrer: "http://localhost:8080/"
172.17.0.1 - - [06/Jun/2017:04:54:04 +0000] "GET /favicon.ico HTTP/1.1" 404 571 "http://localhost:8080/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36" "-"
172.17.0.1 - - [06/Jun/2017:04:54:04 +0000] "GET / HTTP/1.1" 304 0 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36" "-"
172.17.0.1 - - [06/Jun/2017:04:54:04 +0000] "GET /favicon.ico HTTP/1.1" 404 571 "http://localhost:8080/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36" "-"
2017/06/06 04:54:04 [error] 6#6: *1 open() "/usr/share/nginx/html/favicon.ico" failed (2: No such file or directory), client: 172.17.0.1, server: localhost, request: "GET /favicon.ico HTTP/1.1", host: "localhost:8080", referrer: "http://localhost:8080/"
2017/06/06 04:54:05 [error] 6#6: *1 open() "/usr/share/nginx/html/favicon.ico" failed (2: No such file or directory), client: 172.17.0.1, server: localhost, request: "GET /favicon.ico HTTP/1.1", host: "localhost:8080", referrer: "http://localhost:8080/"
172.17.0.1 - - [06/Jun/2017:04:54:05 +0000] "GET /favicon.ico HTTP/1.1" 404 571 "http://localhost:8080/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36" "-"
```

### Stop the container

**Command**

```bash
docker stop affectionate_kalam
```

**Output**

```bash
/ # docker stop affectionate_kalam
affectionate_kalam
```

[Previous](28_remove_volume.md) | [Index](README.md) | [Next](30_rename_container.md)
