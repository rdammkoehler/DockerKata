# List the History of an Image

Docker Documentation References:

[docker history](https://docs.docker.com/engine/reference/commandline/history/)

## Intent

The intent of this exercise it to familiarize yourself with how to get the history of an image.

## Overview

In this exercise we will get the history of the `nginx:alpine` image.

## Kata Steps

### Get Image History

**Command**

```bash
docker history nginx:alpine
```

**Output**

```bash
/ # docker history nginx:alpine
IMAGE               CREATED             CREATED BY                                      SIZE                COMMENT
7ebd6770d0d6        6 days ago          /bin/sh -c #(nop)  CMD ["nginx" "-g" "daem...   0 B
<missing>           6 days ago          /bin/sh -c #(nop)  STOPSIGNAL [SIGTERM]         0 B
<missing>           6 days ago          /bin/sh -c #(nop)  EXPOSE 80/tcp                0 B
<missing>           6 days ago          /bin/sh -c #(nop) COPY file:d15ceb73c6ea77...   1.1 kB
<missing>           6 days ago          /bin/sh -c #(nop) COPY file:af94db45bb7e4b...   643 B
<missing>           6 days ago          /bin/sh -c GPG_KEYS=B0F4253373F8F6F510D421...   11.5 MB
<missing>           6 days ago          /bin/sh -c #(nop)  ENV NGINX_VERSION=1.13.1     0 B
<missing>           6 days ago          /bin/sh -c #(nop)  MAINTAINER NGINX Docker...   0 B
<missing>           11 days ago         /bin/sh -c #(nop)  CMD ["/bin/sh"]              0 B
<missing>           11 days ago         /bin/sh -c #(nop) ADD file:df15515197b1837...   3.98 MB
```

[Previous](33_create_container.md) | [Index](README.md) | [Next](35_system_info.md)
