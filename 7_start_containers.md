# Run Containers

Docker Documentation References:

[]()

### Intent

The purpose of this kata is to familarize yourself with the process of running a container.

### Overview

In this exercise we will use an existing container and run it in the detached mode, we will then stop the container

### Kata Steps

1 Start Container

Command:

```bash
docker start docker_katas_nginx
```

Output:

```bash
thought:DockerKata rich$ docker start docker_katas_nginx
docker_katas_nginx
```

2 Test the running container

Command (in :

```bash
open http://localhost:8080
```

Output:

![NGINX Screen Shot](screenshots/image_pull_and_run_kata_nginx_verification.png)

3 Stop the Container

Command:

```bash
docker stop docker_katas_nginx
```

Output:

```bash
thought:DockerKata rich$ docker stop docker_katas_nginx
docker_katas_nginx
```
