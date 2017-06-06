# Change between Remotes

Docker Documentation References:

[docker login](https://docs.docker.com/engine/reference/commandline/login/)

[docker logout](https://docs.docker.com/engine/reference/commandline/logout/)

## Intent

The internet of this exercise is to understand how to change remote repositories. 

## Overview

In the exercise we will login to Docker HUB and then change to a private repository and then back to Docker HUB.

## Kata Steps

### Login to Docker

**Command**

```bash
docker login --password ************ --username rdammkoehler https://index.docker.io/v1/
```

**Output**

```bash
/ # docker login --password ************ --username rdammkoehler https://index.docker.io/v1/
Login Succeeded
```

### Change Repositories

**Command**

```bash
docker login richsreg.azurecr.io --username richsreg --password ************
```

**Output**

```bash
/ # docker login richsreg.azurecr.io --username richsreg --password ************
Login Succeeded
```

### Login to Docker

**Command**

```bash
docker login --password ************ --username rdammkoehler https://index.docker.io/v1/
```

**Output**

```bash
/ # docker login --password ************ --username rdammkoehler https://index.docker.io/v1/
Login Succeeded
```

[Previous](38_logout.md) | [Index](README.md) | [Next](40_stats.md)
