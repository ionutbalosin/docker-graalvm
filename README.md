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

```
$ java --version
```

It should output:

```
openjdk version "1.8.0_172"
OpenJDK Runtime Environment (build 1.8.0_172-20180625212755.graaluser.jdk8u-src-tar-g-b11)
GraalVM 1.0.0-rc8 (build 25.71-b01-internal-jvmci-0.48, mixed mode)
```