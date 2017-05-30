# Create An Image for a Ruby Application

Docker Documentation References:

[Dockerfile](https://docs.docker.com/engine/reference/builder/)

[docker build](https://docs.docker.com/engine/reference/commandline/build/)

[docker run](https://docs.docker.com/engine/reference/commandline/run/)

[docker images](https://docs.docker.com/engine/reference/commandline/images/)

[docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)

Other Documentation References:

[Ruby Language](https://www.ruby-lang.org)

### Intent

The purpose of this kata is to familiarize yourself with the process of creating  the simplest possible image for running a ruby application.

### Overivew

In this exercise we will create a simple Ruby application and place it in a Docker Image. We will then run that image. When we are done we will remove the image and its associated containers.

### Kata Steps

##### Create a Python Application

**Command**:

Use an editor to create a file named [hello_world.rb](hello_world.rb), or use the file contained in this repository

The file should contain the following code

```ruby
puts 'Hello World'
```

##### Test the application

**Command:**

```bash
ruby hello_world.rb
```

**Output:**

```bash
thought:DockerKata rich$ ruby hello_world.rb
Hello World
```

##### Create a `Dockerfile`

Use an editor to create a file name python_hello_world_Dockerfile, or copy the [python_hello_world_Dockerfile](python_hello_world_Dockerfile) from this repository.

The file should contian the following

```Dockerfile
FROM ruby:alpine
MAINTAINER rpd@noradltd.com

COPY hello_world.rb /

ENTRYPOINT [ "ruby", "hello_world.rb" ]
```

##### Build the Image

**Command:**

```bash
docker build -f ruby_hello_world_Dockerfile .
```

**Output:**

```bash
thought:DockerKata rich$ docker build -f ruby_hello_world_Dockerfile .
Sending build context to Docker daemon 410.1 kB
Step 1/4 : FROM ruby:alpine
alpine: Pulling from library/ruby
79650cf9cc01: Pull complete
6ed882a02057: Pull complete
7285d5575114: Pull complete
d441eef8a308: Pull complete
25cbb501c00e: Pull complete
Digest: sha256:ead6b812ae745761a90c8900eae672b8d7e952e3464a92f3e977b073e4f91f1a
Status: Downloaded newer image for ruby:alpine
 ---> 3db0e32b7207
Step 2/4 : MAINTAINER rpd@noradltd.com
 ---> Running in a7d7ed8af293
 ---> aacee134dc3b
Removing intermediate container a7d7ed8af293
Step 3/4 : COPY hello_world.rb /
 ---> 12ea97af7522
Removing intermediate container d114cf088595
Step 4/4 : ENTRYPOINT ruby hello_world.rb
 ---> Running in 00365bcc4a46
 ---> cc70f6402870
Removing intermediate container 00365bcc4a46
Successfully built cc70f6402870
```

##### List Images

**Command:**

```bash
docker images
```

**Output:**

```bash
thought:DockerKata rich$ docker images
REPOSITORY                                   TAG                 IMAGE ID            CREATED             SIZE
<none>                                       <none>              cc70f6402870        54 seconds ago      61.2 MB
```

> Note: We will use the `IMAGE ID` which will differ from machine to machine, so you must select what is on your computer for the next two steps.

##### Run the Image

**Command:**

```bash
docker run 167b6bbcdc92
```

**Output:**

```bash
thought:DockerKata rich$ docker run cc70f6402870
Hello World
```

##### Delete the Image (and related container)

**Command:**

```bash
docker rmi -f cc70f6402870
```

**Output:**

```bash
thought:DockerKata rich$ docker rmi -f cc70f6402870
Deleted: sha256:cc70f64028700dbd0fbe46c37ee5b33b7933abd0c6220fed840169c65d0a8a5e
Deleted: sha256:12ea97af75224f4e63decc5ef01c6bf231730aa608b9d01ebca9f3a4eb801c3b
Deleted: sha256:aacee134dc3be0bd28b98f1742278c667c34310f9d43cd254d98143f1d1b37bd
```

[Previous](15_simple_python_image.md) | [Index](README.md) | [Next](#)
