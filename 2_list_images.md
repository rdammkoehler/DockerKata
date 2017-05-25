# List Images

Docker Documentation References:

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

### Intent

The purpose of this kata is to familarize yourself with the process of listing existing images in your local docker configuration.

### Overview

In this exercise we will list the images on our local machine. We should see one image from the [previous exercise](1_pull_and_run_image.md). Later we will delete this image.

### Kata Steps

1 List Images

**Command:**

```bash
docker images
```

**Output:**

```bash
thought:DockerKata rich$ docker images
REPOSITORY                                   TAG                 IMAGE ID            CREATED             SIZE
nginx                                        alpine              f00ab1b3ac6d        2 weeks ago         15.5 MB
```

[Previous](1_pull_and_run_image.md) | [Index](README.md) | [Next](3_list_containers.md)
