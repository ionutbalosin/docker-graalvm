# Docker GraalVM Image

## Creating the imagine

```
$ docker build .
```

If everything goes well, it should end with

```
Successfully built <image ID>
```

## Launching the imagine / running the container

```
$ winpty docker run -i -t <image ID>
```

## Testing

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

## Push/pull to/from Docker hub

### Tag the image

```
$ docker tag <image ID> ionutbalosin/<image name>
```

### Push the image

```
$ docker push ionutbalosin/<image name>
```

For more info about how to push/pull it to/from your own [Docker hub](https://hub.docker.com/) please visit this [page](https://ropenscilabs.github.io/r-docker-tutorial/04-Dockerhub.html)

