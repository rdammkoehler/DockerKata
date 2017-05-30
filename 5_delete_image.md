# Delete Image

Docker Documentation References:

[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

### Intent

The purpose of this kata is to familarize yourself with the process of deleting an image from your local docker registry.

### Overview

In this exercies we will list the images on in the local registry and then delete one.

### Kata Steps

##### List Images

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

##### Remove image

**Command:**

```bash
docker rmi f00ab1b3ac6d
```

> Note: We use the IMAGE ID for the listed image to select which image to delete

**Output:**

```bash
thought:DockerKata rich$ docker rmi f00ab1b3ac6d
Untagged: nginx:alpine
Untagged: nginx@sha256:33eb1ed1e802d4f71e52421f56af028cdf12bb3bfff5affeaf5bf0e328ffa1bc
Deleted: sha256:f00ab1b3ac6dc3939160f8e77bcd3eaad2a3cdab227f6b722a886f00ba30cf2f
Deleted: sha256:6dcabd9f3c2eb0c67787c345af26a8067ea1059c6add2f82b48e3202ee5da5d3
Deleted: sha256:c8cca4ddb1b2b8b988f6d0ce0706b03741b1f68a8b496d04d278e525c166e918
Deleted: sha256:dbb2947ff4baf54251b41474675ec80406f4f39014ba2db264c47f35cd9ce32c
Deleted: sha256:e154057080f406372ebecadc0bfb5ff8a7982a0d13823bab1be5b86926c6f860
```

[Previous](4_delete_container.md) | [Index](README.md) | [Next](6_named_containers.md)
