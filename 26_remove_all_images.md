# Remove all Images

Docker Documentation References:

[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

Other documentation:

[Melissa Anderson - How To Remove Docker Images, Containers, and Volumes](https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes)

## Intent

The purpose of this kata is to familiarize yourself with the process of removing all images from your local docker repository.

> WARNING: This will delete all of your images! Do NOT execute this Kata against your local configuration unless you are willing to recreate/pull all of your images.

## Overview

In this exercise, we will list all of the images in our local repository, then we will delete them all, and finally we will show that we have no images in our local repository.

## Kata Steps

### List All Images

**Command**

```bash
docker images --all
```

**Output**

```bash
thought:DockerKata rich$ docker images --all
REPOSITORY                                   TAG                 IMAGE ID            CREATED             SIZE
nginx                                        stable-alpine       2ee4da85fb49        2 days ago          15.5 MB
nginx                                        alpine              7ebd6770d0d6        2 days ago          15.5 MB
alpine                                       3.6                 a41a7446062d        6 days ago          3.97 MB
```

### Delete All Images

> WARNING: This will delete all of your images! Do NOT execute this Kata against your local configuration unless you are willing to recreate/pull all of your images.

**Command**

```bash
docker rmi --force $(docker images --all --quiet)
```

> WARNING: This will delete all of your images! Do NOT execute this Kata against your local configuration unless you are willing to recreate/pull all of your images.

**Output**

```bash
thought:DockerKata rich$ docker rmi --force $(docker images --all --quiet)
Untagged: nginx:stable-alpine
Untagged: nginx@sha256:d69b66b23458974804e0f19a6585249d4e9c30e52462df8c7a29381cd598ba20
Deleted: sha256:2ee4da85fb49942a03604295a84e5fe9f9b1d2ec7d0a21d65870e67ce2a06525
Deleted: sha256:dd86b86573e6949e4eedf71aee25d4c74af92a022603207a771afc672fcbabab
Deleted: sha256:7a5a9d824b38d220dda1847820c08cd708e951b156d5d716bf069795b542e866
Deleted: sha256:6156d5aec195fe3cb79b45b9f9ef94b534eed622d121855e69996f6ec6130ce0
Untagged: nginx:alpine
Untagged: nginx@sha256:f36b1e2a2b62a05b25049b2ec09df7e3181e3e24c5758350578bfe1ee594176f
Deleted: sha256:7ebd6770d0d68ea8d118e1208de6d433d6f0cb4e4be83d768346f737e6808177
Deleted: sha256:1c8b3362eef2a39e9a6a356ed7e71e6a3bc8ca21aedade5f93d8eab094a828c6
Deleted: sha256:063754ba1996825a5246179521bd62087192bfbdf6a401951da4be648b982dc8
Deleted: sha256:b952803b0d306dcc5f729bd9259012289a0177201bf4cc87761f79e7c907a2a0
Deleted: sha256:ff143e5bce0a1cb61df9bc93a77241f48592b26d7ae71229dc55bb87eba09531
Untagged: alpine:3.6
Untagged: alpine@sha256:0b94d1d1b5eb130dd0253374552445b39470653fb1a1ec2d81490948876e462c
Deleted: sha256:a41a7446062d197dd4b21b38122dcc7b2399deb0750c4110925a7dd37c80f118
Untagged: ruby:alpine
Untagged: ruby@sha256:ead6b812ae745761a90c8900eae672b8d7e952e3464a92f3e977b073e4f91f1a
Deleted: sha256:3db0e32b72073512f5e1f40e13b3858bfdf932490229dddc4b24b4e1d19b8f22
Deleted: sha256:8f9d58aaf8bbe61864f82a0f3aa093f08886a8e00dc24886db9ac9c21df37a31
Deleted: sha256:584c1d56487e42b15d07f33f3a0047dfeede5c03939d86da4a2abe5c0988333a
Deleted: sha256:44e952684644752300537b0eba768d9832d4daa07f53ec87672f16084d890f38
Deleted: sha256:4c46f2b5d2b84aee57975fc2f806ac52f3c5532f80067679c7030bde4b768241
Deleted: sha256:ba2cc2690e31f63847e4bc0d266b354f8f11dc04474d45d44312ff70edae9c98
```

### List All Images

**Command**

```bash
docker images -a
```

**Output**

```bash
thought:DockerKata rich$ docker images -a
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
```

[Previous](25_remove_dangling_images.md) | [Index](README.md) | [Next](27_list_volumes.md)
