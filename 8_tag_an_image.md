# Tag an Image

Docker Documentation References:

[docker tag](https://docs.docker.com/engine/reference/commandline/tag/)

[docker pull](https://docs.docker.com/engine/reference/commandline/pull/)

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

### Intent

The purpose of this kata is to familarize yourself with the process of tagging an image.

### Overview

In this exercise we will pull and image for the NGINX Web Server and add a custom tag.

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

2 Tag the Image

**Command:**

```bash
docker tag nginx:alpine nginx:mine
```

> Note: the use of mine as a tag is a totally arbitrary value for demonstration purposes

3 Inspect your Images

**Command:**

```bash
docker images
```

**Output:**

```bash
thought:DockerKata rich$ docker images
REPOSITORY                                   TAG                 IMAGE ID            CREATED             SIZE
nginx                                        alpine              f00ab1b3ac6d        2 weeks ago         15.5 MB
nginx                                        mine                f00ab1b3ac6d        2 weeks ago         15.5 MB
```

[Previous](7_start_containers.md) | [Index](README.md) | [Next](9_delete_image_by_tag.md)
