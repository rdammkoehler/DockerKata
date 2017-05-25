# Commiting Changes 

Docker Documentation References:

[docker commit](https://docs.docker.com/engine/reference/commandline/commit/)

[docker start](https://docs.docker.com/engine/reference/commandline/start/)

[docker stop](https://docs.docker.com/engine/reference/commandline/stop/)

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker exec](https://docs.docker.com/engine/reference/commandline/exec/)

[docker rm](https://docs.docker.com/engine/reference/commandline/rm/)

[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)

### Intent

The purpose of this kata is to familiarize yourself with the process of creating a docker image by commiting changes to a container back to the image.

### Overview

In this exercise we will start an existing container, commit that container to create a new image, list the images available, stop the current container, run the new image (created by the commit) to create a new container, inspect the state of that running container, stop the container, delete the new container and the new image.

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

2 Commit the Container

**Command:**

```bash
docker commit --message 'added vim and simple.txt` docker_katas_nginx 
```

**Output:**

```bash
thought:DockerKata rich$ docker commit --message 'added vim and simple.txt' docker_katas_nginx
sha256:f7d8faf086a6750f2ac5515c92ad66a00b027c844e63f8409d658e7add2258f3
```

3 List Images

**Command:**

```bash
docker images
```

**Output:**

```bash
thought:DockerKata rich$ docker images
REPOSITORY                                   TAG                 IMAGE ID            CREATED             SIZE
<none>                                       <none>              f7d8faf086a6        37 seconds ago      42.2 MB
nginx                                        alpine              f00ab1b3ac6d        2 weeks ago         15.5 MB
```

> Note: The image with REPOSITORY <none> and TAG <none> is the image just created.

4 Stop the current container

**Command:**

```bash
docker stop docker_katas_nginx
```

**Output:**

```bash
docker_katas_nginx
```

5 Run the new image

**Command:**

```bash
docker run --name nginx_vim -d f7d8faf086a6
```

> Note: We're using the IMAGE ID to specify what image we want to run

**Output:**

```bash
thought:DockerKata rich$ docker run --name nginx_vim -d f7d8faf086a6
4b9d7d95acdd213b592d1d49e9f4a85d1022c2e0a8fbb90e852d862c2124a63a
```

6 Inspect the file system of the new container

**Command:**

```bash
docker exec -it nginx_vim ls
```

**Output:**

```bash
thought:DockerKata rich$ docker exec -it nginx_vim ls
bin         home        mnt         run         srv         usr
dev         lib         proc        sbin        sys         var
etc         media       root        simple.txt  tmp
```

7 Stop the new container

**Command:**

```bash
docker stop nginx_vim
```

**Output:**

```bash
thought:DockerKata rich$ docker stop nginx_vim
nginx_vim
```

8 Delete the new container

**Command:**

```bash
docker rm nginx_vim
```

**Output:**

```bash
thought:DockerKata rich$ docker rm nginx_vim
nginx_vim
```

9 Delete the new image (it was silly anyway)

**Command:**

```bash
docker rmi f7d8faf086a6
```

```bash
thought:DockerKata rich$ docker rmi f7d8faf086a6
Deleted: sha256:f7d8faf086a6750f2ac5515c92ad66a00b027c844e63f8409d658e7add2258f3
Deleted: sha256:3a31fabdeccaa2d985d1bf6844db8c9bcb14fe0a1b4663d98b4e891293d4e1fe
```

[Previous](11_change_container_state.md) | [Index](README.md) | [Next](#)
