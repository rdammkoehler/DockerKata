# Change The State of The Container

> WARNING: This Kata is behaving strangely in when using the [`meta-docker`](0_docker_in_docker.md) approach. Be warned that your container might freeze up.

Docker Documentation References:

[docker exec](https://docs.docker.com/engine/reference/commandline/exec/)

[docker start](https://docs.docker.com/engine/reference/commandline/start/)

[docker stop](https://docs.docker.com/engine/reference/commandline/stop/)

Other References:

[apk](https://wiki.alpinelinux.org/wiki/Alpine_Linux_package_management)

[vim](http://www.vim.org/)

## Intent

The purpose of this kata is to familarize yourself with the notion that the containers disk and states is independet of the image that created it.

## Overview

In this exercise we will start a container, install the `vim` editor, create a document, demonstrate that the document is saved on the containers disk, stop and restart the container, and demonstrate that the document is still saved on the disk. Finally we will stop the container again.

## Kata Steps

### Start the Container

**Command**

```bash
docker start docker_katas_nginx
```

**Output**

```bash
thought:DockerKata rich$ docker start docker_katas_nginx
docker_katas_nginx
```

### Execute the `apk update` command

> Note: This updates the images list of available packages to install

**Command**

```bash
docker exec docker_katas_nginx apk update
```

**Output**

```bash
thought:DockerKata rich$ docker exec docker_katas_nginx apk update
fetch http://dl-cdn.alpinelinux.org/alpine/v3.5/main/x86_64/APKINDEX.tar.gz
fetch http://dl-cdn.alpinelinux.org/alpine/v3.5/community/x86_64/APKINDEX.tar.gz
v3.5.2-84-gf3deae790a [http://dl-cdn.alpinelinux.org/alpine/v3.5/main]
v3.5.2-81-gf4d50b1370 [http://dl-cdn.alpinelinux.org/alpine/v3.5/community]
OK: 7962 distinct packages available
```

### Execute the `apk add vim` command

> Note: This installs vim on the running container

**Command**

```bash
docker exec docker_katas_nginx apk add vim
```

**Output**

```bash
thought:DockerKata rich$ docker exec docker_katas_nginx apk add vim
(1/5) Installing lua5.2-libs (5.2.4-r2)
(2/5) Installing ncurses-terminfo-base (6.0-r7)
(3/5) Installing ncurses-terminfo (6.0-r7)
(4/5) Installing ncurses-libs (6.0-r7)
(5/5) Installing vim (8.0.0329-r0)
Executing busybox-1.25.1-r0.trigger
OK: 45 MiB in 31 packages
```

### Use `vim` on the container

**Command**

```bash
docker exec -it docker_katas_nginx vim
```

> Note: We will disucss the -it option on exec in a later step

**Output**

* You should find yourself in a vim session. 
* Insert some text and save the file using `<ESC> :w simple.txt`
* Then exit `vim` using `<ESC> :q`

### List files on the container to see the document you created in the prevoius step

**Command**

```bash
docker exec docker_katas_nginx ls
```

**Output**

```bash
thought:DockerKata rich$ docker exec -it docker_katas_nginx ls
bin         home        mnt         run         srv         usr
dev         lib         proc        sbin        sys         var
etc         media       root        simple.txt  tmp
```

### Stop the Container

**Command**

```bash
docker stop docker_katas_nginx
```

**Output**

```bash
thought:DockerKata rich$ docker stop docker_katas_nginx
docker_katas_nginx
```

### Restart the Container

**Command**

```bash
docker start docker_katas_nginx
```

**Output**

```bash
thought:DockerKata rich$ docker start docker_katas_nginx
docker_katas_nginx
```

### List files on the container to see the document you created in the prevoius step

**Command**

```bash
docker exec docker_katas_nginx ls
```

**Output**

```bash
thought:DockerKata rich$ docker exec -it docker_katas_nginx ls
bin         home        mnt         run         srv         usr
dev         lib         proc        sbin        sys         var
etc         media       root        simple.txt  tmp
```

> Note: that your file persisted in the conainer between stops and starts, however the image used to create this container does not contain the changes (installation of vim and the simple.txt file), so additional containers created from that image will not have these things. In the next kata we will demonstrate how to create an image from a container.

### Stop the Container

**Command**

```bash
docker stop docker_katas_nginx
```

**Output**

```bash
thought:DockerKata rich$ docker stop docker_katas_nginx
docker_katas_nginx
```

[Previous](10_exec_in_container.md) | [Index](README.md) | [Next](12_commit_changes.md)
