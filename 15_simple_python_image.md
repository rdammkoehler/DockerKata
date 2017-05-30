# Create An Image for a Python Application

Docker Documentation References:

[]()

### Intent

The purpose of this kata is to familiarize yourself with the process of creating  the simplest possible image for running a python application.

### Overivew

TBD

### Kata Steps

##### Create a Python Application

**Command**:

Use an editor to create a file named [hello_world.py](hello_world.py), or use the file contained in this repository

The file should contain the following code

```python
print('Hello World')
```

##### Test the application

**Command:**

```bash
python hello_world.py
```

**Output:**

```bash
thought:DockerKata rich$ python hello_world.py
Hello World
```

##### Create a `Dockerfile`

Use an editor to create a file name python_hello_world_Dockerfile, or copy the [python_hello_world_Dockerfile](python_hello_world_Dockerfile) from this repository.

The file should contian the following

```Dockerfile
FROM python:alpine
MAINTAINER rpd@noradltd.com

COPY hello_world.py /

ENTRYPOINT [ "python", "hello_world.py" ]
```

##### Build the Image

**Command:**

```bash
docker build -f python_hello_world_Dockerfile .
```

**Output:**

```bash
thought:DockerKata rich$ docker build -f python_hello_world_Dockerfile .
Sending build context to Docker daemon 390.1 kB
Step 1/4 : FROM python:alpine
 ---> cb178ebbf0f2
Step 2/4 : MAINTAINER rpd@noradltd.com
 ---> Using cache
 ---> 3c394b1b607a
Step 3/4 : COPY hello_world.py /
 ---> c3b4d01fefd2
Removing intermediate container c9168e27bf8a
Step 4/4 : ENTRYPOINT python hello_world.py
 ---> Running in 1159a6589c4f
 ---> c5c27efb5127
Removing intermediate container 1159a6589c4f
Successfully built c5c27efb5127
```

##### List Images

**Command:**

```bash
docker images
```

**Output:**

```bash
REPOSITORY                                   TAG                 IMAGE ID            CREATED             SIZE
<none>                                       <none>              167b6bbcdc92        54 seconds ago      88.6 MB
```

> Note: We will use the `IMAGE ID` which will differ from machine to machine, so you must select what is on your computer for the next two steps.

##### Run the Image

**Command:**

```bash
docker run 167b6bbcdc92
```

**Output:**

```bash
thought:DockerKata rich$ docker run 167b6bbcdc92
Hello World
```

##### Delete the Image (and related container)

**Command:**

```bash
docker rmi -f 167b6bbcdc92
```

**Output:**

```bash
thought:DockerKata rich$ docker rmi -f 167b6bbcdc92
Deleted: sha256:167b6bbcdc923383d418579e9aa9e91e455aa3f32af440223d4b4b8f797d7b02
Deleted: sha256:9966dcc31ceb9c1ba920c4fcbf45da6cda2d3fae2157dc017d51998312ac6bd2
```

[Previous](14_pushing_images.md) | [Index](README.md) | [Next](#)
