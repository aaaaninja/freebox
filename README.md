freebox
================================================================================
all in one docker image.

how to build
----------------------------------------
recommended way
```sh
DOCKER_BUILDKIT=1 docker build --squash -t freebox - < Dockerfile
```

### minimum build
```sh
docker build -t freebox .
```

### stdin build
```sh
docker build -t freebox - < Dockerfile
```

### parallel build (buildkit)
```sh
DOCKER_BUILDKIT=1 docker build -t freebox - < Dockerfile
# or
DOCKER_BUILDKIT=1 docker build -t freebox .
```

### layer squash build
><https://docs.docker.com/engine/reference/commandline/image_build/>
>Squash newly built layers into a single new layer

!!! Warning
    >"--squash" is only supported on a Docker daemon with experimental features enabled

    this way needs to write `"experimental": true` into your /etc/docker/daemon.json.
    ```json
    {
      "experimental": true
    }
    ```

#### minimum ver.
```sh
docker build --squash -t freebox - < Dockerfile
# or
docker build --squash -t freebox .
```

#### buildkit ver.
```sh
DOCKER_BUILDKIT=1 docker build --squash -t freebox - < Dockerfile
# or
DOCKER_BUILDKIT=1 docker build --squash -t freebox .
```
