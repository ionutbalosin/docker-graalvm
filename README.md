# Docker GraalVM Image

## Create the Docker image

```
$ docker build .
```

If everything goes well, it should end with

```
Successfully built <image ID>
```

## Launch the Docker image / run the container

```
$ winpty docker run -i -t <image ID>
```

## Test the container

Open a new terminal and type:

```
$ docker ps -a
```

You should see the <container ID> and the <image ID> in the output with status Up

Inside the Container terminal, type:

```
$ java -version
```

It should output:

```
openjdk version "1.8.0_172"
OpenJDK Runtime Environment (build 1.8.0_172-20180625212755.graaluser.jdk8u-src-tar-g-b11)
GraalVM 1.0.0-rc8 (build 25.71-b01-internal-jvmci-0.48, mixed mode)
```

## Update Docker image and push it back to Docker hub

In order to further update or add other JDK distributions to the Docker image, you might proceed as per below:

- locally start the container based on Docker image
- download the requested JDK distribution
- copy the JDK distribution inside the container
- unzip and install the JDK distribution inside the container

Then, to save the updated container as a new Docker image and push it back to the Docker hub, please proceed as below:

```
$ docker commit <container ID> ionutbalosin/<image name>:<tag>
```

In order to be able to push the Docker image, first please log in on [Docker hub](https://hub.docker.com/):

```
$ docker login --username ionutbalosin --password <password>
```

To push the Docker image to Docker Hub:

```
$ docker push ionutbalosin/<image ID>:<tag>
```

## Push/pull the Docker image to/from Docker hub

### Tag the Docker image

```
$ docker tag <image ID> ionutbalosin/<image name>
```

### Push the Docker image

```
$ docker push ionutbalosin/<image name>
```

For extra info about how to push/pull it to/from your own [Docker hub](https://hub.docker.com/) please visit this [page](https://ropenscilabs.github.io/r-docker-tutorial/04-Dockerhub.html)
