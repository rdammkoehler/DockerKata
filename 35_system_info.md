# Get Info on Docker

Docker Documentation References:

[docker info](https://docs.docker.com/engine/reference/commandline/info/)

## Intent

The intent of this exercise is to familiarize yourself with getting information about the current docker installation using `docker info`.

## Overview

In this exercise, we will use `docker info` to get information about the current docker environment.

## Kata Steps

### Execute `docker info`

**Command**

```bash
docker info
```

**Output**

```bash
/ # docker info
Containers: 0
 Running: 0
 Paused: 0
 Stopped: 0
Images: 1
Server Version: 17.03.1-ce
Storage Driver: vfs
Logging Driver: json-file
Cgroup Driver: cgroupfs
Plugins:
 Volume: local
 Network: bridge host macvlan null overlay
Swarm: inactive
Runtimes: runc
Default Runtime: runc
Init Binary: docker-init
containerd version: 4ab9917febca54791c5f071a9d1f404867857fcc
runc version: 54296cf40ad8143b62dbcaa1d90e520a2136ddfe
init version: 949e6fa
Security Options:
 seccomp
  Profile: default
Kernel Version: 4.9.27-moby
Operating System: Alpine Linux v3.5 (containerized)
OSType: linux
Architecture: x86_64
CPUs: 4
Total Memory: 1.952 GiB
Name: b7ecc8a2a071
ID: IJZ4:QHWJ:47MY:OAOE:765H:6NXZ:LZCF:XQJ3:V2SD:FWRF:54Y2:ODET
Docker Root Dir: /var/lib/docker
Debug Mode (client): false
Debug Mode (server): false
No Proxy: *.local, 169.254/16
Registry: https://index.docker.io/v1/
WARNING: bridge-nf-call-iptables is disabled
WARNING: bridge-nf-call-ip6tables is disabled
Experimental: false
Insecure Registries:
 127.0.0.0/8
Live Restore Enabled: false
```

[Previous](34_image_history.md) | [Index](README.md) | [Next](36_kill_container.md)
